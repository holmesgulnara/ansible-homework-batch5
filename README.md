# ansible-homework-batch5


NOTE TO SELF:
To check or change remote machine IP address run command:
vi /etc/ansible/hosts

HOMEWORK3 NOTE:
Ansible (root user here) cannot go to Db and cannot create DB, to solve this issue create a user with super permissions, and that user can execute the commands for us:
after installing DB using ansible:
1. SSH into remote VM
2. sudo mysql -u root
Now run next commands 1 by 1:
1. CREATE USER 'ansible'@'localhost' IDENTIFIED BY 'new_password';        (username can be anything)
2. GRANT ALL PRIVILEGES ON *.* TO 'ansible'@'localhost' WITH GRANT OPTION; (password can be anything)
3. FLUSH PRIVILEGES;

CONFIRM:
1. sudo mysql -u ansible -p
2. Enter the password: new_password
Should be logged in successfully
3. EXIT

Now, you can run ansible commands, you should be able to access wordpress and retrieve it's db!!!