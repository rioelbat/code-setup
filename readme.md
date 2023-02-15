# 💥VSCode - ESLint, Prettier & Airbnb Setup

### 🪁Install `ESLint`

```
npm install --save-dev eslint
```

### 🎐Init `ESLint` configuration in project folder

```
npx eslint --init
```

### 🕹️(Optional) Select these options. Then, select yes to install all required packages 

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

### 🎀Install `prettier` and `eslint-config-prettier`
```
npm install --save-dev eslint-config-prettier
npm install --save-dev --save-exact prettier
```

### 🛡️Update extends option with this configuration in `eslintrc.json`
```
"extends": ["airbnb", "airbnb/hooks", "plugin:react/jsx-runtime", "prettier"],
```

### 🧵Remove value of plugins option in `eslintrc.json`
```
"plugins": [],
```

### 📀Create `.eslintignore` in root directory and add these lines
```
vite.config.js
```

### 🪙Create `.prettierrc.json` in root directory and add these options
```
{
    "tabWidth": 2,
    "printWidth": 100,
    "singleQuote": true,
    "trailingComma": "all",
    "jsxSingleQuote": false,
    "bracketSpacing": true
}
```

### 📮Add these lines to the script in `package.json`
```
"lint": "eslint src/**/*.{js,jsx,json}",
"lint:fix": "eslint --fix src/**/*.{js,jsx,json}",
"format": "prettier --write src/**/*.{js,jsx,css,md,json} --config ./.prettierrc.json"
```

##### 📍Use this command to run `eslint` in src/**/*.{js,jsx,json}
```
npm run lint
```

##### 📍Use this command to run `eslint` & fix if there is any error found in src/**/*.{js,jsx,json}
```
npm run lint:fix
```

##### 📍Use this command to format with `prettier` in src/**/*.{js,jsx,json}
```
npm run format
```


### References
* ESLint Rules - https://eslint.org/docs/rules/
* Prettier Options - https://prettier.io/docs/en/options.html
* Airbnb Style Guide - https://github.com/airbnb/javascript
* ESLint + Prettier + Typescript and React in 2022 - https://blog.devgenius.io/eslint-prettier-typescript-and-react-in-2022-e5021ebca2b1
