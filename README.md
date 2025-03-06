# YAML
## Ключ - значение
Fruit: Apple
Meat: Chiken
## Массивы/списки
Fruits:
  - Ordnge
  - Apple
## Словари/Мапы
Banana:
      Calories: 102
      Fat: 0.4g
      
### Пример инвентарного файла (INI-формат)
# Группа для веб-серверов
[web]
web1 ansible_host=192.168.1.101 ansible_user=admin ansible_ssh_pass=password123 location=Moscow
web2 ansible_host=192.168.1.102 ansible_user=admin ansible_ssh_pass=password123 location=Murmansk
web3 ansible_host=192.168.1.103 ansible_user=admin ansible_ssh_pass=password123 location=Murmansk

# Группа для баз данных
[db]
db1 ansible_host=192.168.1.201 ansible_user=admin ansible_ssh_pass=password123 location=Moscow
db2 ansible_host=192.168.1.202 ansible_user=admin ansible_ssh_pass=password123 location=Murmansk

# Группа по локациям
[moscow]
web1
db1

[murmansk]
web2
web3
db2

### Пример инвентарного файла (YAML-формат)

all:
  children:
    web:
      hosts:
        web1:
          ansible_host: 192.168.1.101
          ansible_user: admin
          ansible_ssh_pass: password123
          location: Moscow
        web2:
          ansible_host: 192.168.1.102
          ansible_user: admin
          ansible_ssh_pass: password123
          location: Murmansk
        web3:
          ansible_host: 192.168.1.103
          ansible_user: admin
          ansible_ssh_pass: password123
          location: Murmansk
    db:
      hosts:
        db1:
          ansible_host: 192.168.1.201
          ansible_user: admin
          ansible_ssh_pass: password123
          location: Moscow
        db2:
          ansible_host: 192.168.1.202
          ansible_user: admin
          ansible_ssh_pass: password123
          location: Murmansk
    moscow:
      hosts:
        web1:
        db1:
    murmansk:
      hosts:
        web2:
        web3:
        db2:

# ansible
## Установка 
### sudo apt update
### sudo apt install software-properties-common
### sudo add-apt-repository --yes --update ppa:ansible/ansible
### sudo apt install ansible

## Использование SSH-ключа вместо пароля для управления
### Сгенерируйте SSH-ключ на управляющей машине
ssh-keygen -t rsa -b 4096
### Скопируйте публичный ключ на целевой хост
ssh-copy-id osboxes@192.168.0.42
