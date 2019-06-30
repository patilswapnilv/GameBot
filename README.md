# GameBot

[![Build Status](https://travis-ci.org/patilswapnilv/GameBot.svg?branch=dev)](https://travis-ci.org/patilswapnilv/GameBot)
[![Build status: Windows](https://ci.appveyor.com/api/projects/status/b5xy6ev6oykth0d2/branch/master?svg=true)](https://ci.appveyor.com/project/patilswapnilv/GameBot/branch/dev)
[![NPM version](http://img.shields.io/npm/v/GameBot.svg?style=flat)](https://www.npmjs.com/package/GameBot)
[![Dependency Status](https://david-dm.org/patilswapnilv/GameBot.svg)](https://david-dm.org/patilswapnilv/GameBot)
[![devDependency Status](https://david-dm.org/patilswapnilv/GameBot/dev-status.svg)](https://david-dm.org/patilswapnilv/GameBot#info=devDependencies)

> GameBot chrome extension to keep yourself updates on your favorite games

## Features

 - Simple [React](https://github.com/facebook/react)/[Redux](https://github.com/rackt/redux) examples of Chrome Extension Window & Popup & Inject pages
 - Hot reloading React/Redux (Using [Webpack](https://github.com/webpack/webpack) and [React Transform](https://github.com/gaearon/react-transform))
 - Write code with ES2015+ syntax (Using [Babel](https://github.com/babel/babel))
 - E2E tests of Window & Popup & Inject pages (Using [Chrome Driver](https://www.npmjs.com/package/chromedriver), [Selenium Webdriver](https://www.npmjs.com/package/selenium-webdriver))


## Installation

```bash
# clone it
$ git clone https://github.com/patilswapnilv/GameBot.git

# Install dependencies
$ npm install
```

## Development

* Run script
```bash
# build files to './dev'
# start webpack development server
$ npm run dev
```
* If you're developing Inject page, please allow `https://localhost:3000` connections. (Because `injectpage` injected GitHub (https) pages, so webpack server procotol must be https.)
* [Load unpacked extensions](https://developer.chrome.com/extensions/getstarted#unpacked) with `./dev` folder.


## Build

```bash
# build files to './build'
$ npm run build
```

## Compress

```bash
# compress build folder to {manifest.name}.zip and crx
$ npm run build
$ npm run compress -- [options]
```

#### Options

If you want to build `crx` file (auto update), please provide options, and add `update.xml` file url in [manifest.json](https://developer.chrome.com/extensions/autoupdate#update_url manifest.json).

* --app-id: your extension id (can be get it when you first release extension)
* --key: your private key path (default: './key.pem')  
  you can use `npm run compress-keygen` to generate private key `./key.pem`
* --codebase: your `crx` file url

See [autoupdate guide](https://developer.chrome.com/extensions/autoupdate) for more information.

## Test

* `test/app`: React components, Redux actions & reducers tests
* `test/e2e`: E2E tests (use [chromedriver](https://www.npmjs.com/package/chromedriver), [selenium-webdriver](https://www.npmjs.com/package/selenium-webdriver))

```bash
# lint
$ npm run lint
# test/app
$ npm test
$ npm test -- --watch  # watch files
# test/e2e
$ npm run build
$ npm run test-e2e
```

## LICENSE

[GPL3.0](LICENSE)
