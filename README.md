# Typescript Project Config

### Additional Dependencies

| Package Name                                                 | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier) | Turns off all rules that are unnecessary or might conflict with Prettier. |
| [@typescript-eslint/parser](https://github.com/eslint/typescript-eslint-parser) | An ESLint-specific parser which leverages `typescript-estree` and is designed to be used as a replacement for ESLint's default parser, `espree`. |
| [eslint-plugin-react-hooks](https://www.npmjs.com/package/eslint-plugin-react-hooks) | This ESLint plugin enforces the [Rules of Hooks](https://reactjs.org/docs/hooks-rules.html). |
| [@typescript-eslint/eslint-plugin](https://github.com/typescript-eslint/typescript-eslint/tree/master/packages/eslint-plugin) | An ESLint-specific plugin which, when used in conjunction with `@typescript-eslint/parser`, allows for TypeScript-specific linting rules to run. |
| [prettier](https://github.com/prettier/prettier)             | Prettier is an opinionated code formatter.                   |
| [stylelint](https://github.com/stylelint/stylelint)          | A mighty, modern linter that helps you avoid errors and enforce conventions in your styles. |
| [stylelint-config-prettier](https://github.com/prettier/stylelint-config-prettier) | Turns off all rules that are unnecessary or might conflict with prettier. |

### Install Dependencies & Add Config Files

`yarn add -D eslint-config-airbnb eslint-config-prettier eslint-config-unicorn eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-jest eslint-plugin-react eslint-plugin-react-hooks @typescript-eslint/parser @typescript-eslint/eslint-plugin prettier stylelint stylelint-config-prettier stylelint-config-recommended stylelint-config-styled-components stylelint-processor-styled-components`

##### Create linter config files

`touch .eslintrc .prettierrc .stylelintrc`

---

### tsconfig.json

```json
{
  "compilerOptions": {
    "target": "esnext",
    "module": "esnext",
    "lib": ["dom", "es6", "es2017", "esnext"],
    "sourceMap": true,
    "outDir": "build/",
    "moduleResolution": "node",
    "declaration": false,
    "composite": false,
    "strict": true,
    "noImplicitAny": true,
    "strictNullChecks": false,
    "strictFunctionTypes": true,
    "noImplicitThis": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noImplicitReturns": true,
    "noFallthroughCasesInSwitch": true,
    "allowSyntheticDefaultImports": true,
    "esModuleInterop": true,
    "newLine": "LF",
    "experimentalDecorators": true,
    "skipLibCheck": true,
    "allowJs": false,
    "jsx": "preserve",
    "rootDir": "src",
    "forceConsistentCasingInFileNames": true,
    "suppressImplicitAnyIndexErrors": true,
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true
  },
  "include": ["src/**/*"],
  "exclude": ["node_modules", "build", "dist", "scripts"]
}
```

---

### .eslintrc

```json
{
  "extends": [
    "airbnb-base",
    "plugin:@typescript-eslint/recommended",
    "plugin:react/recommended"
  ],
  "parser": "@typescript-eslint/parser",
  "plugins": ["@typescript-eslint/eslint-plugin"],
  "env": {
    "browser": false,
    "node": true,
    "jest": true
  },
  "settings": {
    "import/resolver": {
      "typescript": {},
      "node": {
        "extensions": [".ts", ".tsx", ".js", ".jsx"]
      }
    }
  },
  "overrides": [
    {
      "files": ["src/**/*.js"],
      "rules": { "@typescript-eslint/no-var-requires": "off" }
    }
  ],
  "rules": {
    "radix": 0,
    "arrow-body-style": 0,
    "no-underscore-dangle": 0,
    "class-methods-use-this": 0,
    "no-confusing-arrow": ["warn"],
    "no-return-assign": ["warn"],
    "@typescript-eslint/camelcase": ["warn"],
    "max-len": ["warn"],
    "no-unused-vars": "off",
    "semi": [2, "always"],
    "@typescript-eslint/indent": ["error", 2],
    "@typescript-eslint/explicit-member-accessibility": "off",
    "@typescript-eslint/explicit-function-return-type": "off",
    "@typescript-eslint/no-unused-vars": ["error", { "args": "none" }],
    "import/extensions": ["off"],
    "no-param-reassign": [2, { "props": false }],
    "@typescript-eslint/no-empty-interface": 0,
    "no-nested-ternary": "warn",
    "react/display-name": "warn",
    "object-curly-newline": [
      "error",
      {
        "ObjectExpression": { "multiline": true, "minProperties": 5 },
        "ObjectPattern": { "multiline": true, "minProperties": 5 },
        "ImportDeclaration": { "multiline": true, "minProperties": 5 },
        "ExportDeclaration": { "multiline": true, "minProperties": 5 }
      }
    ],
    "@typescript-eslint/ban-ts-ignore": "off",
    "comma-dangle": "warn"
  }
}
```

---

### .prettierrc

```json
{
  "printWidth": 80,
  "tabWidth": 2,
  "useTabs": false,
  "semi": true,
  "singleQuote": true,
  "trailingComma": "es5",
  "bracketSpacing": true,
  "jsxBracketSameLine": false
}
```

---

### .stylelintrc

```json
{
  "processors": ["stylelint-processor-styled-components"],
  "extends": [
    "stylelint-config-recommended",
    "stylelint-config-styled-components",
    "stylelint-config-prettier"
  ]
}
```

---

### To-Do

- [ ]  add links and descriptions for remaining dependencies

- [ ]  add brief explanations for important/most-used linter preferences