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
    "react-hooks",
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
    "react-hooks/rules-of-hooks": "error",
    "@typescript-eslint/class-name-casing": "warn",
    "react/jsx-filename-extension": "off",
    "unicorn/filename-case": "off",
    "import/extensions": { "ts": "never", "tsx": "never" },
    "no-use-before-define": "warn",
    "no-param-reassign": "warn",
    "unicorn/prevent-abbreviations": "off",
    "no-plusplus": "warn",
    "@typescript-eslint/no-var-requires": "warn",
    "no-restricted-globals": "warn"
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

---

### To-Do

- [ ]  add links and descriptions for remaining dependencies

- [ ]  add brief explanations for important/most-used linter preferences