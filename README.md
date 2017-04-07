# api documentation for  [lodash-deep (v2.0.0)](https://github.com/marklagendijk/lodash-deep)  [![npm package](https://img.shields.io/npm/v/npmdoc-lodash-deep.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-lodash-deep) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-lodash-deep.svg)](https://travis-ci.org/npmdoc/node-npmdoc-lodash-deep)
#### Lodash mixins for (deep) object accessing / manipulation.

[![NPM](https://nodei.co/npm/lodash-deep.png?downloads=true)](https://www.npmjs.com/package/lodash-deep)

[![apidoc](https://npmdoc.github.io/node-npmdoc-lodash-deep/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-lodash-deep_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-lodash-deep/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-lodash-deep/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-lodash-deep/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Mark Lagendijk",
        "email": "mark@lagendijk.info"
    },
    "bugs": {
        "url": "https://github.com/marklagendijk/lodash-deep/issues"
    },
    "dependencies": {
        "lodash": ">=3.7.0"
    },
    "description": "Lodash mixins for (deep) object accessing / manipulation.",
    "devDependencies": {
        "gulp": "~3.8.8",
        "gulp-jasmine": "^2.3.0",
        "gulp-rename": "~1.2.0",
        "gulp-uglify": "~1.0.1",
        "karma": "0.13.21",
        "karma-chrome-launcher": "0.2.2",
        "karma-jasmine": "0.3.7",
        "karma-sauce-launcher": "0.3.1"
    },
    "directories": {
        "test": "test"
    },
    "dist": {
        "shasum": "ca958f5bcdb3d68d3ec37acdf1c58c1ccbd8865c",
        "tarball": "https://registry.npmjs.org/lodash-deep/-/lodash-deep-2.0.0.tgz"
    },
    "engines": {
        "node": ">=0.8.0",
        "npm": ">=1.2.10"
    },
    "gitHead": "b15a417549fea7c8c05289ffca0e1cda728e4bea",
    "homepage": "https://github.com/marklagendijk/lodash-deep",
    "keywords": [
        "lodash",
        "mixin",
        "mixins",
        "deep",
        "object",
        "walking"
    ],
    "license": "MIT",
    "main": "lodash-deep.js",
    "maintainers": [
        {
            "name": "marklagendijk",
            "email": "mark@lagendijk.info"
        }
    ],
    "name": "lodash-deep",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/marklagendijk/lodash-deep.git"
    },
    "scripts": {
        "test": "gulp test"
    },
    "version": "2.0.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module lodash-deep](#apidoc.module.lodash-deep)
1.  [function <span class="apidocSignatureSpan">lodash-deep.</span>deepMapValues (object, callback, propertyPath)](#apidoc.element.lodash-deep.deepMapValues)



# <a name="apidoc.module.lodash-deep"></a>[module lodash-deep](#apidoc.module.lodash-deep)

#### <a name="apidoc.element.lodash-deep.deepMapValues"></a>[function <span class="apidocSignatureSpan">lodash-deep.</span>deepMapValues (object, callback, propertyPath)](#apidoc.element.lodash-deep.deepMapValues)
- description and source-code
```javascript
deepMapValues = function (object, callback, propertyPath){
    propertyPath = propertyPath || '';
    if(_.isArray(object)){
        return _.map(object, deepMapValuesIteratee);
    }
    else if(_.isObject(object) && !_.isDate(object) && !_.isRegExp(object) && !_.isFunction(object)){
        return _.extend({}, object, _.mapValues(object, deepMapValuesIteratee));
    }
    else{
        return callback(object, propertyPath);
    }

    function deepMapValuesIteratee(value, key){
        var valuePath = propertyPath ? propertyPath + '.' + key: key;
        return _.deepMapValues(value, callback, valuePath);
    }
}
```
- example usage
```shell
...
    _.mixin(require("lodash-deep"));
    '''

## Docs
The following mixins are included in 'lodash-deep':
- [_.deepMapValues](#_deepmapvaluesobject-propertypath)

### _.deepMapValues(object, propertyPath)
Maps all values in an object tree and returns a new object with the same structure as the original.

#### object
Type: 'Object'

The root object of the object tree.
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
