---
project: sablejs
stars: 1102
description: 🏖️ The safer and faster ECMA5.1 interpreter written by JavaScript
url: https://github.com/sablejs/sablejs
---

> 🎉 sablejs 2.0 will be opening all the code, please click to learn more about our milestone and goals.

English | 简体中文

The safer and faster ECMA5.1 interpreter written by JavaScript, it can be used:

1.  Sandbox (like Figma Plugin Sandbox, but better and easier to use);
2.  Protect JavaScript source code via AOT compiling to opcode.

sablejs covered ~95% test262 es5-tests cases, it can be safely used in production.

-   Quick Start
-   APIs
-   Benchmark
-   Limits
-   Bindings
-   License

### Quick Start

**sablejs includes the Compiler and Interpreter independently**, so we removed the related dynamic api from the spec (see Limits 1). In short, you need to compile your JavaScript code with sablejs cli before you run it.

#### Example

Suppose we have the following code in `fib.js`:

function fib(n) {
  return n < 2 ? n : fib(n \- 1) + fib(n \- 2);
}

var start \= Date.now();
console.log("\[INFO\] fib: " + fib(30));
console.log("\[INFO\] time consuming: " + (Date.now() \- start) + "ms");

#### Compile It!

\> npm i sablejs -g
\> sablejs -i fib.js -o output # get output file that contains base64 string

sablejs cli includes the following commands:

Usage: sablejs \[options\]

Options:
  -v, --vers           output the current version
  -i, --input <path\>   compile input filepath
  -o, --output <path\>  compile output filepath
  -j  --json           don't do Base64 compress, output simple json result
  -s, --slient         don't output log
  -h, --help

#### Run It!

\> npm install sablejs --save

or you can import to your html directly

<script src\="https://cdn.jsdelivr.net/npm/sablejs@1.0.8/runtime.js"\></script\>

##### Browser

const VM \= require("sablejs/runtime")();

// import console.log function to vm call
const vm \= new VM();
const vGlobal \= vm.getGlobal();
const vConsole \= vm.createObject();
const vLog \= vm.createFunction("log", function () {
  const temp \= \[\];
  for (let i \= 0; i < arguments.length; i++) {
    temp.push(vm.asString(arguments\[i\]));
  }

  console.log(...temp);
  return vm.createUndefined();
});

vm.setProperty(vConsole, "log", vLog);
vm.setProperty(vGlobal, "console", vConsole);

(async () \=> {
  const resp \= await fetch("<output url>");
  const data \= await resp.text();
  vm.run(data);
  vm.destroy();
})();

##### Node

const VM \= require("sablejs/runtime")();
const fs \= require("fs");

// import console.log function to vm call
const vm \= new VM();
const vGlobal \= vm.getGlobal();
const vConsole \= vm.createObject();
const vLog \= vm.createFunction("log", function () {
  const temp \= \[\];
  for (let i \= 0; i < arguments.length; i++) {
    temp.push(vm.asString(arguments\[i\]));
  }

  console.log(...temp);
  return vm.createUndefined();
});

vm.setProperty(vConsole, "log", vLog);
vm.setProperty(vGlobal, "console", vConsole);

// please run: sablejs -i fib.js -o output
vm.run(fs.readFileSync("./output").toString());
vm.destroy();

### APIs

-   VM.prototype.run(source, isSimpleJSON)
    -   source: String - the compiled result via sablejs compiler
    -   isSimpleJSON: Boolean - if be true, you should use `-j` to make compiler output simple json result, default false.
    -   `return:` undefined

Initialize the VM and execute the compiled source code.

const VM \= require('sablejs/runtime')();
const vm \= new VM();

