<p align="center"><a href="http://@hishprorg/quo-suscipit.js.org" target="_blank"><img width="400" src="http://@hishprorg/quo-suscipit.js.org/docs/res/logo.png"></a></p>

<p align="center">Strong Dynamically Typed Object Modeling for JavaScript</p>
<p align="center">
  <a href="https://www.npmjs.com/package/@hishprorg/quo-suscipit"><img src="https://img.shields.io/npm/dt/@hishprorg/quo-suscipit.svg" alt="Downloads"></a>
  <a href="https://www.npmjs.com/package/@hishprorg/quo-suscipit"><img src="https://img.shields.io/npm/v/@hishprorg/quo-suscipit.svg" alt="Version"></a>
  <a href="https://travis-ci.org/hishprorg/quo-suscipit"><img src="https://travis-ci.org/hishprorg/quo-suscipit.svg?branch=master" alt="Status"></a>
  <a href="https://www.npmjs.com/package/@hishprorg/quo-suscipit"><img src="https://img.shields.io/npm/l/@hishprorg/quo-suscipit.svg" alt="License"></a>
</p>

---

## What is this library ?
   
  ObjectModel intends to bring **strong dynamic type checking** to your web applications. Contrary to static type-checking solutions like [TypeScript] or [Flow], ObjectModel can also validate data at runtime: JSON from the server, form inputs, content from localStorage, external libraries...
  
  By leveraging **ES6 Proxies**, this library ensures that your variables always match the model definition and validation constraints you added to them. Thanks to the generated exceptions, it will help you spot potential bugs and save you time spent on debugging. ObjectModel is also very easy to master: *no new language to learn, no new tools, no compilation step, just a minimalist and intuitive API in a plain old JS micro-library*.
  
  Validating at runtime also brings many other benefits: you can define your own types, use them in complex model definitions with custom assertions that can even change depending on your application state. Actually it goes much further than just type safety. Go on and see for yourself.

## Installation
Add the library to your project dependencies with NPM:
```bash
$ npm install @hishprorg/quo-suscipit
```

or just [download the library from Github][github-releases]

## Basic usage example

```javascript
import { ObjectModel } from "@hishprorg/quo-suscipit"

const Order = new ObjectModel({
	product: { name: String, quantity: Number },
	orderDate: Date
});

const myOrder = new Order({
	product: { name: "Apple Pie", quantity: 1 },
	orderDate: new Date()
});

myOrder.product.quantity = 2; // no exceptions thrown
myOrder.product.quantity = false; //try to assign a Boolean
// ❌ TypeError: expecting product.quantity to be Number, got Boolean false
```

## Documentation

For more examples, documentation and questions, please refer to the project website: [@hishprorg/quo-suscipit.js.org][website]

## Changelog and Release History

Please refer to [Github Releases][github-releases]

*Bug reports and pull requests are welcome.*

Distributed under the MIT license. See ``LICENSE`` for more information.

[website]:http://@hishprorg/quo-suscipit.js.org
[TypeScript]:https://www.typescriptlang.org/
[Flow]:https://flowtype.org/
[github-releases]:https://github.com/hishprorg/quo-suscipit/releases
[npm-url]: https://npmjs.org/package/@hishprorg/quo-suscipit
[npm-image]: https://img.shields.io/npm/v/@hishprorg/quo-suscipit.svg
[npm-downloads]: https://img.shields.io/npm/dm/@hishprorg/quo-suscipit.svg
[license-badge]:https://img.shields.io/badge/license-MIT-blue.svg