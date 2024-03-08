# Sandbox for NPM install

This repository shows how to set up NPM packages so that these two things
are both true:

1) The names and versions of dependency packages are recorded in `package.json`
as a set of instructions for the `npm install` command.

2) After installation, the source code of installed packages is not picked up
by version control.

This is done by adding `node_modules`, the name of the folder where the
dependency source code lives, to the [`.gitignore` file](https://github.com/Birkbeck2/sandbox-npm-install/blob/main/.gitignore).

To see the results, compare the outputs below before and after installation:

```shell
$ git status
nothing to commit, working tree clean
$ ls
app.js  package.json  package-lock.json  README.md
$ npm install
added 1 package, and audited 2 packages in 384ms
$ ls
app.js  node_modules  package.json  package-lock.json  README.md
$ git status
nothing to commit, working tree clean
```
