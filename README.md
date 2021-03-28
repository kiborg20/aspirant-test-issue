# aspirant-test-issue

Для запуска проекта необходимо:
- в терминале выполнить команду docker-compose up -d --build (при первом запуске);
- получить список контейнеров докер - docker ps, получив имя контейнера (container_name) приложения (в моем случае "aspirant-test-issue_app_1")
- инициализировать табилицы БД в контейнере, полученном на предыдущем пункте, командой docker docker exec container_name bin/console orm:schema-tool:update --force
- затем для импорта таблиц используем команду из контейнера приложения docker exec container_name bin/console fetch:trailers
- открываем в браузере http://localhost:8080