# Лабораторная работа 06

## Настройка auditd и сбор логов

### Выполненные действия
1. Установлен auditd.
2. Добавлены правила аудита:
   - `/etc/ssh/sshd_config` (ключ `sshd_config`)
   - `chmod` и `chown` (ключ `file_perms`)
   - команды с `uid=0` (ключ `priv_esc`)
3. Выполнены тестовые команды: `sudo ls`, добавлен комментарий в `sshd_config`, `chmod +r`.
4. Сформированы отчёты `report1.txt` (правила) и `report2.txt` (записи аудита).

### Файлы
- `report1.txt` – вывод `auditctl -l`.
- `report2.txt` – выдержки из `/var/log/audit/audit.log` по ключам.
