# Typescript Project Config

### Additional Dependencies

| Package Name                          | Description   |
| ------------------------------------- | ------------- |
| [tslint](https://github.com/palantir/tslint) | An extensible linter for the TypeScript language. |
| [tslint-config-airbnb](https://github.com/progre/tslint-config-airbnb) | A TSLint config for Airbnb JavaScript Style. |
| [tslint-config-prettier](https://github.com/prettier/tslint-config-prettier) | Use tslint with prettier without any conflict. |
| [tslint-plugin-prettier](https://github.com/prettier/tslint-plugin-prettier) | Runs Prettier as a TSLint rule and reports differences as individual TSLint issues. |
| [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier) | Turns off all rules that are unnecessary or might conflict with Prettier. |
| [@typescript-eslint/parser](https://github.com/eslint/typescript-eslint-parser) | An ESLint-specific parser which leverages `typescript-estree` and is designed to be used as a replacement for ESLint's default parser, `espree`. |
| [eslint-plugin-react-hooks](https://www.npmjs.com/package/eslint-plugin-react-hooks) | This ESLint plugin enforces the [Rules of Hooks](https://reactjs.org/docs/hooks-rules.html). |
| [@typescript-eslint/eslint-plugin](https://github.com/typescript-eslint/typescript-eslint/tree/master/packages/eslint-plugin) | An ESLint-specific plugin which, when used in conjunction with `@typescript-eslint/parser`, allows for TypeScript-specific linting rules to run. |
| [prettier](https://github.com/prettier/prettier) | Prettier is an opinionated code formatter. |
| [stylelint](https://github.com/stylelint/stylelint) | A mighty, modern linter that helps you avoid errors and enforce conventions in your styles. |
| [stylelint-config-prettier](https://github.com/prettier/stylelint-config-prettier) | Turns off all rules that are unnecessary or might conflict with prettier. |
| [stylelint-config-recommended](https://github.com/stylelint/stylelint-config-recommended) | The recommended shareable config for stylelint. |
| [stylelint-config-styled-components](https://github.com/styled-components/stylelint-config-styled-components) | The shareable stylelint config for stylelint-processor-styled-components. |
| [stylelint-processor-styled-components](https://github.com/styled-components/stylelint-processor-styled-components) | Lint your styled components with stylelint. |

### Install Dependencies & Add Config Files

`yarn add -D tslint tslint-config-airbnb tslint-config-prettier tslint-plugin-prettier eslint-config-prettier eslint-plugin-react-hooks @typescript-eslint/parser @typescript-eslint/eslint-plugin prettier stylelint stylelint-config-prettier stylelint-config-recommended stylelint-config-styled-components stylelint-processor-styled-components`

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
    "strictNullChecks": true,
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
    "jsx": "react",
    "rootDir": "src",
    "baseUrl": "src",
    "forceConsistentCasingInFileNames": true,
    "suppressImplicitAnyIndexErrors": true,
    "paths": {
      "*": ["src/*", "node_modules/*"]
    }
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
    "plugin:@typescript-eslint/recommended",
    "airbnb",
    "prettier",
    "prettier/@typescript-eslint",
    "prettier/react",
    "plugin:prettier/recommended",
    "plugin:jest/recommended",
    "plugin:unicorn/recommended"
  ],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaFeatures": {
      "jsx": false
    },
    "project": "./tsconfig.json"
  },
  "plugins": [
    "@typescript-eslint",
    "@typescript-eslint/tslint",
    "prettier",
    "jest",
    "unicorn"
  ],
  "env": {
    "node": true,
    "es6": true,
    "browser": true,
    "jest": true
  },
  "rules": {
    "@typescript-eslint/class-name-casing": "warn",
    "react/jsx-filename-extension": "off",
    "unicorn/filename-case": "off",
    "import/extensions": { "ts": "never", "tsx": "never" },
    "no-use-before-define": "warn",
    "no-param-reassign": "warn"
  },
  "settings": {
    "import/resolver": {
      "node": {
        "extensions": [".js", ".jsx", ".ts", ".tsx"]
      }
    }
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

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).


