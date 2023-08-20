Выполните установку Node.js:
	sudo apt install nodejs

Проверьте, что установка выполнена успешно, запросив у node номер версии:
	nodejs -v

установить npm:
	sudo apt install npm

Виртуальное окружение
Установка глобальная:
	sudo pip install nodeenv

Создание нового окружения:
	nodeenv env

Активация окружения:
	. env/bin/activate

Отключение окружения:
	deactivate_node

Сохранение в файл «зависимостей» версий всех установленных пакетов:
	. env-4.3/bin/activate
	(env-4.3)$ npm install -g express
	(env-4.3)$ npm install -g jade
	(env-4.3)$ freeze ../prod-requirements.txt

Создание точной копии окружения из файла «зависимостей»:
	nodeenv --requirement=../prod-requirements.txt --jobs=4 env-copy