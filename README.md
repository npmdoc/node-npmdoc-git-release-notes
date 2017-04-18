# npmdoc-git-release-notes

#### api documentation for  [git-release-notes (v1.0.0)](https://github.com/ariatemplates/git-release-notes)  [![npm package](https://img.shields.io/npm/v/npmdoc-git-release-notes.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-git-release-notes) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-git-release-notes.svg)](https://travis-ci.org/npmdoc/node-npmdoc-git-release-notes)

#### Generate beautiful release notes from a git log.

[![NPM](https://nodei.co/npm/git-release-notes.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/git-release-notes)

- [https://npmdoc.github.io/node-npmdoc-git-release-notes/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-git-release-notes/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-git-release-notes/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-git-release-notes/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-git-release-notes/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-git-release-notes/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "ariatemplates",
        "url": "http://github.com/ariatemplates"
    },
    "bin": {
        "git-release-notes": "./index.js"
    },
    "bugs": {
        "url": "https://github.com/ariatemplates/git-release-notes/issues"
    },
    "contributors": {
        "name": "Fabio Crisci",
        "url": "https://github.com/piuccio"
    },
    "dependencies": {
        "debug": "^2.6.0",
        "ejs": "^2.5.5",
        "optimist": "^0.6.1"
    },
    "description": "Generate beautiful release notes from a git log.",
    "devDependencies": {
        "eslint": "^3.14.0"
    },
    "directories": {},
    "dist": {
        "shasum": "39a742b076dad32280594fbc0cea41d77651267c",
        "tarball": "https://registry.npmjs.org/git-release-notes/-/git-release-notes-1.0.0.tgz"
    },
    "gitHead": "f6cf9af177db54a8e788d1b26a3fa0cf66599d26",
    "homepage": "https://github.com/ariatemplates/git-release-notes",
    "keywords": [
        "git",
        "log",
        "release notes",
        "compare",
        "version"
    ],
    "maintainers": [
        {
            "name": "ariatemplates"
        },
        {
            "name": "piuccio"
        }
    ],
    "name": "git-release-notes",
    "optionalDependencies": {},
    "preferGlobal": true,
    "repository": {
        "type": "git",
        "url": "git+https://github.com/ariatemplates/git-release-notes.git"
    },
    "scripts": {
        "lint": "eslint index.js lib",
        "posttest": "npm run lint"
    },
    "version": "1.0.0"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
