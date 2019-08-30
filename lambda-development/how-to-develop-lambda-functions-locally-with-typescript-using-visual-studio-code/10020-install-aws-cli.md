# Install AWS CLI

Change to your  `$WORKSPACE` folder.

```
$ cd $WORKSPACE
```

Install Python 3 if not installed
[https://www.python.org/downloads/](https://www.python.org/downloads/)

Create virtual environment.

```
$ python3 -m venv .venv
$ source .venv/bin/activate
```

Update pip.

```
$ pip install --upgrade pip
```

Install AWS CLI

```
$ pip install --upgrade awscli
$ aws --version
aws-cli/1.16.229 Python/3.7.2 Darwin/18.7.0 botocore/1.12.219
```

>Note: `aws-cli` version might be different.