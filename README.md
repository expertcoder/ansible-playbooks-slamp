Run the ansible playbook with a command similar to

````
ansible-playbook -i /work/mylamp/mylamp/ansible/host /work/mylamp/mylamp/ansible/all.yml --extra-vars "root_password=rootpw1 mysql_password=mysqlpw1"
````