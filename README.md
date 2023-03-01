# 💥VSCode - ESLint, Prettier (+Airbnb guide style) Setup

This is a guidance for me to setup my VSCode when start a project. 

## If using Vite, Add Vite's plugins to integrate ESLint properly

```
npm install vite-plugin-eslint --save-dev
```

### Update `vite.config.js`

```javascript
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';
import eslint from 'vite-plugin-eslint';

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react(), eslint()],
});
```


## 🪁Install `ESLint`

```
npm install --save-dev eslint
```

## 🎐Init `ESLint` configuration in project folder

```
npx eslint --init
```

## 🕹️(Optional) Select these options. Then, select yes to install all required packages 

```
✔️ How would you like to use ESLint? · style       
✔️ What type of modules does your project use? · esm
✔️ Which framework does your project use? · react
✔️ Does your project use TypeScript? · No
✔️ Where does your code run? · browser
✔️ How would you like to define a style for your project? · guide
✔️ Which style guide do you want to follow? · airbnb
✔️ What format do you want your config file to be in? · JSON
```

## 🎀Install `prettier` and `eslint-config-prettier`

```
npm install --save-dev eslint-config-prettier
```

```
npm install --save-dev --save-exact prettier
```

## 🛡️Update extends option with this configuration in `eslintrc.json`

```json
"extends": ["airbnb", "airbnb/hooks", "plugin:react/jsx-runtime", "prettier"],
```

## 🧵Remove value of plugins option in `eslintrc.json`

```json
"plugins": [],
```

## 👾Create `.prettierrc.json` in root directory and add these options

```json
{
    "tabWidth": 2,
    "printWidth": 100,
    "singleQuote": true,
    "trailingComma": "all",
    "jsxSingleQuote": false,
    "bracketSpacing": true
}
```

## 📮Add these script alias to the script props in `package.json`

```json
"lint": "eslint src/**/*.{js,jsx,json}",
"lint:fix": "eslint --fix src/**/*.{js,jsx,json}",
"format": "prettier --write src/**/*.{js,jsx,css,md,json} --config ./.prettierrc.json"
```

#### 📍Use this command to run `eslint` in src/**/*.{js,jsx,json}

```
npm run lint
```

#### 📍Use this command to run `eslint` & fix if there is any error found in src/**/*.{js,jsx,json}

```
npm run lint:fix
```

#### 📍Use this command to format with `prettier` in src/**/*.{js,jsx,css,md,json}

```
npm run format
```


## References
* ESLint Rules - https://eslint.org/docs/rules/
* Prettier Options - https://prettier.io/docs/en/options.html
* Airbnb Style Guide - https://github.com/airbnb/javascript
* ESLint + Prettier + Typescript and React in 2022 - https://blog.devgenius.io/eslint-prettier-typescript-and-react-in-2022-e5021ebca2b1
* Vite with ESLint - https://www.robinwieruch.de/vite-eslint/
