---
project: pdf-img-convert.js
stars: 195
description: Simple node package to convert a PDF into images.
url: https://github.com/ol-th/pdf-img-convert.js
---

pdf-img-convert.js
==================

**A lightweight JavaScript package for converting PDFs into images, built on Mozilla's powerful PDF.js library.**

Motivation
----------

While there are numerous JavaScript solutions for converting PDFs, many rely heavily on the filesystem by creating temporary files and using non-native binaries like Ghostscript.

This solution simplifies the process by exclusively using JavaScript arrays, significantly streamlining the pipeline and, ideally, enhancing performance.

Installation
------------

npm install pdf-img-convert

Usage
-----

The package by default returns an `Array` of `Uint8Array` objects, each of which represents an image encoded in png format or a base64-encoded image output if required

Here are some examples of how to use the module. First, make sure to import it

const pdf2img \= await import("pdf-img-convert");

The package provides a single function, convert, which accepts the following PDF formats as input:

-   URL of a PDF (e.g., www.example.com/sample.pdf)
    
-   Path to a local PDF file (e.g., ./examples/sample.pdf)
    
-   A `Buffer` object containing PDF data
    
-   A `Uint8Array` object containing PDF data
    
-   Base64-encoded PDF data
    

**Note: The convert function is asynchronous and returns a `Promise` object.**

The output can be manipulated using the `conversion_config` argument mentioned below.

Here's an example of how to use it in synchronous code, `uint8arrays` as the default output:

import fs from 'fs';
import path from 'path';

