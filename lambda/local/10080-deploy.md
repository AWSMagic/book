# Deploy Lambda Function

### Open VSCode Terminal

Create a new terminal by pressing ``control + shift + ```.

### Activate Virtual Environment

```bash
$ source .venv/bin/activate
```

### Set Environment Variables

In the terminal screen activate the virtualenv and  set environment variables.

```bash
(.venv)$ PROJECTNAME=projectOne
(.venv)$ FUNCTIONNAME=functionOne
(.venv)$ BUCKETNAME=ozlambdabucket
(.venv)$ PROFILENAME=lambdadev
(.venv)$ STACKNAME=$FUNCTIONNAME-cfn
```

###  Configure AWS CLI Credentials

You need an IAM user in order to proceed. \([AWS document on creating IAM user](https://docs.aws.amazon.com/en_pv/IAM/latest/UserGuide/id_users_create.html)\)

```bash
(.venv)$ aws configure --profile $PROFILENAME
AWS Access Key ID [None]: AKIAQ4QLF5QD6GY8NKHW
AWS Secret Access Key [None]: T1A6BYuMGo4i84JO6bDYPcXAh+N1OvvemH0tb3Qa
Default region name [None]: us-east-1
Default output format [None]: json
```

### Configure S3 Bucket

We need an S3 bucket to store packaged lambda code. Find a bucket name that is not already taken. Below we are using `ozlambdabucket`.

```bash
(.venv)$ aws s3 mb s3://$BUCKETNAME --region us-east-1 --profile $PROFILENAME
make_bucket: ozlambdabucket
```

### Modify SAM Configuration

Change `template.yaml` to look like below, with `Outputs` section.

{% code-tabs %}
{% code-tabs-item title="template.yaml" %}
```yaml
AWSTemplateFormatVersion: '2010-09-09'
Transform: 'AWS::Serverless-2016-10-31'
Description: A starter AWS Lambda function.
Resources:
  functionOne:
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
Outputs:
  functionOneArn:
    Description: "functionOne Lambda Function ARN"
    Value: !GetAtt functionOne.Arn
  functionOneRoleArn:
    Description: "functionOne Lambda Function Role"
    Value: !GetAtt functionOneRole.Arn


```
{% endcode-tabs-item %}
{% endcode-tabs %}

### Build and Package

Be sure you are under function folder.

```bash
(venv)$ # cd $PROJECTNAME/$FUNCTIONAME
(venv)$ sam build
(venv)$ sam package --output-template packaged.yaml --s3-bucket $BUCKETNAME \
--profile $PROFILENAME
```

### Deploy

```bash
(.venv)$ sam deploy --template-file packaged.yaml --region us-east-1 \
--capabilities CAPABILITY_IAM --stack-name $STACKNAME --profile $PROFILENAME
```

You will see an output similar to this one;

```bash
Waiting for changeset to be created..
Waiting for stack create/update to complete
Successfully created/updated stack - functionOne-cfn
```

### Test Your Stack

```bash
(.venv)$ aws cloudformation describe-stacks --stack-name $STACKNAME \
--region us-east-1 --query "Stacks[].Outputs" --profile $PROFILENAME
```

You will see an output similar to this one;

```bash
[
    [
        {
            "OutputKey": "functionOneArn",
            "OutputValue": "arn:aws:lambda:us-east-1:061226742791:function:functionOne-cfn-functionOne-37WRWIL2LYZ8",
            "Description": "functionOne Lambda Function ARN"
        },
        {
            "OutputKey": "functionOneRoleArn",
            "OutputValue": "arn:aws:iam::061226742791:role/functionOne-cfn-functionOneRole-12J5NO0E1SLTJ",
            "Description": "functionOne Lambda Function Role"
        }
    ]
]
```

Get the Lambda Function ARN from the output of the previous command and invoke it using AWS CLI.

```bash
(.venv)$ aws lambda invoke \
--function-name arn:aws:lambda:us-east-1:061226742791:function:functionOne-cfn-functionOne-37WRWIL2LYZ8 \
--payload file://src/event.json response.json 

{
    "StatusCode": 200,
    "ExecutedVersion": "$LATEST"
}
(.venv)$ cat response.json 
"{\n  \"key1\": \"value1\",\n  \"key2\": \"value2\",\n  \"key3\": \"value3\"\n}"
```



