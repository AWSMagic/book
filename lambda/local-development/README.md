---
description: >-
  Develop and Debug Lambda functions locally using AWS SAM and Visual Studio
  Code
---

# Local Development

{% hint style="success" %}
As a developer, I want to be able to develop, run and debug Lambda functions locally so that I can deliver code faster.
{% endhint %}

## Overview

In this document, we will use AWS SAM for local Lambda development using TypeScript. Our choice of IDE will be Visual Studio Code.

## High level folder structure

Eventually, we will have this folder structure;

```bash
- project-one
  - .git
  - .venv
  - .vscode
  - function-one
    - dist
    - node_modules
    - package-lock.json
    - package.json
    - src
      - event.json
      - index.ts
    - template.yaml
    - tsconfig.json
```
