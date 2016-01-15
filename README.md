##Steps

* Clone git repo to a path like ````/work/{{ my-project }}/mylamp````

* Edit ````/mylamp/ansible/host````. replace the text ````[[EDIT]]```` to make a valid IP address. For example you may replace it with 180.

* Edit ````/mylamp/Vagrantfile````. Replace the text ````[[EDIT]]```` to make valid IP address and paths. The public network IP should match the IP address in the host file mentioned above.


Run the ansible playbook with a command similar to

````
ansible-playbook -i /work/{{ my-project }}/mylamp/ansible/host /work/{{ my-project }}/mylamp/ansible/all.yml 
--extra-vars "root_password=rootpw1 mysql_password=mysqlpw1" --skip-tags "ssl"
````
If you want SSL installed with apache, remove the --skip-tags "ssl" option.
You will need to ensure that certificate.ca-bundle.j2 and certificate.key.j2 have valid contents else apache cannot start/restart


