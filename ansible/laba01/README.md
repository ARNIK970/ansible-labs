# Лабораторная работа 01: Сбор фактов Ansible

## Цель
Получить информацию о виртуальных машинах.

## Выполненные команд
```bash
# Сбор фактов с localhost (нашей основной машины)
ansible localhost -m setup -a "filter=ansible_all_ipv4_addresses,ansible_board_name,ansible_board_vendor,ansible_fqdn,ansible_os_family,ansible_uptime_seconds,ansible_user_id" > facts_hosts.txt

# Сбор фактов с тестовой машины 10.0.47.101
ansible -i "10.0.47.101," all -m setup -a "filter=ansible_all_ipv4_addresses,ansible_board_name,ansible_board_vendor,ansible_fqdn,ansible_os_family,ansible_uptime_seconds,ansible_user_id" -u temniynik >> facts_hosts.txt

# Сбор фактов с тестовой машины 10.0.47.102
ansible -i "10.0.47.102," all -m setup -a "filter=ansible_all_ipv4_addresses,ansible_board_name,ansible_board_vendor,ansible_fqdn,ansible_os_family,ansible_uptime_seconds,ansible_user_id" -u temniynik >> facts_hosts.txt
