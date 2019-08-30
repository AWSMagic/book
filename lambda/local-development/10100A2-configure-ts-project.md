# Configure TypeScript Project

Create typescript config file.

```bash
tsc --init
```

The command above will create the `tsconfig.json` file with all the available options. 

Change `tsconfig.json` to look like this below.

```json
{
  "compilerOptions": {
    "target": "es2017",
    "module": "commonjs",
    "sourceMap": true,
    "outDir": "./dist",
    "strict": true,
    "typeRoots": [
      "node_modules/@types"
    ],
    "types": [
      "node"
    ],
    "esModuleInterop": true
  }
}
```

Create `src` folder and switch to it.

```bash
$ cd $LAMBDADIR
$ mkdir src
$ cd src

```
