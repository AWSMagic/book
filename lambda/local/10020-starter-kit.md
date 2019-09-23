# Use Starter Kit

We will use the starter kit to configure our environment. This has an `install.sh` script which installs various packages and copies several configuration files automatically.

## Clone Starter Kit

Switch to a folder where you want to clone the starter kit to. Below we clone to a folder named `src` under home folder.

```bash
$ cd ~/src
$ git clone https://github.com/AWSMagic/lambda-typescript-vscode-starter-kit.git
$ cd lambda-typescript-vscode-starter-kit
```

## About Installer Script

Installer `install.sh` accepts three attributes.

```text
-r: root folder
-p: project name
-f: function name
```

Sample Usage:

```bash
$ ./intsall.sh -r ~/src -p projectOne -f functionOne
```

The command above is going to create `projectOne` folder under `~/src` folder. Then it will create `functionOne` folder under `~/src/projectOne` folder. Root folder has to exist in order to run the `install.sh` script. Other two folders are going to be created by the `install.sh` script.

## Run Installer

```bash
$ cd lambda-typescript-vscode-starter-kit/
$ ./intsall.sh -r ~/src -p projectOne -f functionOne

Captured these as requirements:
root folder: /Users/oz/src/
project name: projectOne
function name: functionOne
workspace folder: /Users/oz/src/projectOne
configuration folder (pwd): /Users/oz/src/lambda-typescript-vscode-starter-kit

Do you want to continue? (y/n) y
```

If this is the first time you are running this script it will download the docker image required to run lambda function locally. This may take a while to complete.

You will see the output below.

```bash
2019/08/31 01:26:48 Successfully parsed template.yaml
2019/08/31 01:26:48 Connected to Docker 1.40
2019/08/31 01:26:48 Fetching lambci/lambda:nodejs8.10 image for nodejs8.10 runtime...
nodejs8.10: Pulling from lambci/lambda
Digest: sha256:bc59e063662af0e2ad2a634e0ca23e10a31ea1db12212da80aebf2ff2d9ee323
Status: Image is up to date for lambci/lambda:nodejs8.10
2019/08/31 01:26:49 Invoking dist/index.handler (nodejs8.10)
2019/08/31 01:26:49 Mounting /Users/oz/src/projectOne/functionOne as /var/task:ro inside runtime container
START RequestId: 7b5f4577-2b5f-1dfd-9dad-74e5db26bcbe Version: $LATEST
2019-08-31T05:26:50.034Z    7b5f4577-2b5f-1dfd-9dad-74e5db26bcbe    value1 = value1
2019-08-31T05:26:50.035Z    7b5f4577-2b5f-1dfd-9dad-74e5db26bcbe    value2 = value2
2019-08-31T05:26:50.035Z    7b5f4577-2b5f-1dfd-9dad-74e5db26bcbe    value3 = value3
2019-08-31T05:26:50.035Z    7b5f4577-2b5f-1dfd-9dad-74e5db26bcbe    DEV
END RequestId: 7b5f4577-2b5f-1dfd-9dad-74e5db26bcbe
REPORT RequestId: 7b5f4577-2b5f-1dfd-9dad-74e5db26bcbe    Duration: 5.49 ms    Billed Duration: 100 ms    Memory Size: 128 MB    Max Memory Used: 30 MB    

"{\n  \"key1\": \"value1\",\n  \"key2\": \"value2\",\n  \"key3\": \"value3\"\n}"
```

As seen above `install.sh` ran the `functionOne` lambda function locally to test the installation. If you don't see the `"{\n \"key1\": \"value1\",\n \"key2\": \"value2\",\n \"key3\": \"value3\"\n}"` at the end of the logs, you might have a problem with the installer.

