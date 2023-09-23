Создаnm проект на GitHub-проект, после чего с помощью npm init сгенерируйте package:

package name - defender-game
version - 1.0.0
description - "Browser based game"
entry point - index.js
test command - оставьте пустым
git repository - URL вашего GitHub репозитория
keywords - game
author - ваше имя или псевдоним
license - ISC

Создайте репозиторий на GitHub, после чего с помощью npm init --scope=@username (где username - имя вашего пользователя на GitHub в нижнем регистре, например, если на GitHub у меня логин Netology-Code, то команда будет npm init --scope=@netology-code)

package name - @username/ajs (вам предложат автоматически)
version - 1.0.0 (по умолчанию)
description - оставьте пустым (по умолчанию)
entry point - dist/index.js (!надо поменять на dist/index.js)
остальное всё по умолчанию (просто нажимайте enter)
Убедитесь, что в packages.json автоматически прописался адрес вашего репозитория.