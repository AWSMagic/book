# Install AWS CLI

Change to your `$WORKSPACE` folder.

```bash
$ cd $WORKSPACE
```

Install Python 3 if not installed [https://www.python.org/downloads/](https://www.python.org/downloads/)

Create virtual environment.

```bash
$ python3 -m venv .venv
$ source .venv/bin/activate
```

Update pip.

```bash
$ pip install --upgrade pip
```

Install AWS CLI

```bash
$ pip install --upgrade awscli
$ aws --version
aws-cli/1.16.229 Python/3.7.2 Darwin/18.7.0 botocore/1.12.219
```

{% hint style="info" %}
`aws-cli`version might be different depending on when you install the cli.
{% endhint %}

