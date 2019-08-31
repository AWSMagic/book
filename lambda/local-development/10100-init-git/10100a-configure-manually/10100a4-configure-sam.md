# Configure SAM

## Create SAM Template

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

## Test Current Configuration

Switch to `function-one` folder and run `npm run sam` to run the lambda function in a container. If you are running this command for the first time, it will download the container image and will take a while to download.

```bash
$ cd $LAMBDADIR
$ npm run sam

> function-one@1.0.0 sam /Users/oz/project-one/function-one
> node_modules/aws-sam-local/node_modules/.bin/sam local invoke -e src/event.json function-one

2019/08/30 22:18:11 Successfully parsed template.yaml
2019/08/30 22:18:11 Connected to Docker 1.40
2019/08/30 22:18:11 Fetching lambci/lambda:nodejs8.10 image for nodejs8.10 runtime...
nodejs8.10: Pulling from lambci/lambda
Digest: sha256:bc59e063662af0e2ad2a634e0ca23e10a31ea1db12212da80aebf2ff2d9ee323
Status: Image is up to date for lambci/lambda:nodejs8.10
2019/08/30 22:18:12 Invoking dist/index.handler (nodejs8.10)
2019/08/30 22:18:12 Mounting /Users/oz/project-one/function-one as /var/task:ro inside runtime container
START RequestId: 327f5e85-88eb-10df-fc47-98b3331c4d80 Version: $LATEST
2019-08-31T02:18:13.121Z        327f5e85-88eb-10df-fc47-98b3331c4d80    value1 = value1
2019-08-31T02:18:13.122Z        327f5e85-88eb-10df-fc47-98b3331c4d80    value2 = value2
2019-08-31T02:18:13.122Z        327f5e85-88eb-10df-fc47-98b3331c4d80    value3 = value3
2019-08-31T02:18:13.122Z        327f5e85-88eb-10df-fc47-98b3331c4d80    DEV
END RequestId: 327f5e85-88eb-10df-fc47-98b3331c4d80
REPORT RequestId: 327f5e85-88eb-10df-fc47-98b3331c4d80  Duration: 7.04 ms       Billed Duration: 100 ms Memory Size: 128 MB     Max Memory Used: 30 MB

"{\n  \"key1\": \"value1\",\n  \"key2\": \"value2\",\n  \"key3\": \"value3\"\n}"
```

