# Лабораторная работа 03

## Настройка TMOUT и проверка конфигурации Kerberos/SSSD

### Цели
- Установить тайм-аут бездействия пользовательской сессии (TMOUT=900) в файлах `/etc/profile` и `/etc/bash.bashrc`.
- Настроить клиент Kerberos (`/etc/krb5.conf`) с требуемыми параметрами шифрования.
- Настроить SSSD (`/etc/sssd/sssd.conf`) с отключением кэширования учётных данных (`cache_credentials = False`) и формой домашнего каталога с подстановкой домена (`/home/%u@%d`).

### Файлы
- `configure_tmout.yml` – плейбук для настройки TMOUT.
- `configure_ad.yml` – плейбук для настройки Kerberos и SSSD.
- `check_tmout.yml` – плейбук для проверки TMOUT.
- `check_ad_config.yml` – плейбук для проверки настроек Kerberos и SSSD.
- `configure_tmout_output.txt` – вывод при настройке TMOUT.
- `configure_ad_output.txt` – вывод при настройке Kerberos и SSSD.
- `check_tmout_output.txt` – вывод при проверке TMOUT.
- `check_ad_output.txt` – вывод при проверке Kerberos и SSSD.

### Команды для запуска (с основной ВМ)

```bash
# Настройка TMOUT
ansible-playbook -i "10.0.47.102," -u temniynik --private-key=/home/temniynik/.ssh/id_rsa -K configure_tmout.yml | tee configure_tmout_output.txt

# Настройка Kerberos и SSSD
ansible-playbook -i "10.0.47.102," -u temniynik --private-key=/home/temniynik/.ssh/id_rsa -K configure_ad.yml | tee configure_ad_output.txt

# Проверка TMOUT
ansible-playbook -i "10.0.47.102," -u temniynik --private-key=/home/temniynik/.ssh/id_rsa -K check_tmout.yml | tee check_tmout_output.txt

# Проверка настроек Kerberos и SSSD
ansible-playbook -i "10.0.47.102," -u temniynik --private-key=/home/temniynik/.ssh/id_rsa -K check_ad_config.yml | tee check_ad_output.txt