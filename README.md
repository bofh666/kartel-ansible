# Ansible для сред разработки и тестирования

По умолчанию (ansible.cfg) плейбуки работают с тестовой средой. Все описанные ниже команды нужно выполнять на контрольной машине ctl.kartel.com.ru под пользователем kartel, перейдя в дирекотрию ~/playbooks. Чтобы ничего не сломать, перед их выполнением *обязательно* нужно делать ```git pull```.

Чтобы создать полностью среду "с нуля", нужно выполнить ```ansible-playbook deploy.yml```, причем дважды -- есть непонятный нюанс: пакет rabbitmq-server упорно не хочет ставиться с первого раза.

Чтобы обновить скрипты создания БД, нужно выполнить ```ansible-playbook createdb.yml```.

Чтобы обновить код сервисов, нужно выполнить ```ansible-playbook services.yml```.

Чтобы обновить код кабинета, нужно выполнить ```ansible-playbook cabinets.yml```.

Чтобы запустить Ansible на среде для разработки, к указанным командам нужно добавить параметр через -i: ```ansible-playbook -i envs/dev/hosts deploy.yml```.
