# api documentation for  [git-release-notes (v1.0.0)](https://github.com/ariatemplates/git-release-notes)  [![npm package](https://img.shields.io/npm/v/npmdoc-git-release-notes.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-git-release-notes) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-git-release-notes.svg)](https://travis-ci.org/npmdoc/node-npmdoc-git-release-notes)
#### Generate beautiful release notes from a git log.

[![NPM](https://nodei.co/npm/git-release-notes.png?downloads=true)](https://www.npmjs.com/package/git-release-notes)

[![apidoc](https://npmdoc.github.io/node-npmdoc-git-release-notes/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-git-release-notes_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-git-release-notes/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-git-release-notes/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-git-release-notes/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "ariatemplates",
        "email": "contact@ariatemplates.com",
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
        "email": "fabio@ariatemplates.com",
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
            "name": "ariatemplates",
            "email": "admin@ariatemplates.com"
        },
        {
            "name": "piuccio",
            "email": "piuccio@gmail.com"
        }
    ],
    "name": "git-release-notes",
    "optionalDependencies": {},
    "preferGlobal": true,
    "readme": "ERROR: No README data found!",
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



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module git-release-notes](#apidoc.module.git-release-notes)
1.  object <span class="apidocSignatureSpan">git-release-notes.</span>git

#### [module git-release-notes.git](#apidoc.module.git-release-notes.git)
1.  [function <span class="apidocSignatureSpan">git-release-notes.git.</span>log (options, callback)](#apidoc.element.git-release-notes.git.log)



# <a name="apidoc.module.git-release-notes"></a>[module git-release-notes](#apidoc.module.git-release-notes)



# <a name="apidoc.module.git-release-notes.git"></a>[module git-release-notes.git](#apidoc.module.git-release-notes.git)

#### <a name="apidoc.element.git-release-notes.git.log"></a>[function <span class="apidocSignatureSpan">git-release-notes.git.</span>log (options, callback)](#apidoc.element.git-release-notes.git.log)
- description and source-code
```javascript
log = function (options, callback) {
	var spawn = require("child_process").spawn;
	var gitArgs = ["log", "--no-color", "--no-merges", "--branches=" + options.branch, "--format=" + formatOptions, options.range];
	debug("Spawning git with args %o", gitArgs);
	var gitLog = spawn("git", gitArgs, {
		cwd : options.cwd,
		stdio : ["ignore", "pipe", process.stderr]
	});

	var allCommits = "";
	gitLog.stdout.on("data", function (data) {
		allCommits += data;
	});

	gitLog.on("exit", function (code) {
		debug("Git command exited with code '%d'", code);
		if (code === 0) {
			allCommits = normalizeNewlines(allCommits).trim();

			if (allCommits) {
				// Build the list of commits from git log
				var commits = processCommits(allCommits, options);
				callback(commits);
			} else {
				callback([]);
			}
		}
	});
}
```
- example usage
```shell
...
	if (err) {
		require("optimist").showHelp();
		console.error("\nUnable to locate template file " + argv._[1]);
		process.exit(5);
	} else {
		getOptions(function (options) {
			debug("Running git log in '%s' on branch '%s' with range '%s'", options.p, options.b, argv._[0]);
			git.log({
				branch : options.b,
				range : argv._[0],
				title : new RegExp(options.t),
				meaning : Array.isArray(options.m) ? options.m : [options.m],
				cwd : options.p
			}, function (commits) {
				debug("Got %d commits", commits.length);
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
