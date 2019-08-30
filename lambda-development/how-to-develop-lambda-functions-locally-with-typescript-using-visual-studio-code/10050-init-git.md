# Initialize Git

TODO: configure credential helper and document here

Option 1: Clone the repo to `$LAMDADIR`, if the repo is not empty.
Option 2: Initialize git and push to the repo, if the repo is empty.

## Option 1: Clone

```bash
$ cd $LAMDADIR
$ git clone https://git-codecommit.us-east-1.amazonaws.com/v1/repos/function-one .
```

## Option 2: Init repo and add origin

```bash
$ cd $LAMDADIR
$ git init
$ git remote add origin https://git-codecommit.us-east-1.amazonaws.com/v1/repos/function-one
```

