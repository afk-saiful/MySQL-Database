# Setting Up MySQL Database

This guide will walk you through the process of setting up a MySQL database with a new user using the command line.

## Prerequisites

- MySQL installed on your system

## Steps

1. Open your terminal or command prompt.

2. Log in to MySQL as the root user:

   ```bash
   mysql -u root -p
   use mysql
   CREATE USER 'lufias'@'%' IDENTIFIED BY 'lufias';
   GRANT ALL PRIVILEGES ON *.* TO 'lufias'@'%' WITH GRANT OPTION;
   FLUSH PRIVILEGES;
   exit
   
Output:

![](https://bgasparotto.com/wp-content/uploads/2015/05/mysql-logo.png)


> [!NOTE]
> You Need To Open The ports for the MySql which is 3306.

- This is to be done when you are not able to add the data in the panel.
- Make sure your MYSQL Ports are open.

1. You need to go in this file
```bash
nano /etc/mysql/mariadb.conf.d/50-server.cnf
```

4. Change the Bind port from ``127.0.0.1`` TO ``0.0.0.0``


- **Don't use the numpad of your keyboard in this file.**

4. Save the file.

5. Run
```bash
   systemctl restart mysql && systemctl restart mariadb
```
- So that all the settings take place
