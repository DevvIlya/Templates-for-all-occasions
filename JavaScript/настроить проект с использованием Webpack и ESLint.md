Конечно, я могу помочь вам настроить проект с использованием Webpack и ESLint. Вам потребуется следовать нескольким шагам:

1. Установка зависимостей:
Откройте терминал и перейдите в корневую директорию вашего проекта. Затем выполните следующие команды:

```bash
# Инициализация проекта (если ещё не инициализирован)
npm init
npm init -y
npm init --scope=@username
npm init --template=<template-name>

#Создание нового окружения:
  nodeenv env

#Активация окружения:
  . env/bin/activate
или
  source env-4.3/bin/activate

# Установка Webpack и связанных зависимостей
npm install webpack webpack-cli webpack-dev-server --save-dev

# Установка Babel для поддержки современного JavaScript
npm install @babel/core @babel/preset-env babel-loader --save-dev

# Установка ESLint и связанных зависимостей
npm install eslint eslint-loader eslint-plugin-import eslint-plugin-react --save-dev

# Установка Mocha для тестирования
npm install mocha chai @babel/preset-env @babel/register --save-dev

npm install --save-dev jest babel-jest @babel/core @babel/cli @babel/preset-env
npm install core-js@3
```

2. Создание файлов конфигурации:

Создайте файлы конфигурации для Webpack и ESLint в корне вашего проекта.

**webpack.config.js**:

```javascript
const path = require('path');

module.exports = {
  entry: './src/index.js', // Ваш основной файл приложения
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js',
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: 'babel-loader',
      },
    ],
  },
  devServer: {
    contentBase: path.resolve(__dirname, 'dist'),
    port: 8080,
  },
};
```

**.eslintrc.js**:

```javascript
module.exports = {
  parser: '@babel/eslint-parser',
  parserOptions: {
    sourceType: 'module',
    allowImportExportEverywhere: false,
  },
  plugins: ['import'],
  extends: ['eslint:recommended', 'plugin:react/recommended'],
  rules: {
    // Ваши правила ESLint
  },
};
```

3. Создание структуры проекта:

Создайте директорию `src` в корне вашего проекта и поместите в неё ваши файлы классов и другой код.

4. Настройка скриптов:

В вашем файле `package.json` добавьте следующие скрипты:

```json
"scripts": {
  "start": "webpack serve --mode development --open",
  "build": "webpack --mode production",
  "lint": "eslint src",
  "test": "mocha --require @babel/register test/**/*.js"
},
```

5. Создание тестов:

Создайте директорию `test` в корне вашего проекта и поместите в неё файлы с тестами.

6. Настройка Babel:

Создайте файл `.babelrc` в корне вашего проекта:

```json
{
  "presets": ["@babel/preset-env"]
}
```

7. Начните разработку:

Теперь вы можете начать разработку, выполнив команду:

```bash
npm start
```

Это запустит сервер разработки с помощью Webpack Dev Server. Ваши файлы будут доступны по адресу http://localhost:8080.

Вы также можете выполнить команду `npm run lint` для проверки кода на соответствие правилам ESLint, и `npm test` для запуска тестов.

Обязательно подставьте свой код в соответствующие части конфигурационных файлов и структуру проекта.