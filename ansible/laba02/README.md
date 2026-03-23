# Лабораторная работа 02

## Плейбук gather_facts.yml
Собирает информацию о хосте 10.0.47.102 и выводит в форматированном виде.

## Плейбук install_nginx.yml
Устанавливает nginx, настраивает конфигурацию с добавлением заголовков:
- X-Frame-Options: SAMEORIGIN
- X-Custom-Header: TestAnsiblePlaybook
После выполнения проверяет конфигурацию nginx -t и выполняет curl --head.

## Результаты выполнения
- gather_facts_output.txt — вывод плейбука с информацией о хосте.
- install_nginx_output.txt — вывод плейбука установки nginx.