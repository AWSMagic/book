# Create SAM Template

Make sure you are in `$LAMBDADIR` folder.

```bash
$ cd $LAMBDADIR
```

Create `template.yaml` file under `src` folder with the content below.

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Transform: 'AWS::Serverless-2016-10-31'
Description: A starter AWS Lambda function.
Parameters: 
    IdentityNameParameter: 
      Type: String
Resources:
  function-one:
    Type: 'AWS::Serverless::Function'
    Properties:
      Handler: dist/index.handler
      Runtime: nodejs8.10
      CodeUri: .
      Description: A starter AWS Lambda function.
      MemorySize: 128
      Timeout: 3
      Environment:
        Variables:
          Stage: DEV
```