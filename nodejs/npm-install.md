# npm install

`npm install foobar` adds the package named `foobar` as dependency to the project,  added it to `package.json` and adds the package files to `node-modules`.  

Prior to npm 5.0.0, if `--save` wasn't specified, the package was installed to `node-modules` but not added to `package.json`