// source should be base64 string via sablejs compiling
vm.run(\`<compiled source string>\`);

-   VM.prototype.getGlobal()
    -   `return:` Value

Returns the `global` in the VM, which is similar to the `window` in browser and the `global` in Node.js.

const global \= vm.getGlobal();

-   VM.prototype.createUndefined()
    -   `return` Value

Create an `undefined` boxed type.

const vUndefined \= vm.createUndefined();

-   VM.prototype.createNull()
    -   `return:` Value

Create an `null` boxed type.

const vNull \= vm.createNull();

-   VM.prototype.createBoolean(bool)
    -   bool: Boolean
    -   `return` Value

Create an `bool` boxed type.

const vBoolean \= vm.createBoolean(true);

-   VM.prototype.createNumber(num)
    -   num: Number
    -   `return` Value

Create an `number` boxed type.

const vNumber \= vm.createNumber(1024);

-   VM.prototype.createString(str)
    -   str: String
    -   `return` Value

Create an `string` boxed type.

const vString \= vm.createString('Hello World!');

-   VM.prototype.createObject()
    -   `return` Value

Create an `object` boxed type.

const vObject \= vm.createObject();

-   VM.prototype.createArray(length)
    -   length: Number | undefined
    -   `return` Value

Create an `array` boxed type.

const vArray1 \= vm.createArray();
// or
const vArray2 \= vm.createArray(128);

-   VM.prototype.createFunction(name, func)
    -   name: String
    -   func: Function
    -   `return` Value

Create an `funcntion` boxed type. It receives a function name and the specific implementation of the function. Both the `function parameter` and `this` are boxed types in `func`.

const vFunction \= vm.createFunction("trim", function(str) {
  // this is the undefined or new's instannce boxed type
  // str maybe the string boxed type, we need to check it
});

-   VM.prototype.createError(message)
    -   message: String | undefined
    -   `return` Value

Create an `error` boxed type.

const vError1 \= vm.createError();
// or
const vError2 \= vm.createError("unknown error");

-   VM.prototype.createRegExp(pattern, flags)
    -   pattern: String
    -   flags: String | undefined
    -   `return` Value

Create an `regexp` boxed type.

const vRegExp \= vm.createRegExp("\\\\w+", "ig");

-   VM.prototype.createDate()
    -   `return` Value

Create an `date` boxed type.

const vDate \= vm.createDate();

-   VM.prototype.isUndefined(value)
    -   value: Value
    -   `return` Boolean

Used to determine if the type is `undefinend`.

const vUndefined \= vm.createUndefined();
if(vm.isUndefined(vUndefined)) {
  // ...
}

-   VM.prototype.isNull(value)
    -   value: Value
    -   `return` Boolean

Used to determine if the type is `null`.

const vNull \= vm.createNull();
if(vm.isNull(vNull)) {
  // ...
}

-   VM.prototype.isBoolean(value)
    -   value: Value
    -   `return` Boolean

Used to determine if the type is `bool`.

const vBoolean \= vm.createBoolean(true);
if(vm.isBoolean(vBoolean)) {
  // ...
}

-   VM.prototype.isNumber(value)
    -   value: Value
    -   `return` Boolean

Used to determine if the type is `number`.

const vNumber \= vm.createNumber(1024);
if(vm.isNumber(vNumber)) {
  // ...
}

-   VM.prototype.isString(value)
    -   value: Value
    -   `return` Boolean

Used to determine if the type is `string`.

const vString \= vm.createString("Hello World!");
if(vm.isString(vString)) {
  // ...
}

-   VM.prototype.isObject(value)
    -   value: Value
    -   `return` Boolean

Used to determine if the type is `object`.

const vObject \= vm.createObject();
const vArray \= vm.createArray();
if(vm.isObject(vObject) && vm.isObject(vArray)) {
  // ...
}

-   VM.prototype.isArray(value)
    -   value: Value
    -   `return` Boolean

Used to determine if the type is `array`.

const vArray \= vm.createArray();
if(vm.isArray(vArray)) {
  // ...
}

-   VM.prototype.isFunction(value)
    -   value: Value
    -   `return` Boolean

Used to determine if the type is `function`.

const vFunction \= vm.createFunction("log", function(){});
if(vm.isFunction(vFunction)){
  // ...
}

-   VM.prototype.isError(value)
    -   value: Value
    -   `return` Boolean

Used to determine if the type is `error`.

const vError \= vm.createError('unknown error');
if(vm.isError(vError)){
  // ...
}

-   VM.prototype.isRegExp(value)
    -   value: Value
    -   `return` Boolean

Used to determine if the type is `regexp`.

const vRegExp \= vm.createRegExp("\\\\w+", "ig");
if(vm.isRegExp(vRegExp)){
  // ...
}

-   VM.prototype.isDate(value)
    -   value: Value
    -   `return` Boolean

Used to determine if the type is `date`.

const vDate \= vm.createDate();
if(vm.isDate(vDate)){
  // ...
}

-   VM.prototype.asUndefined(value)
    -   value: Value
    -   `return` undefined

Converting `undefined` boxed type to `plain undefined` value.

const vUndefined \= vm.createUndefined();
vm.asUndefined(vUndefined) \=== undefined;

-   VM.prototype.asNull(value)
    -   value: Value
    -   `return` null

Converting `null` boxed type to `plain null` value.

const vNull \= vm.createNull();
vm.asNull(vNull) \=== null;

-   VM.prototype.asBoolean(value)
    -   value: Value
    -   `return` Boolean

Converting `bool` boxed type to `plain bool` value.

const vBoolean \= vm.createBoolean(true);
const boolean \= vm.asBoolean(vBoolean);
if(boolean \=== true) {
  // ...
}

-   VM.prototype.asNumber(value)
    -   value: Value
    -   `return` Number

Converting `number` boxed type to `plain number` value.

const vNumber \= vm.createNumber(1024);
const number \= vm.asNumber(vNumber);
if(number \=== 1024) {
  // ...
}

-   VM.prototype.asString(value)
    -   value: Value
    -   `return` String

Converting `string` boxed type to `plain string` value.

const vString \= vm.createString('Hello World!');
const string \= vm.asString(vString);
if(string \=== 'Hello World!') {
  // ...
}

-   VM.prototype.asObject(value)
    -   value: Value
    -   `return` Object

Converting `object` boxed type to `inner object` value.

const vObject \= vm.createFunction("asObject", function(){});
const object \= vm.asObject(vObject);
if(object.type \=== 12) {
  // ...
}

-   VM.prototype.instanceof(lval, rval)
    -   lval: Value
    -   rval: Value
    -   `return` Boolean

Equivalent to the `instanceof` keyword.

const global \= vm.getGlobal();
const vDateFunc \= vm.getProperty(global, "Date");
const vDate \= vm.createDate();
if(vm.instanceof(vDate, vDateFunc)) {
  // ...
}

-   VM.prototype.typeof(value)
    -   value: Value
    -   `return` String

Equivalent to the `typeof` keyword.

const vString \= vm.createString('Hello World!');
if(vm.typeof(vString) \=== "string") {
  // ...
}

-   VM.prototype.getProperty(value, name)
    -   value: Value
    -   name: String
    -   `return` Value

Get the value of the property of the object. Return is a property boxed type.

const global \= vm.getGlobal();
const vPrint \= vm.getProperty(global, "print");
if(vm.isFunction(vPrint)) {
  // ...
}

-   VM.prototype.setProperty(value, name, property)
    -   value: Value
    -   name: String
    -   property: Value
    -   `return` Value

Assigning the property to object. Return is a property boxed type.

const global \= vm.getGlobal();
const console \= vm.createObject();
const log \= vm.createFunction("log", function() {
  // console.log impl
});

vm.setProperty(console, "log", log);
vm.setProperty(global, "console", console);

-   VM.prototype.deleteProperty(value, name)
    -   value: Value
    -   name: String
    -   `return` Boolean

Delete the property of object.

const global \= vm.getGlobal();
vm.deleteProperty(global, "print");

const vPrint \= vm.getProperty(global, "print");
if(vm.isUndefined(vPrint)) {
  // ...
} 

-   VM.prototype.defineProperty(value, name, desc)
    -   value: Value
    -   name: String
    -   desc: Object
    -   `return` Value

Equivalent to the `Object.defineProperty` function.

const vObject \= vm.createObject();
vm.defineProperty(vObject, "name", { 
  value: vm.createString("sablejs"),
});

const getter \= vm.createFunction("getter", function() {
  return vm.createNumber("101");
});

const setter \= vm.createFunction("setter", function(age) {
  vm.setProperty(this, "\_\_age\_\_", age);
});

vm.defineProperty(vObject, "age", {
  enumerable: false,
  get: getter,
  set: setter,
});

-   VM.prototype.getPrototype(value)
    -   value: Value
    -   `return` Value

Get the prototype of object.

const global \= vm.getGlobal();
const vStringFunc \= vm.getProperty(global, "String");
if(!vm.isUndefined(vStringFunc)) {
  const vTrimStart \= vm.createFunction("trimStart", function() {
    const str \= vm.asString(this);
    return vm.createString(str);
  });

  const vStringFuncProto \= vm.getPrototype(vStringFunc);
  vm.setProperty(vStringFuncProto, "trimStart", vTrimStart);
}

-   VM.prototype.setPrototype(value, prototype)
    -   value: Value
    -   prototype: Value
    -   `return` Value

Set the prototype of object.

const vA \= vm.createFunction("A", function() {});
const vObject \= vm.createObject();

vm.setProperty(vObject, 'name', vm.createString('Hello World!'));
vm.setPrototype(vA, vObject);

-   VM.prototype.throw(value)
    -   value: Value
    -   `return` undefined

Equivalent to the `throw` keyword.

const vError \= vm.createError('unknown error');
vm.throw(vError);

-   VM.prototype.new(func\[, arg1, arg2, arg3...\])
    -   func: Value
    -   arg: Value
    -   `return` Value

Equivalent to the `new` keyword.

const vA \= vm.createFunction('A', function(name) {
  vm.setProperty(this, 'name', name);
});

vm.new(vA, vm.createString("A"));

-   VM.prototype.call(func, thisPtr\[, arg1, arg2, arg3...\])
    -   func: Value
    -   thisPtr: Value | undefined
    -   arg: Value
    -   `return` Value

Equivalent to the `Function.prototype.call` function.

const vLog \= vm.createFunction('log', function() {
  const temp \= \[\];
  for(let i \= 0; i < arguments.length; i++){
    temp.push(vm.asString(arguments\[i\]));
  }
  console.log(...temp); // '1', 1, false
});

vm.call(
  vLog, 
  vm.createUndefined(), 
  vm.createString('1'), 
  vm.createNumber(1), 
  vm.createBoolean(false)
);

-   VM.prototype.destroy
    -   `return` undefined

Destroy the VM instance.

vm.destroy();

### Benchmark

sablejs may be the fastest interpreter written in JavaScript (using v8 benchmark suites):

> Benchmark Enviorment:
> 
> -   Node.js v12.19.0
> -   Golang 1.15.6
> -   GCC 5.4.0 -O3
> -   2.4 GHz Intel Core i9
> -   MacOS Mojave 10.14.6 (18G6032)

sablejs

sval

eval5

quickjs-wasm

goja

Language

JavaScript

JavaScript

JavaScript

C + WebAssembly

Golang

Richards

110

24.9

24.7

376

208

Crypto

114

24.6

20.2

400

104

RayTrace

258

92.2

98.5

471

294

NavierStokes

183

35.9

49.8

665

191

DeltaBlue

120

35.3

29.5

402

276

Total score

148

37.3

37.3

452

202

Baseline

1

▼ 2.96

▼ 2.96

▲ 2.05

▲ 0.36

File Size(KB)

216

152

134

434

\-

Gzip Size(KB)

29

40

34

245

\-

### Limits

1.  Dynamic execution by `eval` and `Function` is forbidden, but passing literal string/number/null and undefined is allowed (the interpreter doesn't contain any compiler).

eval("print('Hello World!')"); // it's ok
eval("var " + "a=1"); // it's ok

var str \= "Hello World!";
eval("print('" + str + "')"); // throw SyntaxError

Function("a", "b", "return a+b"); // it's ok
new Function("a", "b", "return a+b"); // it's ok

var str \= "return a+b";
Function("a", "b", str); // throw SyntaxError
new Function("a", "b", str); // throw SyntaxError

1.  The browser environment relies on native browser functions such as `btoa` / `unescape` / `decodeURIComponent`, etc. if you need support for IE9 or below, you need to add shims.

### Bindings

-   cax2sablejs - Canvas2D rendering engine for sablejs
-   ajax2sablejs - A tiny and simple ajax for sablejs

### License

sablejs JavaScript Engine

Copyright (c) 2020-Now ErosZhao

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

Non-profit projects of individuals or organizations and commercial projects with commercial authorization of the author.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
