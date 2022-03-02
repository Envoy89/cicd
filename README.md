# CI/CD for Envoy89 git projects

## Описание
1. Запускаем nginx чтобы перенаправлять запросы с порта 80 на порт 443
1. Запускаем drone на порту 443

## Порядок запуска
1. Для запуска заполняем значениями файл variables.env
    1. DRONE_GITHUB_CLIENT_ID = ид приложения авторизации из github
    1. DRONE_GITHUB_CLIENT_SECRET = секретный ключ приложения авторизации из github
    1. DRONE_RPC_SECRET = сгенерированный ключ openssl rand -hex 16
    1. DRONE_SERVER_HOST = адрес, по которому доступен drone
1. В файле nginx-conf/nginx.conf заменить server_name на адрес, по которому доступен drone
1. Запустить все командой docker-compose up -d