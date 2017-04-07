# api documentation for  [cfenv (v1.0.4)](https://github.com/cloudfoundry-community/node-cfenv)  [![npm package](https://img.shields.io/npm/v/npmdoc-cfenv.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-cfenv) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-cfenv.svg)](https://travis-ci.org/npmdoc/node-npmdoc-cfenv)
#### easy access to your Cloud Foundry application environment

[![NPM](https://nodei.co/npm/cfenv.png?downloads=true)](https://www.npmjs.com/package/cfenv)

[![apidoc](https://npmdoc.github.io/node-npmdoc-cfenv/build/screenCapture.buildNpmdoc.browser.%2Fhome%2Ftravis%2Fbuild%2Fnpmdoc%2Fnode-npmdoc-cfenv%2Ftmp%2Fbuild%2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-cfenv/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-cfenv/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-cfenv/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "pmuellr"
    },
    "bugs": {
        "url": "https://github.com/cloudfoundry-community/node-cfenv/issues"
    },
    "dependencies": {
        "js-yaml": "3.7.x",
        "ports": "1.1.x",
        "underscore": "1.8.x"
    },
    "description": "easy access to your Cloud Foundry application environment",
    "devDependencies": {
        "coffee-script": "1.12.x",
        "expect.js": "0.3.x",
        "mocha": "3.2.x"
    },
    "directories": {},
    "dist": {
        "shasum": "b97a1eebde255eced8367a0f4afbc2f85438e0b4",
        "tarball": "https://registry.npmjs.org/cfenv/-/cfenv-1.0.4.tgz"
    },
    "gitHead": "4c29ce1d1dbb65f89abe33b5325201dd2b8eb7c5",
    "homepage": "https://github.com/cloudfoundry-community/node-cfenv",
    "license": "Apache-2.0",
    "main": "./lib/cfenv",
    "maintainers": [
        {
            "name": "pmuellr",
            "email": "pmuellr@apache.org"
        },
        {
            "name": "srl",
            "email": "srl@icu-project.org"
        }
    ],
    "name": "cfenv",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/cloudfoundry-community/node-cfenv.git"
    },
    "scripts": {
        "start": "node server.js"
    },
    "version": "1.0.4"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module cfenv](#apidoc.module.cfenv)
1.  [function <span class="apidocSignatureSpan">cfenv.</span>getAppEnv (options)](#apidoc.element.cfenv.getAppEnv)
1.  object <span class="apidocSignatureSpan">cfenv.</span>server

#### [module cfenv.server](#apidoc.module.cfenv.server)
1.  [function <span class="apidocSignatureSpan">cfenv.server.</span>main ()](#apidoc.element.cfenv.server.main)



# <a name="apidoc.module.cfenv"></a>[module cfenv](#apidoc.module.cfenv)

#### <a name="apidoc.element.cfenv.getAppEnv"></a>[function <span class="apidocSignatureSpan">cfenv.</span>getAppEnv (options)](#apidoc.element.cfenv.getAppEnv)
- description and source-code
```javascript
getAppEnv = function (options) {
  if (options == null) {
    options = {};
  }
  return new AppEnv(options);
}
```
- example usage
```shell
...


quick start
================================================================================

var cfenv = require("cfenv")

var appEnv = cfenv.getAppEnv()
...
// start the server on the given port and binding host, and print
// url to server when it starts

server.listen(appEnv.port, appEnv.bind, function() {
    console.log("server starting on " + appEnv.url)
})
...
```



# <a name="apidoc.module.cfenv.server"></a>[module cfenv.server](#apidoc.module.cfenv.server)

#### <a name="apidoc.element.cfenv.server.main"></a>[function <span class="apidocSignatureSpan">cfenv.server.</span>main ()](#apidoc.element.cfenv.server.main)
- description and source-code
```javascript
main = function () {
  var appEnv, dump, server;
  appEnv = cfenv.getAppEnv();
  dump = generateDump(appEnv);
  server = http.createServer();
  server.on("request", function(request, response) {
    response.writeHead(200, {
      "Content-Type": "text/plain"
    });
    return response.end(dump);
  });
  return server.listen(appEnv.port, appEnv.bind, function() {
    return console.log("server starting on " + appEnv.url);
  });
}
```
- example usage
```shell
...
  };

  JL = function(object) {
    return JSON.stringify(object, null, 4);
  };

  if (require.main === module) {
    exports.main();
  }

}).call(this);
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
