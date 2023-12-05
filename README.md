# Руководство по развертыванию WordPress и Zabbix Monitoring с использованием Docker и Docker Compose

Этот проект автоматизирует развертывание WordPress и сервера мониторинга Zabbix на сервере с использованием Ansible, Docker и Docker Compose. Следуйте этим инструкциям, чтобы быстро начать использование.
## Требования

   1.  Сервер с установленным Ansible:
       -  Убедитесь, что на сервере установлен Ansible. Если нет, установите его согласно официальной документации Ansible.

   2.  Docker и Docker Compose:
       -  Ansible будет использован для установки Docker и Docker Compose на сервер. Убедитесь, что эти пакеты отсутствуют на сервере.

## Шаги

   1. Клонирование репозитория:

   ```
git clone https://github.com/ваш_пользователь/ваш_репозиторий.git
cd ваш_репозиторий
   ```
   2. Редактирование файла инвентаря Ansible:

    - Отредактируйте файл inventory/hosts.yml, добавив IP-адрес вашего сервера.

   3. Запуск Ansible Playbook:

    - Запустите Ansible Playbook для установки Docker и Docker Compose, а также развертывания WordPress и Zabbix.

    ```

        ansible-playbook -i inventory.ini deployment.yml
    ```
    4. Доступ к WordPress:
       -  После успешного выполнения Ansible Playbook, WordPress будет доступен по адресу: http://ваш_сервер:8085. Используйте учетные данные:
            Username: admin    
            Password: admin

    5. Доступ к Zabbix Web:
       - Мониторинг Zabbix будет доступен по адресу: http://ваш_сервер:8081. Войдите с учетными данными по умолчанию:
            Username: Admin    
            Password: zabbix    

    6. Доступ к Zabbix Server:
       -  Zabbix Server будет слушать порт 10051.

## Дополнительные настройки

    - Настройка окружения WordPress:
        Измените параметры в секции wordpress файла docker-compose.yml для настройки вашего WordPress, таких как имя базы данных, пользователя и пароля.

    - Настройка окружения Zabbix:
        Измените параметры в секциях zabbix-server, zabbix-web, wordpress-zbx-agent, wordpress-db-agent, и zbx-server-agent файла docker-compose.yml для настройки вашего сервера мониторинга Zabbix.

## Заметки

Это руководство предоставляет базовую конфигурацию для быстрого старта. Перед внедрением в продакшене рекомендуется более тщательно настроить систему в соответствии с требованиями вашего проекта.
