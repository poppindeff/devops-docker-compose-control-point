Практическое задание №4
Описание: Работа с Docker-compose
Результатом работы должен быть составлен отчет о выполненной работе в
формате .pdf или пришлите ссылку на репозиторий в Gitlab/Github
Описание задания:
У нас есть набор исходников - https://github.com/darkbenladan/docker-nginx-python2-db-
redis-homework
Нам надо выполнить git clone.
Просмотрите все конфиг-файлы, dockerfile, docker-compose.yml и найдите все ошибки.
Например, в dockerfile в качестве исходника для образа может не быть слоя FROM
nginx:alpine/, в других dockerfile может отсутствовать volume /data, порт 6379,
пользователи.
1. В папке web в Dockerfile задайте источник python:2.7-stretch, пользователя root,
порт 9000. Подсказка: в большинстве случаев в месте, где надо что-то добавить,
стоит коммент через #.
2. Внесите правки в docker-compose.yml:
o в блок services определите сети — frontend и backend;
o в блок volume добавьте путь ./web/cron/crontab_todo:/etc/crontab;
o в блок consumers добавьте порт 9000;
o в блок redis build добавьте ./redis и порт 6379.
3. Когда вы подумаете, что все исправления выполнены, выполните $ docker-compose
up.
Если всё сделано корректно, то запустится два экземпляра redis
