# Configure Visual Studio Code

Create `.vscode/launch.json` file with the code below

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug Lambda",
      "type": "node",
      "request": "attach",
      "sourceMaps": true,
      "address": "localhost",
      "port": 9999,
      "localRoot": "${workspaceRoot}/",
      "remoteRoot": "/var/task",
      "protocol": "inspector",
      "stopOnEntry": false,
      "outFiles": [
        "${workspaceFolder}/dist/**/*.js"
      ]
    }
  ]
}
```

Create `.vscode/tasks.json` file with the code below

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "type": "npm",
      "script": "build",
      "problemMatcher": []
    },
    {
      "type": "npm",
      "script": "sam",
      "problemMatcher": []
    }
  ]
}
```

Create `.vscode/settings.json` with the code below

```json
{
  "files.autoSave": "afterDelay",
  "files.autoSaveDelay": 10000,
  "editor.tabSize": 2,
  "editor.detectIndentation": false,
  "files.exclude": {
    "**/*.js": true,
    "**/*.js.map": true,
    "**/node_modules": true,
    "dist": true
  },
  "explorer.autoReveal": true
}
```