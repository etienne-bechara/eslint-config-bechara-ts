# Bechara - TypeScript ESLint Configuration

This package offers a custom set of rules to be used across Node.js projects written in TypeScript.


## Quick Start

1\. Install ESLint and this rule package in your project:

```
npm i -D eslint @bechara/eslint-config-bechara-ts
```

2\. Create a `.eslintrc.js` file at the root of your workspace that extends the recently installed package:

```js
module.exports =  {
  extends: [ 
    '@bechara/eslint-config-bechara-ts'
  ]
}
```

3\. Add a pre-commit hook to fix and validate all staged files, it can be automatically created with:
```
npx mrm lint-staged
```


## Rules

### IDE Integration

To increase productivity, it is highly recommended to install an ESLint extension for your IDE and enable auto-fixing.

Please refer to this guide that includes all the most popular coding tools:

[Even faster code formatting using ESLint](https://medium.com/@netczuk/even-faster-code-formatting-using-eslint-22b80d061461)


### Starting Definition

Our rule set uses as entry point these following predefined sets:

- [ESLint Recommended](https://eslint.org/docs/rules/)
- [ESLint TypeScript Recommended](https://github.com/typescript-eslint/typescript-eslint/tree/master/packages/eslint-plugin)
- [Import Errors](https://github.com/benmosher/eslint-plugin-import/blob/master/config/errors.js)
- [Import Warnings](https://github.com/benmosher/eslint-plugin-import/blob/master/config/warnings.js)
- [Jest Recommended](https://github.com/jest-community/eslint-plugin-jest#rules)
- [Unicorn Recommended](https://github.com/sindresorhus/eslint-plugin-unicorn/blob/master/index.js)

Further customizations are defined in the property `rules` of `index.js`. These include adding, modifying and disabling existing ones.

Please refer to comments inside `index.js` for clarifications.


### Overwriting

To lower or increase severity of a rule, as well as disable it, overwrite its definition in your `.eslintrc.js` e.g.:

```js
module.exports =  {
  extends: [ 
    '@bechara/eslint-config-bechara-ts'
  ],
  rules: {
    'eqeqeq': [ 'warn' ], // Originally 'error'
    'no-console': [ 'off' ], // Originally 'warn'
  }
}
```


## Troubleshooting

### "Parsing error: Invalid ecmaVersion"

To use the most up-to-date features (currently ecma 2020), you must use ESLint `>= 7.8.0`.

In case you are not able to do so, overwrite the `parserOptions` in your `.eslintrc.js` with a previous version, e.g.:

```js
module.exports =  {
  parserOptions: {
    ecmaVersion: 6,
  },
  extends: [ 
    '@bechara/eslint-config-bechara-ts'
  ]
}
```
