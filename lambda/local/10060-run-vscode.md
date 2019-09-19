# Run Lambda in VSCode

## Open The Project

Open Visual Studio Code and open `project-one` folder.

![](../../.gitbook/assets/vscode1001.png)

## "Transpile" TypeScript

Press `Shift + Command + B` and select `npm: build - function-one`

![](../../.gitbook/assets/vscode1002.png)

This will run `tsc` to transpile all the typescript files under the folder.

## Run the Lambda Function

Press `shift + command + P` and select `Tasks: Run Task` and then select`npm: sam - function-one`

![](../../.gitbook/assets/vscode1003.png)

![](../../.gitbook/assets/vscode1004.png)

![](../../.gitbook/assets/vscode1005.png)

Final screenshot shows that we are able to run the lambda function from VSCode.

