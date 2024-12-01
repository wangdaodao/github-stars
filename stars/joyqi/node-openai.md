---
project: node-openai
stars: 28
description: An elegant NodeJs library for openai api.
url: https://github.com/joyqi/node-openai
---

node-openai
===========

**An elegant Node.js library written in TypeScript for the OpenAI API. Pure JavaScript, no dependencies. Works in Node.js and the browser.**

-   Installation
-   Features
-   Example
-   V1 API
    -   Models
    -   Completions
    -   Chat
    -   Edits
    -   Images
    -   Embeddings
    -   Audio
    -   Files
    -   Fine-tunes
    -   Moderations

Installation
------------

npm install node-openai

### Features

API

Supported

Models

✅

Completions

✅

Chat

✅

Edits

✅

Images

✅

Embeddings

✅

Audio

✅

Files

✅

Fine-tunes

✅

Moderations

✅

Example
-------

For Node.js (CommonJS):

const { OpenAI } \= require('node-openai');

For ES Modules:

import { OpenAI } from 'node-openai';

For TypeScript:

import { OpenAI } from 'node-openai';

Create an instance of the OpenAI class:

const openai \= new OpenAI({
    apiKey: 'YOUR\_API\_KEY',
    // organization: 'YOUR\_ORGANIZATION\_ID',
    // endpoint: 'https://api.openai.com',
});

V1 API
------

To use the OpenAI V1 API, you must call the `v1()` method on the client instance:

const api \= openai.v1();

Check out the OpenAI V1 API docs for more information.

### Models

List all available models:

const models \= await api.models.list();

Retrieve a model:

const model \= await api.models.retrieve('davinci');

Delete fine-tuned model:

const model \= await api.models.delete('curie:ft-acmeco-2021-03-03-21-44-20');

### Completions

Create a completion:

const completion \= await api.completions.create({
    model: 'davinci',
    prompt: 'This is a test',
    max\_tokens: 5,
    temperature: 0.9,
    stream: false,
});

If the `stream` option is set to `true`, the completion will be streamed:

const stream \= await api.completions.create({
    model: 'davinci',
    prompt: 'This is a test',
    max\_tokens: 5,
    temperature: 0.9,
    stream: true,
});

const reader \= stream.pipeThrough(new TextDecoderStream()).getReader();
// Read the stream

### Chat

Create a chat:

const chat \= await api.chat.create({
    model: 'gpt-3.5-turbo',
    messages: \[
        {
            role: 'user',
            content: 'Hello, how are you?'
        }
    \]
});

### Edits

Create an edit:

const edit \= await api.edits.create({
    model: 'text-davinci-edit-001',
    input: 'I am a test',
    instruction: 'Make this text funny',
});

### Images

Create an image:

const image \= await api.images.create({
    prompt: 'A cute baby sea otter',
    n: 1,
    size: '512x512',
});

Create image edit:

const imageEdit \= await api.images.edit({
    prompt: 'Make this image funny',
    n: 1,
    size: '512x512',
}, '/path/to/image.png');

Create image variation:

const imageVariation \= await api.images.variation({
    n: 1,
    size: '512x512',
}, '/path/to/image.png');

### Embeddings

Create an embedding:

const embedding \= await api.embeddings.create({
    model: 'text-embedding-ada-002',
    input: 'This is a test',
});

### Audio

Create transcription:

const transcription \= await api.audio.createTranscription({
    model: 'whisper-1',
    prompt: 'This is a test',
}, '/path/to/audio.mp3');

Create translation:

const translation \= await api.audio.createTranslation({
    model: 'whisper-1',
    prompt: 'This is a test',
}, '/path/to/audio.mp3');

### Files

List all available files:

const files \= await api.files.list();

Retrieve a file:

const file \= await api.files.retrieve('file-123');

Upload a file:

const file \= await api.files.upload('/path/to/file.txt', 'fine-tune');

Delete a file:

const file \= await api.files.delete('file-123');

Retrieve a file's contents:

const content \= await api.files.retrieveContents('file-123');

### Fine-tunes

Create fine-tune:

const fineTune \= await api.fineTunes.create({
    training\_file: 'file-123',
});

List fine-tunes:

const fineTunes \= await api.fineTunes.list();

Retrieve fine-tune:

const fineTune \= await api.fineTunes.retrieve('ft-AF1WoRqd3aJAHsqc9NY7iL8F');

Cancel fine-tune:

const fineTune \= await api.fineTunes.cancel('ft-AF1WoRqd3aJAHsqc9NY7iL8F');

List fine-tune's events:

const events \= await api.fineTunes.listEvents('ft-AF1WoRqd3aJAHsqc9NY7iL8F');

### Moderations

Create moderation:

const moderation \= await api.moderations.create({
    model: 'text-moderation-stable',
    input: 'This is a test',
});
