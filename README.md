[![Build Status](https://travis-ci.org/kaelzhang/node-glob-gitignore.svg?branch=master)](https://travis-ci.org/kaelzhang/node-glob-gitignore)
<!-- optional appveyor tst
[![Windows Build Status](https://ci.appveyor.com/api/projects/status/github/kaelzhang/node-glob-gitignore?branch=master&svg=true)](https://ci.appveyor.com/project/kaelzhang/node-glob-gitignore)
-->
<!-- optional npm version
[![NPM version](https://badge.fury.io/js/glob-gitignore.svg)](http://badge.fury.io/js/glob-gitignore)
-->
<!-- optional npm downloads
[![npm module downloads per month](http://img.shields.io/npm/dm/glob-gitignore.svg)](https://www.npmjs.org/package/glob-gitignore)
-->
<!-- optional dependency status
[![Dependency Status](https://david-dm.org/kaelzhang/node-glob-gitignore.svg)](https://david-dm.org/kaelzhang/node-glob-gitignore)
-->

# glob-gitignore

Extends [`glob`](https://www.npmjs.com/package/glob) with support for filtering files according to gitignore rules and exposes an optional Promise API, based on [`node-ignore`](https://www.npmjs.com/package/ignore).

## Install

```sh
$ npm i glob-gitignore --save
```

## Usage

```js
import {
  glob
} from 'glob-gitignore'

// The usage of glob-gitignore is much the same as `node-glob`
glob('**', {
  cwd: '/path/to',

  // Except that options.ignore accepts an array of gitignore rules,
  // or a gitignore rule,
  // or an `ignore` instance.
  ignore: '*.bak'
})

// And glob-gitignore returns a promise
.then(files => {
  console.log(files)
})
```

## Why

1. The `options.ignore` of `node-glob` does not support gitignore rules.

2. It is better **NOT** glob things then filter them with [`node-ignore`](), to filter out files according to gitignore.

## License

MIT
