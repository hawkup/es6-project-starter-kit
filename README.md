Universal Starter Kit to build any javascript ES6 project/library runnable in nodejs and on any browser
====================

[![Build Status][travis-image]][travis-url]

[![Dependency Status][gemnasium-image]][gemnasium-url]
[![NPM version][npm-version-image]][npm-url]
[![NPM downloads][npm-downloads-image]][npm-url]

[![MIT License][license-image]][license-url]

[![Sauce Test Status][saucelabs-image]][saucelabs-url]


# Introduction

javascript 2015/es6/next introduces a lot of new cool [features](https://babeljs.io/features.html) unfortunately not yet available in the current modern browsers. This starter kit contains all the tools you need to let you run your ES6 code on any kind of platform.

# Philosophy

> Just use what you really need

This project __doesn't rely on any build system tool__ like gulp, grunt, duo...
By using the [make](make) file and customizing the tasks in the [tasks](tasks) folder you should be able to develop any kind of javascript project just fitting it to your needs

## javascript ES6

```javascript

import helpers from './helpers/helpers';

/**
 * @class
 * An awesome script
 */
class Greeter {
  constructor(name = 'Dear Coder', text = 'hi there') {
    this.name = name;
    this.text = text;
  }
  get message() {
    return `${this.text} ${this.name}!`;
  }
  set message(text) {
    this.text = helpers.trim(text);
  }
}

export default Greeter;
```

```javascript
var greeter = new Greeter();

console.log(greeter.message) // -> hi there Dear Coder!
// these white spaces will be trimmed
greeter.message = '   goodbye';
console.log(greeter.message) // -> goodbye Dear Coder!

```


## Tools available

- [babeljs](https://babeljs.io/)
- [webpack](https://github.com/webpack/webpack)
- [karma](https://github.com/karma-runner/karma)
- [chai](https://github.com/chaijs/chai)
- [eslint](https://github.com/eslint/eslint)
- [sinon](https://github.com/cjohansen/Sinon.JS)
- [serve](https://github.com/tj/serve)

# Usage

Once you've downloaded the files in this repo please run the following command in your terminal from the project folder (it may require `sudo`):

```shell
$ npm install
```

Browsing the [make](make) file you will find all the available terminal commands to compile/test your project. __This file contains also the script name used for the output__
All the build tasks available are based on the __native javascript promises__ so you will be able to chain and combine them as you prefer

If you have installed correctly all the nodejs modules you can start writing your javascript modules into the `src` folder of course using the awesome javascript es6 syntax.

## Available tasks

### Build and test
```shell
$ ./make
```

### Convert the ES6 code into valid ES5 combining all the modules into one single file
```shell
$ ./make build
```

### Run all the tests
```shell
$ ./make test
```

### Start a nodejs static server
```shell
$ ./make serve
```

### To compile and/or test the project anytime a file gets changed
```shell
$ ./make watch
```

### Run the saucelabs tests
```shell
$ ./make saucelabs
```

# Dependencies

All the code generated depends on the tiny [babel/external-helpers](https://babeljs.io/docs/usage/external-helpers/)
You can include the babel helpers directly in your library ( [updating this line](https://github.com/GianlucaGuarini/es6-project-starter-kit/blob/master/tasks/build.js#L36) ) or just loading it in your page before your script:
```html
<script src="your-path-to/babel/external-helpers.js"></script>
<script src="my-awesome-script.js"></script>
```


[npm-url]: https://npmjs.org/package/es6-project-starter-kit
[npm-version-image]: http://img.shields.io/npm/v/es6-project-starter-kit.svg?style=flat-square
[npm-downloads-image]: http://img.shields.io/npm/dm/es6-project-starter-kit.svg?style=flat-square

[gemnasium-image]: https://img.shields.io/gemnasium/GianlucaGuarini/es6-project-starter-kit.svg?style=flat-square
[gemnasium-url]: https://gemnasium.com/GianlucaGuarini/es6-project-starter-kit

[travis-url]:https://travis-ci.org/GianlucaGuarini/es6-project-starter-kit
[travis-image]: https://img.shields.io/travis/GianlucaGuarini/es6-project-starter-kit.svg?style=flat-square

[saucelabs-image]:https://saucelabs.com/browser-matrix/es6-project-starter-kit.svg
[saucelabs-url]:https://saucelabs.com/u/es6-project-starter-kit

[saucelabs-image]:https://saucelabs.com/browser-matrix/es6projectstarterkit.svg
[saucelabs-url]:https://saucelabs.com/u/es6projectstarterkit

[license-url]: LICENSE
[license-image]: http://img.shields.io/badge/license-MIT-000000.svg?style=flat-square

