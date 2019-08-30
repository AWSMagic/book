# Initialize Git Repository

{% hint style="info" %}
TODO: configure credential helper and document here
{% hint %}

- Option 1: Clone the repo to `$LAMDADIR`, if the repo is not empty.
- Option 2: Initialize git and push to the repo, if the repo is empty.

## Option 1: Clone and Configure Manually

Assumptions:

- You have created a `codecommit` repository to keep your code
- This repository has some files, so you want to configure the environment manually.


```bash
$ cd $LAMDADIR
$ git clone https://git-codecommit.us-east-1.amazonaws.com/v1/repos/function-one .
```

## Option 2: Use starter-kit and push to your origin

```bash
$ cd $LAMDADIR
$ git init
$ git remote add origin https://git-codecommit.us-east-1.amazonaws.com/v1/repos/function-one
```

