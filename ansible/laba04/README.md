# Лабораторная работа 04

## Цели
- Установить и выполнить проверку системы с помощью chkrootkit.
- Проверить, что модули неиспользуемых файловых систем (cramfs, freevxfs, jffs2, hfs, hfsplus, squashfs) отключены.
- Настроить параметры безопасности:
  - UMASK 027 в `/etc/login.defs`
  - Скрипт `/etc/profile.d/orgnm.sh` с `umask 027`
  - DIR_MODE 0700 в `/etc/adduser.conf`
  - Права доступа к `/var/log` по стандарту.

## Файлы
- `chkrootkit.yml` – плейбук для установки и запуска chkrootkit.
- `check_modules.yml` – плейбук для проверки отключения модулей.
- `security_settings.yml` – плейбук для настройки параметров безопасности.
- `chkrootkit_output.txt` – вывод выполнения chkrootkit.
- `check_modules_output.txt` – вывод проверки модулей.
- `security_settings_output.txt` – вывод настройки безопасности.

## Команды для запуска (с основной ВМ)

```bash
# chkrootkit
ansible-playbook -i "10.0.47.102," -u temniynik --private-key=/home/temniynik/.ssh/id_rsa -K chkrootkit.yml | tee chkrootkit_output.txt

# проверка модулей
ansible-playbook -i "10.0.47.102," -u temniynik --private-key=/home/temniynik/.ssh/id_rsa -K check_modules.yml | tee check_modules_output.txt

# настройка безопасности
ansible-playbook -i "10.0.47.102," -u temniynik --private-key=/home/temniynik/.ssh/id_rsa -K security_settings.yml | tee security_settings_output.txt