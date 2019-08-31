# Use Starter-Kit

## Clone Starter Kit

```bash
git clone https://github.com/cloudwayio/lambda-typescript-vscode-starter-kit.git
```

## Edit Installer Configuration

```bash
$ cd lambda-typescript-vscode-starter-kit 
```

Change these below in `install.sh` as you need.

{% code-tabs %}
{% code-tabs-item title="install.sh" %}
```
ROOTFOLDER=~/src
PROJECT=project-six
FUNCTIONNAME=function-one
...
...# truncated
...
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Run Installer

```bash
$ ./install.sh
```