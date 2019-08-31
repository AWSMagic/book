# Install TypeScript

## Install TypeScript

We will instal TypeScript globally.

```bash
$ sudo npm install -g typescript
$ tsc --version
Version 3.4.5
$ npm install @types/node
```

## Configure Linting

Configure `tslint` for TypeScript linting. Under `$WORKSPACE` folder \(project-one\) create `tslint.json` and paste the JSON below.

{% code-tabs %}
{% code-tabs-item title="tslint.json" %}
```javascript
{
  "defaultSeverity": "error",
  "extends": [
    "tslint:recommended"
  ],
  "jsRules": {
    "no-unused-expression": true,
    "noImplicitAny": false,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noImplicitThis": true,
    "noImplicitReturns": true,
    "preserveConstEnums": true,
    "suppressImplicitAnyIndexErrors": true
  },
  "rules": {
    "quotemark": [
      true,
      "single"
    ],
    "member-access": [
      false
    ],
    "ordered-imports": [
      false
    ],
    "max-line-length": [
      true,
      150
    ],
    "member-ordering": [
      false
    ],
    "interface-name": [
      false
    ],
    "arrow-parens": false,
    "object-literal-sort-keys": false,
    "trailing-comma": [
      true,
      {
        "singleline": "never",
        "multiline": {
          "objects": "ignore",
          "arrays": "ignore",
          "functions": "never",
          "typeLiterals": "ignore"
        }
      }
    ],
    "rulesDirectory": []
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

