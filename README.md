# @coon-js/extjs-package-loader ![MIT](https://img.shields.io/npm/l/@coon-js/extjs-package-loader) [![npm version](https://badge.fury.io/js/@coon-js%2Fextjs-package-loader.svg)](https://badge.fury.io/js/@coon-js%2Fextjs-package-loader)

This npm-package provides access to Ext.Package in an NPM environment.
It contais the original/forked package loader from [sencha](https://sencha.com) with an additional ```package.json```
to make sure it can be identified as a [npm](https://npmjs.org)-package.

## Installation

Using npm:
```bash
$ npm i --save-dev @coon-js/extjs-package-loader
```

## Usage

### Ext.Loader
When you're in the need of this package, you're most likely working in an environment where **Ext.Package** is not 
available. If you have access to the [Ext.Loader](https://docs.sencha.com/extjs/7.4.0/classic/Ext.Loader.html)-configuration, 
you can configure it with the following paths:

```javascript
Ext.Loader.setPath("Ext.Package", "./node_modules/@coon-js/extjs-package-loader/packages/package-loader/src/Package.js");
Ext.Loader.setPath("Ext.package", "./node_modules/@coon-js/extjs-package-loader/packages/package-loader/src/package");
```

### Build
The following will create a ```build```-folder inside the root-folder of this package
and place a ```package-loader.js``` and ```package-loader-debug.js``` into it:

```bash
$ npm run build 
```

Further information related to dynamic package loading can be found here: https://github.com/sencha/package-loader
# package-loader
Ext JS Dynamic Package Loader

# Requirements
This package is used by Ext JS applications and Sencha Cmd 6.5

- Install [Sencha Cmd](https://www.sencha.com/products/sencha-cmd/)
- Download [Sencha Ext JS](https://www.sencha.com/products/extjs).  We
  recommend extracting Ext JS into a `"sencha-sdks"` folder in your home directory.

## Use In Cmd Application
Simply add `package-loader` to the `'app.json'` file's `requires` array:

    "requires": [
        "package-loader"
    ]

Then build the application

    sencha app build --dev

The `package-loader` package will be automatically downloaded from Sencha's CDN.

# Manual Installation

In most cases you won't need to manually install this package. If you cannot access
the Sencha CDN as part of the app build, you can manually download the files to
your workspace.

Be sure that the `'packages/package-loader'` path is placed in the correct root of
your application or workspace.

# Build

Should you want to build the package yourself, first you will need to setup the
workspace which will need a local copy of Ext JS to build:

    $ sencha workspace install ~/sencha-sdks
    $ cd packages/package-loader
    $ sencha package build
