# Create a Node Project.

```bash
$ cd $LAMBDADIR
$ npm init -y
```

You will see an output similar to below.

```json
Wrote to /Users/ozakan/src/temp/workspace/function-one/package.json:

{
  "name": "function-one",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "dependencies": {
    "aws-sam-local": "^0.2.11"
  },
  "devDependencies": {},
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}

```

Replace the content of `package.json` so it will look like below;

```json
{
  "name": "function-one",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "tsc",
    "sam": "node_modules/aws-sam-local/node_modules/.bin/sam local invoke -e src/event.json function-one",
    "debug": "node_modules/aws-sam-local/node_modules/.bin/sam local invoke -e src/event.json --debug-port 9999 function-one"
  },
  "repository": {
    "type": "git",
    "url": "https://git-codecommit.us-east-1.amazonaws.com/v1/repos/workspace"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "@types/node": "^12.7.3",
    "aws-sam-local": "^0.2.11"
  }
}
```
