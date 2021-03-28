# cheatsheet


# Websites

https://landscape.cncf.io - Great site for an overall overview of devops memes and cloud native technologies. Paints the industry picture about tools for sysadmins/SRE/devops.

![20210328181453_vivaldi_xYCmoEW1jX](https://user-images.githubusercontent.com/30216139/112759037-89fece80-8ff1-11eb-93fb-a2be9c10f0b1.png)







# TOOL SPECIFIC 

## MARIADB [DB] 
Database portal 
mariadb cheat-sheet 
conventions: 
use camel case for names
....
databaseName
newPassword 
databaseUser
...

maintence commands mariadb with references to definitive sources
https://robbinespu.github.io/eng/2018/03/29/Reset_mariadb_root_password.html

Password reset

Password reset root option #1
use mysql;
FLUSH PRIVILEGES;
UPDATE user SET authentication_string = password("newPassword") where User='root';
FLUSH PRIVILEGES;

Password reset root option #2
use mysql;
FLUSH PRIVILEGES;
ALTER USER 'root'@'localhost' IDENTIFIED BY 'newPassword';
UPDATE mysql.user SET password = PASSWORD('newPassword') WHERE user = 'root';

option #3 - forgot root pass

mysqld_safe --skip-grant-tables &
https://mariadb.org/authentication-in-mariadb-10-4/


ALTER USER 'root'@'localhost' IDENTIFIED BY 'pass';
DROP DATABASE IF EXISTS databaseName;
select VERSION();


GRANT ALL ON databaseName.* TO 'databaseUser'@'localhost';
SET PASSWORD FOR 'databaseUser'@'localhost' = PASSWORD('newPassword');

