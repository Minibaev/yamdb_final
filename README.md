# yamdb_final
​
![example workflow](https://github.com/github/docs/actions/workflows/yamdb_workflow.yml/badge.svg)
​
Остановить службу: 
​
    sudo systemd stop nginx
​
Установить докер:
​
    sudo apt install docker.io
​
Установить docker-compose
​
    sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
    sudo chmod +x /usr/local/bin/docker-compose
    docker-compose --version
​
Скопируйте файлы docker-compose.yaml и nginx/default.conf из вашего проекта на сервер в home/<ваш_username>/docker-compose.yaml и home/<ваш_username>/nginx/default.conf соответственно.
​
Оживший из этого кода сайт живет [здесь](http://51.250.16.52/admin/)