# Initialize Git Repository

We have two options:

- Option A: Clone the repo to `$LAMBDADIR`, if the repo is not empty.
- Option B: Use starter-kit and push to the repo, if the repo is empty.

## Option A: Configure Manually

Assumptions:

- You have created a `codecommit` repository to keep your code.
- This repository has some files.
- You have to configure the environment manually and then check-in to the codecommit repo.


```bash
$ cd $LAMBDADIR
$ git clone https://git-codecommit.us-east-1.amazonaws.com/v1/repos/function-one .
```

## Option B: Use Starter-Kit

Assumptions:

- You have created a `codecommit` repository to keep your code.
- This repository is empty.
- You can use starter-kit and push your local folder to codecommit repo.

```bash
$ cd $LAMBDADIR
$ git init
$ git remote add origin https://git-codecommit.us-east-1.amazonaws.com/v1/repos/function-one
```

