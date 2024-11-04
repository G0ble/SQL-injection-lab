# SQL-injection-lab
SQL injection lab to perform attacks

Let’s start by creating our own database so we can later exploit it. We first need to install the following programs:
```bash
apt install mariadb-server apache2 php-mysql
service mariadb start
service apache2 start
```
Now we can connect to the database to set up the with the following command:
```bash
mariadb -u ["username"] -p ["password"]
-> mariadb -u root -p
```
To look at the existing databases:
```SQL
-> show databases;
```
To store our data we have to create a new database and we have to select it:
-> create database ["database_name"];
-> use ["database_name"];

Our data is stored in tables, each of which contain a certain number of columns.
To create the table with our desired columns:

-> create table users(id int(32), username varchar(32), password varchar(32), ["column"] ["datatype"]);

Now to insert the data:

-> insert into users(id, username, password) values(1, "admin", "admin123$!");
																	.
																	.
																	.

To view the stored data:

-> select ["column"] from users;
or to view all the data
-> select * from users;

We are now ready to exploit an SQL injection. Let’s imagine that we are testing a simple website
