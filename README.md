# Ansible playbook which installs Jenkins



## devops-bootstrap.yml playbook:



1. Generating ssh-keys on host machine. The public key will be sent to nodes, the private key will be used to access them from host.





## inventory.yml - a file with servers, which should be provisioned.  
Group and group's variables are used.  

  



## provision.yml playbook:
  


List of roles:



1. **common** - provides system updates.

2. **create_user** - creates "devops:devops" user, uploads key for ssh-connection, configures sudoers, disables requiretty setting for this user. The role uses the following parameteres (in defaults/main.yml):  
- user (str) - user name to be created  
- group (str) - user's primary group  
- groups2 (list) - user's secondary groups  
- uid (number) - user id  
-	gid (number) – group id
-	home (str) – user's home folder location
-	create_home (bool) - whether create home for user or no
-	authorized_keys (list) - public ssh keys to be updated on the system / current user
-	sudoers (str) – user's sudoers priviliges

3. **java** - installs java-openjdk. Role registers javac and jar in alternatives.

4. **jenkins** - installs Jenkins, creates user jenkins:jenkins, configures systemd to start Jenkins, starts Jenkins and prints the init password to console. The role should skip installation if it's already done.


All roles gather facts about configured software on the system.  

Handlers, templates and default variables are used.



