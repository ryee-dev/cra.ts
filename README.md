This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

# Typescript Project Config

### Additional Dependencies

| Package Name                          | Description   |
| ------------------------------------- | ------------- |
| tslint                                | (to be added) |
| tslint-config-airbnb                  | (to be added) |
| tslint-config-prettier                | (to be added) |
| tslint-plugin-prettier                | (to be added) |
| eslint-config-prettier                | (to be added) |
| @typescript-eslint/parser             | (to be added) |
| @typescript-eslint/eslint-plugin      | (to be added) |
| prettier                              | (to be added) |
| stylelint                             | (to be added) |
| stylelint-config-prettier             | (to be added) |
| stylelint-config-recommended          | (to be added) |
| stylelint-config-styled-components    | (to be added) |
| stylelint-processor-styled-components | (to be added) |

### Install Dependencies & Add Config Files

`yarn add -D tslint tslint-config-airbnb tslint-config-prettier tslint-plugin-prettier eslint-config-prettier @typescript-eslint/parser @typescript-eslint/eslint-plugin prettier stylelint stylelint-config-prettier stylelint-config-recommended stylelint-config-styled-components stylelint-processor-styled-components`

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
