# [vite](https://vitejs.dev/) + [React](https://reactjs.org/) + [TypeScript](https://www.typescriptlang.org/) Starter

This setup includes:
* [vite](https://vitejs.dev/)
* [eslint](https://eslint.org/), [typescript-eslint](https://typescript-eslint.io/), [eslint-airbnb-config](https://github.com/airbnb/javascript), [prettier](https://prettier.io/)
* [vitest](https://vitest.dev/), [jsdom](https://github.com/jsdom/jsdom), [@testing-library](https://testing-library.com/)
* [react-router v6](https://reactrouter.com/en/main)

## Vite

```bash
npm create vite@latest
```

## Eslint

install

 ```bash
 npm i -D eslint
 ```

init, select check syntax and find problems

```bash
npx eslint --init
```

### eslint-config-airbnb

- [eslint-config-airbnb - npm](https://www.npmjs.com/package/eslint-config-airbnb)

```bash
npx install-peerdeps --dev eslint-config-airbnb
```

Add `"extends": "airbnb"` to your `.eslintrc`

**eslint-config-airbnb/hooks**

This entry point enables the linting rules for React hooks (requires v16.8+). To use, add `"extends": ["airbnb", "airbnb/hooks"]` to your `.eslintrc`.

### eslint-config-airbnb-typescript

- [eslint-config-airbnb-typescript - npm](https://www.npmjs.com/package/eslint-config-airbnb-typescript)

```bash
npm install eslint-config-airbnb-typescript -D
```

**Configure ESLint**

```bash
extends: [
  'airbnb',
  'airbnb-typescript'
]
```

the final finished file

```
extends: [
    'airbnb', 
    'airbnb-typescript',
    'airbnb/hooks',
    'plugin:react/recommended',
    'plugin:@typescript-eslint/recommended',
    'plugin:prettier/recommended',
  ],
```

**Configure the ESLint TypeScript parser**

This config requires knowledge of your TypeScript config.

In your ESLint config, set [parserOptions.project](https://github.com/typescript-eslint/typescript-eslint/tree/master/packages/parser#parseroptionsproject) to the path of your `tsconfig.json`.

For example:

```bash
{
  extends: ['airbnb', 'airbnb-typescript'],
+ parserOptions: {
+   project: './tsconfig.json'
+ }
}
```

### configure tsconfig.json

add eslintrc.cjs 

```bash
"include": [
    ".eslintrc.cjs",
    "src"
  ],
```

the final file

```bash
"include": [
    "vite.config.ts",
    ".eslintrc.cjs",
    "src"
  ],
```

## Prettier

- [eslint-config-prettier - npm](https://www.npmjs.com/package/eslint-config-prettier)

- [eslint-plugin-prettier - npm](https://www.npmjs.com/package/eslint-plugin-prettier)

```
npm install -D prettier eslint-config-prettier eslint-plugin-prettier
```

create .prettierrc.cjs

```js
module.exports = {
  trailingComma: "es5",
  tabWidth: 2,
  semi: true,
  singleQuote: true,
};
```

Then, in your `.eslintrc.json`:

```bash
{
  "plugins": ["prettier"],
}
```

Then you need to add `plugin:prettier/recommended` as the *last* extension in your `.eslintrc.json`:

```
{
  "extends": ["plugin:prettier/recommended"]
}
```



## References

* https://markus.oberlehner.net/blog/using-testing-library-jest-dom-with-vitest/
* https://testing-library.com/docs/queries/about#priority
* https://kentcdodds.com/blog/common-mistakes-with-react-testing-library