
 1. Клонируем проект 

$ git clone https://github.com/BroccoliPower/sf_final_1.git
$ cd sf_final_1

2. Генерируем ключи и копируем в каталог проекта

$ ssh-keygen -t rsa
$ cp ~/.ssh/id_rsa* ./

3. Правим реквизиты Yandex Cloud в файле terraform/main.tf

$ cd terraform 
$ terraform init 
$ terraform apply

4. Запускаем плейбуки для настройки кластера k8s

$ cd ../ansible 
$ ansible-playbook -i hosts create-users.yml 
$ ansible-playbook -i hosts kube-install.yml 
$ ansible-playbook -i hosts conf-master.yml 
$ ansible-playbook -i hosts join-workers.yml 
$ ansible-playbook -i hosts final-conf.yml 

