- mkdir 'project'
- cd 'project'
- npm init
- code .
- mkdir src
- mkdir bin
- touch src/cli.js
- touch bin/h-cli

- update cli.js with following:
```
export function cli(args){
    console.log(args);
}
```

- update h-cli with following:
```
#!/usr/bin/env node

require = require('esm')(module /*, options */);
require('../src/cli').cli(process.argv)
```

- npm install esm

- update package.json similiar to following: 
```
{
  "name": "@caginbektas/h-cli",
  "version": "1.0.0",
  "description": "My first CLI to learn it",
  "main": "src/index.js",
  "bin": {
      "@caginbektas/h-cli": "bin/h-cli",
      "h-cli": "bin/h-cli"
  },
  "publishConfig": {
    "access": "public"
  },
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [
    "cli",
    "h-cli"
  ],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "esm": "^3.2.25"
  }
}
```

- npm link

then finally our first CLI try:
- h-cli --test should give you an output like, 
```
[
  '/usr/local/Cellar/node/15.2.1/bin/node',
  '/usr/local/bin/h-cli',
  '--test'
]
```