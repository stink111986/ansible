# YAML
## Ключ - значение
### Fruit: Apple
### Meat: Chiken
## Массивы/списки
Fruits:
  - Ordnge
  - Apple
## Словари/Мапы
Banana:
      Calories: 102
      Fat: 0.4g
      
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
