# Лабораторная работа 05

## Проверка служб и параметров ядра (рекомендации ФСТЭК)

### Цели
- Убедиться, что нежелательные службы (autofs, avahi, dhcp, dns, ftp, ldap, nfs, nis, cups, samba, snmp, tftp, web, xinetd, mta) неактивны.
- Проверить параметры ядра из рекомендаций ФСТЭК (полный список sysctl и опций загрузки GRUB).

### Файлы
- `check_services.yml` – плейбук для проверки служб.
- `check_kernel.yml` – плейбук для проверки параметров ядра.
- `check_services_output.txt` – вывод проверки служб.
- `check_kernel_output.txt` – вывод проверки параметров ядра.

### Команды для запуска (с основной ВМ)

```bash
# Проверка служб
ansible-playbook -i "10.0.47.102," -u temniynik --private-key=/home/temniynik/.ssh/id_rsa -K check_services.yml | tee check_services_output.txt

# Проверка параметров ядра
ansible-playbook -i "10.0.47.102," -u temniynik --private-key=/home/temniynik/.ssh/id_rsa -K check_kernel.yml | tee check_kernel_output.txt