---
layout: post
title: "Error fix: module 'require' not defined/found & similar errors - NodeJS"
thumbnail-img: assets/img/2022-08-03/nodejslogo.png
cover-img: 
date: 2022-08-03
last-updated:
tags: nodejs programming javascript
---

When running a `nodejs` project on my computer, I ran into a similar error to the one below:

```bash
var express = require('express');
              ^
              
ReferenceError: require is not defined in ES module scope, you can use import instead
This file is being treated as an ES module because it has a '.js' file extension and '/home/ismael/Projects/private-website-blocker/package.json' contains "type": "module". To treat it as a CommonJS script, rename it to use the '.cjs' file extension.
```

After some research, it turns out that I had ESM (ECMAScript modules) enabled in my `package.json` file.

```
//package.json
{
    "type": "module"
    ...
}
```

To fix this problem, I either needed to use [CommonJS modules](https://nodejs.org/dist/latest-v16.x/docs/api/modules.html#modules-commonjs-modules) and remove `"type": "module"` from `package.json` or use [ECMAScript modules](https://nodejs.org/dist/latest-v16.x/docs/api/esm.html#introduction) and use ES6 syntax. Although I could use both, I chose the latter option to make things simple and consistent. To transition to ES6 syntax, I made changes to my code similar to the following example:

From:
```
const express = require('express');

exports.myExport = 7 * 3;

module.exports = class MyClass {
    ...
}


```

To:
```
import express from 'express';

export const myExport = 7 * 3;

export class MyClass {
    ...
}
```

Further reading:
- [https://nodejs.org/dist/latest-v16.x/docs/api/esm.html#introduction](https://nodejs.org/dist/latest-v16.x/docs/api/esm.html#introduction)
- [https://nodejs.org/dist/latest-v16.x/docs/api/modules.html#modules-commonjs-modules](https://nodejs.org/dist/latest-v16.x/docs/api/modules.html#modules-commonjs-modules)
- [https://tc39.es/ecma262/#sec-modules](https://tc39.es/ecma262/#sec-modules)

Thumbnail image source: [https://pixabay.com/vectors/node-js-logo-nodejs-javascript-736399/](https://pixabay.com/vectors/node-js-logo-nodejs-javascript-736399/)