async function processPDFs() {
    const pdf2img \= await import("pdf-img-convert");

    // Both HTTP, HTTPS, and local paths are supported
    const outputWithExternalLink \= await pdf2img.convert('https://sedl.org/afterschool/toolkits/science/pdf/ast\_sci\_data\_tables\_sample.pdf');
    const outputWithLocalSample \= await pdf2img.convert('./test\_pdfs/sample.pdf');

    // OUTPUT OPTIONS ARRAY
    const outputs \= \[outputWithExternalLink, outputWithLocalSample\];
    
    const pdfArray \= outputs\[0\]; // Change the index to select different outputs

    function saveImages(pdfArray) {
        pdfArray.forEach((image, index) \=> {
            const outputPath \= path.join('./outputImages', \`saveImages\_${index}.png\`);
            fs.writeFile(outputPath, image, (error) \=> {
                if (error) {
                    console.error(\`Error saving image ${index + 1}:\`, error);
                } else {
                    console.log(\`Image ${index + 1} saved successfully\`);
                }
            });
        });
    }
    // Call the function to save images
    saveImages(pdfArray);
}
// Call the async function
processPDFs();

Here's an example of how to use it in synchronous code, `base64-encoded` output as the chosen option:

import fs from 'fs';
import path from 'path';

let config \= {
    base64: true,
    scale: 2
};
async function processPDF() {
    const pdf2img \= await import("pdf-img-convert");
    const outputWithLocalSampleAndConfig \= await pdf2img.convert('./examples/example.pdf', config);
    const pdfArray \= outputWithLocalSampleAndConfig;
    function saveBase64Images(pdfArray) {
        console.log('Processing base64Images...');
        pdfArray.forEach((base64Data, index) \=> {
            // Convert Base64 string to binary buffer
            const buffer \= Buffer.from(base64Data, 'base64');
            // Define an output path
            const outputPath \= path.join('./outputImages', \`saveBase64Image\_${index}.png\`);
            // Write the buffer to a PNG file
            fs.writeFile(outputPath, buffer, (error) \=> {
                if (error) {
                    console.error(\`Error saving image ${index + 1} (base64):\`, error);
                } else {
                    console.log(\`Image ${index + 1} (base64) saved successfully\`);
                }
            });
        });
    }
    // Example usage: call this function with the Base64 array
    saveBase64Images(pdfArray);
}
// Call the async function
processPDF();

Here's an example of how to use it in Next.js api folder, `base64-encoded` output as the chosen option:

_Ensure you have a dotenv file with `ROOT_PATH` pointing to your root directory_

ROOT\_PATH\=./

_You have a `/public/uploads directory` in the root entry of your project, if not create it._

import path from "path";
import fs from "fs";

const UPLOAD\_DIR \= path.resolve(process.env.ROOT\_PATH ?? "", "public/uploads");

/\*SHARP ENHANCEMENT\*/
const writeToDir \= async (imageData, fileName, filePath) \=> {
    try {
        await fs.promises.writeFile(filePath, imageData);
        console.log(\`Image processed and saved successfully: ${filePath}\`);
        return {
            fileName: fileName,
            filePath: filePath
        };
    } catch (error) {
        console.error("Error processing the image:", error);
        return null;
    }
};
export const POST \= async (req: NextRequest) \=> {
    const pdf2img \= await import("pdf-img-convert");
    const formData \= await req.formData();
    const pdfFiles \= \[\]
    const convertedImages \= \[\]

    // Loop over the FormData content
    for (const \[key, value\] of formData.entries()) {
        if (value instanceof Blob) {
            if (key \=== "pdfFiles") {
                pdfFiles.push(value);
            }
        }
    }
    // check for file uploads
    if (pdfFiles.length \=== 0) {
        return NextResponse.json({
            success: false,
            message: "No files uploaded"
        });
    }
    for (const file of pdfFiles) {
        const pdfBuffer \= Buffer.from(await file.arrayBuffer());
        const imagePages \= await pdf2img.convert(pdfBuffer, { base64: true }); // Ensure base64 is true to get Base64 data

        for (let i \= 0; i < imagePages.length; i++) {
            const imageData \= imagePages\[i\];
            const base64Data \= imageData.replace(/^data:image\\/\\w+;base64,/, ""); // Remove Base64 header
            const imageBuffer \= Buffer.from(base64Data, "base64"); // Convert Base64 to Buffer

            const fileName \= \`${path.basename(file.name, path.extname(file.name))}\_page\_${i + 1}.png\`;
            const filePath \= path.join(UPLOAD\_DIR, fileName);

            const writeFile \= await writeToDir(imageBuffer, fileName, filePath);
            if (writeFile) {
                convertedImages.push(writeFile);
            }
        }
    }
    // if successfully
    return NextResponse.json({
        success: true,
        message: "Files uploaded successfully",
    });
}

Here is how to fetch single or multiple PDF documents from the client side using a `.jsx or .tsx` component:

_In this case my `api` route points to `/app/api/pdf2img`, you can change it to suite your own naming_

"use client";
import React, { useRef, useState } from "react";
export default function PDFUploader() {
    const MAX\_FILES \= 4;
    const \[fileNames, setFileNames\] \= useState(\[\]);
    const \[pdfFiles, setPdfFiles\] \= useState(\[\]);
    const \[errorMessage, setErrorMessage\] \= useState("");
    const fileInputRef \= useRef(null);

    const handleFileChange \= (e) \=> {
        const files \= Array.from(e.target.files);
        if (files.length \> MAX\_FILES) {
            setErrorMessage(\`You can only upload a maximum of ${MAX\_FILES} files.\`);
            clearStates();
        } else {
            const names \= files.map((file) \=> file.name);
            const pdfs \= files.filter(file \=> file.type \=== "application/pdf");
            setStates(pdfs, names);
        }
    };

    const handleSubmit \= async (e) \=> {
        e.preventDefault();
        if (pdfFiles.length \=== 0) {
            setErrorMessage("No PDF files selected.");
            return;
        }
        try {
            const formData \= new FormData();
            pdfFiles.forEach((file) \=> {
                formData.append("pdfFiles", file); // Key is "pdfFiles"
            });

            const response \= await fetch("/api/pdf2img", {
                method: "POST",
                body: formData
            });

            const result \= await response.json();
            if (result.success) {
                clearStates();
                alert(\`Upload successful: ${result.message}\`);
            } else {
                alert(\`Upload failed: ${result.message}\`);
            }
        } catch (error) {
            console.error("Upload error:", error);
            alert("An error occurred during upload.");
        }
    };

    const clearStates \= () \=> {
        setFileNames(\[\]);
        setPdfFiles(\[\]);
        if (fileInputRef.current) {
            fileInputRef.current.value \= ""; // Reset the file input via ref
        }
    };

    const setStates \= (pdfs, names) \=> {
        setPdfFiles(pdfs);
        setFileNames(names);
    };

    return (
        <html\>
        <body style\={{padding:0, left: 0}}\>
        <form onSubmit\={handleSubmit}\>
            <input
                ref\={fileInputRef}
                onChange\={handleFileChange}
                type\="file"
                name\="fileUpload"
                multiple
                accept\=".pdf"
            />
            <button type\="submit"\>Submit</button\>
        </form\>
        {errorMessage && (
            <div\>
                <p style\={{ textAlign: "center", color: "red" }}\>{errorMessage}</p\>
            </div\>
        )}
        </body\>
        </html\>
    );
}

There is also an optional second `conversion_config` argument which accepts an object like this:

{
  width: 100 //Number in px
  height: 100 // Number in px
  scale: 2
  page\_numbers: \[1, 2, 3\] // A list of pages to render instead of all of them
  base64: true
}

The following attributes are optional and can be omitted from the configuration object:

-   `width` or `height`: Controls the scale of the output images. If both are provided, only width will be used, and height will be ignored.
    
-   `page_numbers`: Specifies which pages to render. Pages are 1-indexed.
    
-   `base64`: Set to true to receive base64-encoded image output. If omitted or set to false, the output will be an array of Uint8Arrays.
    
-   `scale`: Defines the viewport scale ratio, defaulting to 1 (original width and height).
    

Contributing
------------

If you'd like to contribute, please do submit a pull request!

Once you've finalised your changes, please include a summary of these changes under the `[Unreleased]` section of `CHANGELOG.md` in this format.
