# <span style='color:green, font-family; times, serif; font-size:30pt; font-style:italic'>Chapter No# 10 Databases</span>

* What Is Database?
* Downloading & Installation Mysql Or Mariadb
* Memorize Some Mysql Command
* Installation Mysql Library
* Mysql Connectivity With Respect To Python
* Create Database | Create Table |Insert
* Select | Where | Order By | Delete
* Drop Table | Update | Limit |Join


# <li style="font-size:20pt;">What Is Database?</li>
A database is an organized collection of structured information, or data, typically stored electronically on a computer system. A database is used for storing, maintaining, and accessing any sort of data. They collect information on people, places, or things so that it can be observed and analyzed. A database is usually controlled by a database management system (DBMS).

# <li style="font-size:20pt;">What Is MYSQL?</li>
MySQL is an open-source relational database management system (RDBMS). The software uses SQL as its underlying data language. There are no limits to the number of servers, users or databases that you may create with it as long as your subscription remains active. In addition, the software has a large user community and many commercial support options are available.

# <li style="font-size:20pt;">Downloading & Installation Mysql Or Mariadb</li>

https://dev.mysql.com/downloads/installer/

## Step 1:
Go to the official website of MySQL and download the community server edition software. Here, you will see the option to choose the Operating System, such as Windows.

## Step 2:
Next, there are two options available to download the setup. Choose the version number for the MySQL community server, which you want. If you have good internet connectivity, then choose the mysql-installer-web-community. Otherwise, choose the other one.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/550d21a8-bb6a-4907-9ee1-e298ed098e5b)

# Installing MySQL on Windows
## Step 1:
After downloading the setup, unzip it anywhere and double click the MSI installer .exe file. It will give the following screen:
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/dca1be60-67e2-49af-bfa3-6e54e990f843)

## Step 2:
In the next wizard, choose the Setup Type. There are several types available, and you need to choose the appropriate option to install MySQL product and features. Here, we are going to select the Full option and click on the Next button.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/5e3f609b-962a-457f-be05-ea131bc1551e)

This option will install the following things: MySQL Server, MySQL Shell, MySQL Router, MySQL Workbench, MySQL Connectors, documentation, samples and examples, and many more.

## Step 3:
Once we click on the Next button, it may give information about some features that may fail to install on your system due to a lack of requirements. We can resolve them by clicking on the Execute button that will install all requirements automatically or can skip them. Now, click on the Next button.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/2876885b-7074-41c4-b7ee-4a9afd7612b4)

## Step 4:
In the next wizard, we will see a dialog box that asks for our confirmation of a few products not getting installed. Here, we have to click on the Yes button.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/0975452f-071f-4174-8ce1-34ae89330ecf)

After clicking on the Yes button, we will see the list of the products which are going to be installed. So, if we need all products, click on the Execute button.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/2f8d7211-10fd-4e51-a414-40a10367aba4)

## Step 5:
Once we click on the Execute button, it will download and install all the products. After completing the installation, click on the Next button.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/5619d0ef-2b12-48de-81c1-f9a8dffa3230)

## Step 6:
In the next wizard, we need to configure the MySQL Server and Router. Here, I am not going to configure the Router because there is no need to use it with MySQL. We are going to show you how to configure the server only. Now, click on the Next button.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/3a4927cd-9f29-4f97-aa3c-366254ad3bd6)

## Step 7:
As soon as you will click on the Next button, you can see the screen below. Here, we have to configure the MySQL Server. Now, choose the Standalone MySQL Server/Classic MySQL Replication option and click on Next. Here, you can also choose the InnoDB Cluster based on your needs.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/61cc5c0f-0e56-4234-8b00-58a2b0b554ba)

## Step 8:
In the next screen, the system will ask you to choose the Config Type and other connectivity options. Here, we are going to select the Config Type as 'Development Machine' and Connectivity as TCP/IP, and Port Number is 3306, then click on Next.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/95f9ec4c-5bc7-48b3-b84e-777e31f82a57)

## Step 9:
Now, select the Authentication Method and click on Next. Here, I am going to select the first option.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/aea1ca23-41da-44de-9433-87b34a0eeb6b)

## Step 10:
The next screen will ask you to mention the MySQL Root Password. After filling the password details, click on the Next button.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/0b9c1616-2e53-41c0-a070-159b7119769c)

## Step 11:
The next screen will ask you to configure the Windows Service to start the server. Keep the default setup and click on the Next button.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/16f05f9d-5cef-4a99-9a38-e15ea28c08bb)

## Step 12:
In the next wizard, the system will ask you to apply the Server Configuration. If you agree with this configuration, click on the Execute button.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/deac10cf-d8cb-4d3e-8131-204eb608a644)

## Step 13:
Once the configuration has completed, you will get the screen below. Now, click on the Finish button to continue.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/e1199431-0622-4793-b093-29cfe5d73868)

## Step 14:
In the next screen, you can see that the Product Configuration is completed. Keep the default setting and click on the Next-> Finish button to complete the MySQL package installation.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/95786ef2-2b45-429d-b252-c4bb9242043a)

## Step 15:
In the next wizard, we can choose to configure the Router. So click on Next->Finish and then click the Next button.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/c2ba2800-2d44-4917-9bc4-360faf7c81b9)

## Step 16:
In the next wizard, we will see the Connect to Server option. Here, we have to mention the root password, which we had set in the previous steps.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/adcebf22-8ab4-49ed-a849-ae10cce22e29)

In this screen, it is also required to check about the connection is successful or not by clicking on the Check button. If the connection is successful, click on the Execute button. Now, the configuration is complete, click on Next.

## Step 17:
In the next wizard, select the applied configurations and click on the Execute button.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/39401439-09ac-4ba1-9ac1-a44b5dd5e757)

## Step 18:
After completing the above step, we will get the following screen. Here, click on the Finish button.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/5a62aa85-4c04-45ed-b30b-2efd491f90ad)

## Step 19:
Now, the MySQL installation is complete. Click on the Finish button.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/f0beac76-cdda-4bd4-8165-e385205d9ef5)


# Verify MySQL installation
Once MySQL has been successfully installed, the base tables have been initialized, and the server has been started, you can verify its working via some simple tests.

Open your MySQL Command Line Client; it should have appeared with a mysql> prompt. If you have set any password, write your password here. Now, you are connected to the MySQL server, and you can execute all the SQL command at mysql> prompt as follows:

## For example: 
Check the already created databases with show databases command:
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/de0d994c-631f-45c4-b1d7-ac1a0d6648c6)

# What is the Primary key?
A primary key is a single field or combination of fields that contain a unique record. It must be filled. None of the fields of the primary key can contain a null value. A table can have only one primary key.

# <li style="font-size:20pt;">Download MariaDB</li>

`Goto this link `https://mariadb.org/download/?t=mariadb&o=true&p=mariadb&r=10.5.5&os=windows&cpu=x86_64&pkg=msi `and download mariadb`

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/1b0b8e59-b5fa-4903-81b8-86e7dbf6e6a5)

To install MariaDB on Windows, you follow these steps:

## Step 1. Start installation
Double-click the installer to start the installation process.

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/e813e135-3d60-46a5-b945-d74e45179b95)

## Step 2. Accept the end-user license agreement
Read the end-user license agreement and click the Next button:

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/09306b3a-6a24-41f9-8e43-a8ebf6f5c6fd)

## Step 3. Select features
Choose the directory that stores the MariaDB files and click the Next button. The default location on Windows is C:\Program Files\MariaDB 10.4\.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/0a2d3db5-939e-46e0-afb4-cbe9b3f66344)

## Step 4. Set root’s password
Type a password for the root user account. You will use this password to connect to MariaDB later.  The root user is the default user of the MariaDB, which has all privileges.

If you don’t want the root user to login from a remote machine, you need to uncheck the `Enable access from remote machines for 'root' user` checkbox.

The `Use UTF8 as the default server's character set` option allows you to use the UTF8 as the default character set when you create new databases and tables.

Once you complete selecting all options, click the Next button to go to the next step.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/f0bbdc52-245f-46f7-af45-4b3b96db198c)

## Step 5. Configure Database
In this step:

First, install MariaDB as a service by selecting the Install as service option. It allows you to rename the service name.

Second, configure the port for the MariaDB. By default, MariaDB uses 3306 port. However, you can change it to your port if you want.

Third, specify the parameters for the Innodb engine including buffer pool size and page size.  16KB page size is suitable for most databases.

Finally, click the Next button to go to the next step.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/9a6b17b4-21e2-4805-acae-135c3065c36f)

## Step 6. Submit usage information
If you want to submit anonymous usage information so that MariaDB developers can improve the system, check the checkbox and click the Next button.
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/e65edd77-e526-4de4-8c67-925618967a56)


## Step 7.  Ready to install MariaDB
Click the Install button to start installing MariaDB

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/38145a24-6977-4c75-88b1-3c75721f0e21)
It will take a few minutes depending on the system.

![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/f44b67be-2fb4-4636-b1c0-d4b5477b400f)

## Step 8. Complete the MariaDB setup
Click the Finish button to complete MariaDB setup
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/0d5b5bc3-77e2-4182-8b5c-ac5a8c6f77be)

You can find the MariaDB tools in the startup menu:
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/3c0a798e-50ba-4132-bbfa-5c378c5deb84)

# <li style="font-size:20pt;">Memorize Some Mysql Command</li>

## Command 1: `SHOW DATABASES; | show databases;`
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/7ed44577-6640-4503-a461-aad921ea49ac)

## Command 2: `create database employees_data;`
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/7884b32c-f4e1-4d51-a5a0-eac134af8a45)

## Command 3: `show tables;`
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/3759d987-1293-4121-8144-85906f0f48bb)

## Command 4: `use employees_data;`
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/865f7242-f43e-453e-b900-3ffc4a120714)

## Command 5: `create table staff (id INT AUTO_INCREMENT PRIMARY KEY, name VARCHAR(255), address VARCHAR(255));`
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/a4281fc9-326e-44c3-93b8-2f16be6d6cf3)

## Command 6: `desc staff;` <- describe Table
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/4886c2cc-437a-46a2-85a9-c120274a1a1f)

## Command 7: `insert into staff (name, address) VALUES ("Imran", "Highway Bahria Town");`
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/758be2e9-d1e2-41f8-9b9f-6498b07ccbf8)

## Command 8: `select * from staff;`
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/2b0b7d6d-eb67-4919-80e4-ee191c62702d)
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/f6a27a8d-1c6d-4cde-a198-c239182ae811)

## Command 9: `select * from staff where name ="Ali";`
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/17ee8286-a722-433f-8d4e-a4d7185519d9)
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/9778d7a3-1bbb-4736-ab35-b91e55126aa7)

## Command 10: `SELECT * FROM staff ORDER BY name DESC;`
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/6fc9f275-8a21-49c3-b4cb-1a9f87184327)

## Command 11: `DELETE FROM staff WHERE name = 'Asad';`4
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/84a663c4-3931-440c-9d22-9e1070cc186c)

## Command 12: `UPDATE staff SET address = 'Defense Housing Society' WHERE address = 'Highway Bahria Town';`
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/6f7acc35-63aa-469d-96d5-d7d7c9b77924)

# <li style="font-size:20pt;">Installation Mysql Library</li>

### pip install mysql-connector-python | py -m pip install mysql-connector-python
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/fda37a58-8c88-4764-be33-02459ec7cb89)

Package Install Successfully
![image](https://github.com/MuhammadRaheelNaseem/Learn-Python-By-Sir-Raheel/assets/63813881/aa82e969-72e0-4e4d-b729-47cf3559e77c)


# <li style="font-size:20pt;">Mysql Connectivity With Respect To Python</li>



```python
import mysql.connector

db = mysql.connector.connect(
    host="localhost",
    user="root",
    password="admin"
)

if db.is_connected():
    print("Database Connected")
```

    Database Connected
    

# <li style="font-size:20pt;">Create Database</li>
# What is cursor?
A cursor is an object which helps to execute the query and fetch the records from the database. This article will learn some deep information about the execute methods and how to use those methods in python.


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin"
)

cur = db.cursor()
cur.execute("show databases")

for i in cur:
    print(i)

```

    ('books',)
    ('employees_data',)
    ('information_schema',)
    ('iot',)
    ('mysql',)
    ('performance_schema',)
    ('python',)
    ('sakila',)
    ('schools',)
    ('sys',)
    ('world',)
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin"
)

cur = db.cursor()
cur.execute("use mysql")
```


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
    database='mysql'
)
if db.is_connected():
    print("Database Connected")
```

    Database Connected
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
    database="",
)

cursor = db.cursor()
sql = "create database IoTT"
cursor.execute(sql)

print("Database Created Successful !!!")
```

    Database Created Successful !!!
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin"
)

cur = db.cursor()
cur.execute("show databases")

for i in cur:
    print(i)

```

    ('books',)
    ('employees_data',)
    ('information_schema',)
    ('iot',)
    ('iott',)
    ('mysql',)
    ('performance_schema',)
    ('python',)
    ('sakila',)
    ('schools',)
    ('sys',)
    ('world',)
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
)

cursor = db.cursor()
sql = "create database Bookss"
cursor.execute(sql)

print("Database Created Successful !!!")
```

    Database Created Successful !!!
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin"
)

cur = db.cursor()
cur.execute("show databases")

for i in cur:
    print(i)

```

    ('books',)
    ('bookss',)
    ('employees_data',)
    ('information_schema',)
    ('iot',)
    ('iott',)
    ('mysql',)
    ('performance_schema',)
    ('python',)
    ('sakila',)
    ('schools',)
    ('sys',)
    ('world',)
    

# <li style="font-size:20pt;">Create Table</li>


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
    database="books",
)

cursor = db.cursor()
sql = """CREATE TABLE Book_Namess (
  book_id INT AUTO_INCREMENT PRIMARY KEY,
  Book_Name VARCHAR(255),
  Book_Author Varchar(255)
)
"""
cursor.execute(sql)

print("Table Created Successful !!!")
```

    Table Created Successful !!!
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
    database="books",
)

cursor = db.cursor()
sql = "show tables"
cursor.execute(sql)

for i in cursor:
    print(i)
```

    ('book_names',)
    ('book_namess',)
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
    database="books",
)

cursor = db.cursor()
sql = """CREATE TABLE Book_Catogary (
  book_id INT AUTO_INCREMENT PRIMARY KEY,
  Book_Name VARCHAR(255),
  Book_Author Varchar(255)
)
"""
cursor.execute(sql)

print("Table Created Successful !!!")
```

    Table Created Successful !!!
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
    database="books",
)

cursor = db.cursor()
sql = "show tables"
cursor.execute(sql)

for i in cursor:
    print(i)
```

    ('book_catogary',)
    ('book_names',)
    ('book_namess',)
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
    database="books",
)

cursor = db.cursor()
sql = """CREATE TABLE Book_Writer (
  book_id INT AUTO_INCREMENT PRIMARY KEY,
  Book_Name VARCHAR(255),
  Book_Author Varchar(255)
)
"""
cursor.execute(sql)

print("Table Created Successful !!!")
```

    Table Created Successful !!!
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
    database="books",
)

cursor = db.cursor()
sql = "show tables"
cursor.execute(sql)

for i in cursor:
    print(i)
```

    ('book_catogary',)
    ('book_names',)
    ('book_namess',)
    ('book_writer',)
    

# <li style="font-size:20pt;">Describe Table</li>


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin"
)

cursor = db.cursor()
sql = "show databases"
cursor.execute(sql)

for i in cursor:
    print(i)
```

    ('books',)
    ('bookss',)
    ('employees_data',)
    ('information_schema',)
    ('iot',)
    ('iott',)
    ('mysql',)
    ('performance_schema',)
    ('python',)
    ('sakila',)
    ('schools',)
    ('sys',)
    ('world',)
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
    database="mysql",
)

cursor = db.cursor()
sql = "show tables"
cursor.execute(sql)

for i in cursor:
    print(i)
```

    ('columns_priv',)
    ('component',)
    ('db',)
    ('default_roles',)
    ('engine_cost',)
    ('func',)
    ('general_log',)
    ('global_grants',)
    ('gtid_executed',)
    ('help_category',)
    ('help_keyword',)
    ('help_relation',)
    ('help_topic',)
    ('innodb_index_stats',)
    ('innodb_table_stats',)
    ('password_history',)
    ('plugin',)
    ('procs_priv',)
    ('proxies_priv',)
    ('replication_asynchronous_connection_failover',)
    ('replication_asynchronous_connection_failover_managed',)
    ('replication_group_configuration_version',)
    ('replication_group_member_actions',)
    ('role_edges',)
    ('server_cost',)
    ('servers',)
    ('slave_master_info',)
    ('slave_relay_log_info',)
    ('slave_worker_info',)
    ('slow_log',)
    ('tables_priv',)
    ('time_zone',)
    ('time_zone_leap_second',)
    ('time_zone_name',)
    ('time_zone_transition',)
    ('time_zone_transition_type',)
    ('user',)
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
    database="sakila",
)

cursor = db.cursor()
sql = "show tables"
cursor.execute(sql)

for i in cursor:
    print(i)
```

    ('actor',)
    ('actor_info',)
    ('address',)
    ('category',)
    ('city',)
    ('country',)
    ('customer',)
    ('customer_list',)
    ('film',)
    ('film_actor',)
    ('film_category',)
    ('film_list',)
    ('film_text',)
    ('inventory',)
    ('language',)
    ('nicer_but_slower_film_list',)
    ('payment',)
    ('rental',)
    ('sales_by_film_category',)
    ('sales_by_store',)
    ('staff',)
    ('staff_list',)
    ('store',)
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
    database='sys'
)

cursor = db.cursor()
sql = "show tables"
cursor.execute(sql)

for i in cursor:
    print(i)
```

    ('host_summary',)
    ('host_summary_by_file_io',)
    ('host_summary_by_file_io_type',)
    ('host_summary_by_stages',)
    ('host_summary_by_statement_latency',)
    ('host_summary_by_statement_type',)
    ('innodb_buffer_stats_by_schema',)
    ('innodb_buffer_stats_by_table',)
    ('innodb_lock_waits',)
    ('io_by_thread_by_latency',)
    ('io_global_by_file_by_bytes',)
    ('io_global_by_file_by_latency',)
    ('io_global_by_wait_by_bytes',)
    ('io_global_by_wait_by_latency',)
    ('latest_file_io',)
    ('memory_by_host_by_current_bytes',)
    ('memory_by_thread_by_current_bytes',)
    ('memory_by_user_by_current_bytes',)
    ('memory_global_by_current_bytes',)
    ('memory_global_total',)
    ('metrics',)
    ('processlist',)
    ('ps_check_lost_instrumentation',)
    ('schema_auto_increment_columns',)
    ('schema_index_statistics',)
    ('schema_object_overview',)
    ('schema_redundant_indexes',)
    ('schema_table_lock_waits',)
    ('schema_table_statistics',)
    ('schema_table_statistics_with_buffer',)
    ('schema_tables_with_full_table_scans',)
    ('schema_unused_indexes',)
    ('session',)
    ('session_ssl_status',)
    ('statement_analysis',)
    ('statements_with_errors_or_warnings',)
    ('statements_with_full_table_scans',)
    ('statements_with_runtimes_in_95th_percentile',)
    ('statements_with_sorting',)
    ('statements_with_temp_tables',)
    ('sys_config',)
    ('user_summary',)
    ('user_summary_by_file_io',)
    ('user_summary_by_file_io_type',)
    ('user_summary_by_stages',)
    ('user_summary_by_statement_latency',)
    ('user_summary_by_statement_type',)
    ('version',)
    ('wait_classes_global_by_avg_latency',)
    ('wait_classes_global_by_latency',)
    ('waits_by_host_by_latency',)
    ('waits_by_user_by_latency',)
    ('waits_global_by_latency',)
    ('x$host_summary',)
    ('x$host_summary_by_file_io',)
    ('x$host_summary_by_file_io_type',)
    ('x$host_summary_by_stages',)
    ('x$host_summary_by_statement_latency',)
    ('x$host_summary_by_statement_type',)
    ('x$innodb_buffer_stats_by_schema',)
    ('x$innodb_buffer_stats_by_table',)
    ('x$innodb_lock_waits',)
    ('x$io_by_thread_by_latency',)
    ('x$io_global_by_file_by_bytes',)
    ('x$io_global_by_file_by_latency',)
    ('x$io_global_by_wait_by_bytes',)
    ('x$io_global_by_wait_by_latency',)
    ('x$latest_file_io',)
    ('x$memory_by_host_by_current_bytes',)
    ('x$memory_by_thread_by_current_bytes',)
    ('x$memory_by_user_by_current_bytes',)
    ('x$memory_global_by_current_bytes',)
    ('x$memory_global_total',)
    ('x$processlist',)
    ('x$ps_digest_95th_percentile_by_avg_us',)
    ('x$ps_digest_avg_latency_distribution',)
    ('x$ps_schema_table_statistics_io',)
    ('x$schema_flattened_keys',)
    ('x$schema_index_statistics',)
    ('x$schema_table_lock_waits',)
    ('x$schema_table_statistics',)
    ('x$schema_table_statistics_with_buffer',)
    ('x$schema_tables_with_full_table_scans',)
    ('x$session',)
    ('x$statement_analysis',)
    ('x$statements_with_errors_or_warnings',)
    ('x$statements_with_full_table_scans',)
    ('x$statements_with_runtimes_in_95th_percentile',)
    ('x$statements_with_sorting',)
    ('x$statements_with_temp_tables',)
    ('x$user_summary',)
    ('x$user_summary_by_file_io',)
    ('x$user_summary_by_file_io_type',)
    ('x$user_summary_by_stages',)
    ('x$user_summary_by_statement_latency',)
    ('x$user_summary_by_statement_type',)
    ('x$wait_classes_global_by_avg_latency',)
    ('x$wait_classes_global_by_latency',)
    ('x$waits_by_host_by_latency',)
    ('x$waits_by_user_by_latency',)
    ('x$waits_global_by_latency',)
    

# <li style="font-size:20pt;">Insert Table</li>



```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
    database="employees_data",
)

cursor = db.cursor()
sql = "INSERT INTO staff (name, address) VALUES (%s, %s)"
values = ("Alian","Street 5 Jupiter")

# for val in values:
#     cursor.execute(sql, val)
cursor.execute(sql,values)

db.commit()

print("{} data added".format(cursor.rowcount))
```

    1 data added
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
    database="employees_data",
)

cursor = db.cursor()
sql = "INSERT INTO staff (name, address) VALUES (%s, %s)"
values = [
    ("Alian","Street 5 Jupiter"),
    ("Alia","Street 5 Jupiter"),
    ("Ali","Street 5 Jupiter"),
    ("john alia","Street 5 Jupiter"),
    ("Alian","Street 5 Jupiter")
]

# for val in values:
#     cursor.execute(sql, val)
cursor.executemany(sql,values)

db.commit()

print("{} data added".format(cursor.rowcount))
```

    5 data added
    


```python
import mysql.connector

db = mysql.connector.connect(
    host="127.0.0.1",
    user="root",
    password="admin",
    database="books",
)

cursor = db.cursor()
sql = "INSERT INTO book_writer (book_name, book_author) VALUES (%s, %s)"
values = [
    ("Alian","Street 5 Jupiter"),
    ("Alia","Street 5 Jupiter"),
    ("Ali","Street 5 Jupiter"),
    ("john alia","Street 5 Jupiter"),
    ("Alian","Street 5 Jupiter")
]

# for val in values:
#     cursor.execute(sql, val)
cursor.executemany(sql,values)

db.commit()

print("{} data added".format(cursor.rowcount))
```

    5 data added
    

# <li style="font-size:20pt;">Select Table -> fetchall()</li>



```python
import mysql.connector

dataBase = mysql.connector.connect(
host ="localhost",
user ="root",
passwd ="admin",
database = "employees_data"
)

# preparing a cursor object
cursorObject = dataBase.cursor()

query = "SELECT address FROM staff"
cursorObject.execute(query)

myresult = cursorObject.fetchall()

for x in myresult:
    print(x)

# disconnecting from server
db.close()
db
```

    ('Street 5 Jupiter',)
    ('Street 5 Jupiter',)
    ('Street 5 Jupiter',)
    ('Street 5 Jupiter',)
    ('Street 5 Jupiter',)
    ('Street 5 Jupiter',)
    




    <mysql.connector.connection_cext.CMySQLConnection at 0x19b7524cb80>




```python
import mysql.connector

dataBase = mysql.connector.connect(
host ="localhost",
user ="root",
passwd ="admin",
database = "mysql"
)

# preparing a cursor object
cursorObject = dataBase.cursor()

query = "SELECT * FROM user"
cursorObject.execute(query)

myresult = cursorObject.fetchall()

for x in myresult:
    print(x)
    print('\n')

# disconnecting from server
db.close()
# db.commit()
```

    ('localhost', 'mysql.infoschema', 'Y', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', '', b'', b'', b'', 0, 0, 0, 0, 'caching_sha2_password', b'$A$005$THISISACOMBINATIONOFINVALIDSALTANDPASSWORDTHATMUSTNEVERBRBEUSED', 'N', datetime.datetime(2022, 8, 11, 12, 31, 10), None, 'Y', 'N', 'N', None, None, None, None)
    
    
    ('localhost', 'mysql.session', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'Y', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'Y', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', '', b'', b'', b'', 0, 0, 0, 0, 'caching_sha2_password', b'$A$005$THISISACOMBINATIONOFINVALIDSALTANDPASSWORDTHATMUSTNEVERBRBEUSED', 'N', datetime.datetime(2022, 8, 11, 12, 31, 10), None, 'Y', 'N', 'N', None, None, None, None)
    
    
    ('localhost', 'mysql.sys', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', 'N', '', b'', b'', b'', 0, 0, 0, 0, 'caching_sha2_password', b'$A$005$THISISACOMBINATIONOFINVALIDSALTANDPASSWORDTHATMUSTNEVERBRBEUSED', 'N', datetime.datetime(2022, 8, 11, 12, 31, 10), None, 'Y', 'N', 'N', None, None, None, None)
    
    
    ('localhost', 'root', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', 'Y', '', b'', b'', b'', 0, 0, 0, 0, 'caching_sha2_password', b'$A$005$%]_+uD<(G1P9j!\x13*r^\x11\x05SUAwVGDvXK5/i7c8McrlpZFWC4g4fPSE7EGUyn5S/t5', 'N', datetime.datetime(2022, 8, 11, 12, 31, 16), None, 'N', 'Y', 'Y', None, None, None, None)
    
    
    

# <li style="font-size:20pt;">Where Table</li>



```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="employees_data"
)

mycursor = mydb.cursor()

sql = "SELECT * FROM staff WHERE address ='Street 5 Jupiter'"

mycursor.execute(sql)

myresult = mycursor.fetchall()

for x in myresult:
    print(x)
```

    (1, 'Alian', 'Street 5 Jupiter')
    (2, 'Alian', 'Street 5 Jupiter')
    (3, 'Alia', 'Street 5 Jupiter')
    (4, 'Ali', 'Street 5 Jupiter')
    (5, 'john alia', 'Street 5 Jupiter')
    (6, 'Alian', 'Street 5 Jupiter')
    


```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="mysql"
)

mycursor = mydb.cursor()

sql = "SELECT * FROM user WHERE Password_reuse_history = ''"

mycursor.execute(sql)

myresult = mycursor.fetchall()

for x in myresult:
    print(x)
```

# <li style="font-size:20pt;">Order By Table</li>



```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="employees_data"
)

mycursor = mydb.cursor()

sql = "SELECT * FROM staff ORDER BY name"

mycursor.execute(sql)

myresult = mycursor.fetchall()

for x in myresult:
    print(x)
```

    (4, 'Ali', 'Street 5 Jupiter')
    (3, 'Alia', 'Street 5 Jupiter')
    (1, 'Alian', 'Street 5 Jupiter')
    (2, 'Alian', 'Street 5 Jupiter')
    (6, 'Alian', 'Street 5 Jupiter')
    (5, 'john alia', 'Street 5 Jupiter')
    


```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="employees_data"
)

mycursor = mydb.cursor()

sql = "SELECT * FROM staff ORDER BY name DESC"

mycursor.execute(sql)

myresult = mycursor.fetchall()

for x in myresult:
    print(x)
```

    (5, 'john alia', 'Street 5 Jupiter')
    (1, 'Alian', 'Street 5 Jupiter')
    (2, 'Alian', 'Street 5 Jupiter')
    (6, 'Alian', 'Street 5 Jupiter')
    (3, 'Alia', 'Street 5 Jupiter')
    (4, 'Ali', 'Street 5 Jupiter')
    

# <li style="font-size:20pt;">Delete Table</li>
 


```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="employees_data"
)

mycursor = mydb.cursor()

sql = "DELETE FROM staff WHERE name ='Imran'"

mycursor.execute(sql)

mydb.commit()

print(mycursor.rowcount, "record(s) deleted")
```

    0 record(s) deleted
    


```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="employees_data"
)

mycursor = mydb.cursor()

sql = "DELETE FROM staff WHERE name ='Alian'"

mycursor.execute(sql)

mydb.commit()

print(mycursor.rowcount, "record(s) deleted")
```

    3 record(s) deleted
    


```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="employees_data"
)

mycursor = mydb.cursor()

sql = "SELECT * FROM staff"

mycursor.execute(sql)

myresult = mycursor.fetchall()

for x in myresult:
    print(x)
```

    (3, 'Alia', 'Street 5 Jupiter')
    (4, 'Ali', 'Street 5 Jupiter')
    (5, 'john alia', 'Street 5 Jupiter')
    

# <li style="font-size:20pt;">Update Table</li>


```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="employees_data"
)

mycursor = mydb.cursor()

sql = "UPDATE staff SET address = 'Karachi, Pakistan' WHERE address = 'Street 5 Jupiter'"

mycursor.execute(sql)

mydb.commit()

print(mycursor.rowcount, "record(s) affected")
```

    3 record(s) affected
    


```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="employees_data"
)

mycursor = mydb.cursor()

sql = "UPDATE staff SET name = 'Thomas Edison' WHERE name = 'Raheel'"

mycursor.execute(sql)

mydb.commit()

print(mycursor.rowcount, "record(s) affected")
```

    0 record(s) affected
    

# <li style="font-size:20pt;">Limit</li>


```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="employees_data"
)

mycursor = mydb.cursor()

mycursor.execute("SELECT * FROM staff LIMIT 2")

myresult = mycursor.fetchall()

for x in myresult:
    print(x)
```

    (3, 'Alia', 'Karachi, Pakistan')
    (4, 'Ali', 'Karachi, Pakistan')
    


```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="employees_data"
)

mycursor = mydb.cursor()

mycursor.execute("SELECT * FROM staff LIMIT 4")

myresult = mycursor.fetchall()

for x in myresult:
    print(x)
```

    (3, 'Alia', 'Karachi, Pakistan')
    (4, 'Ali', 'Karachi, Pakistan')
    (5, 'john alia', 'Karachi, Pakistan')
    

# <li style="font-size:20pt;">Drop Table</li>



```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="books"
)

cur = mydb.cursor()
cur.execute("show tables")

for i in cur:
    print(i)
```

    ('book_catogary',)
    ('book_names',)
    ('book_namess',)
    ('book_writer',)
    


```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="books"
)

mycursor = mydb.cursor()

mycursor.execute("DROP TABLE book_catogary")


```


```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="books"
)

cur = mydb.cursor()
cur.execute("show tables")

for i in cur:
    print(i)
```

    ('book_names',)
    ('book_namess',)
    ('book_writer',)
    


```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="books"
)

mycursor = mydb.cursor()

mycursor.execute("DROP TABLE book_writer")


```


```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  password="admin",
  database="books"
)

cur = mydb.cursor()
cur.execute("show tables")

for i in cur:
    print(i)
```

    ('book_names',)
    ('book_namess',)
    

# Project of Database 


```python
import mysql.connector

db = mysql.connector.connect(host='localhost',user='root',password='admin')

cur=db.cursor()
cur.execute("create database if not exists schools")
cur.execute("use schools")
cur.execute("create table if not exists lms(Student_ID INT AUTO_INCREMENT PRIMARY KEY,Roll_Number varchar(200),Name varchar(200),Father_Name varchar(200),Mobile_Number varchar(200))")

def add_user():
    global cur
    rollNum=input("Enter Roll Number: ")
    Name = input("Enter Name: ")
    Fname = input("Enter Father Name: ")
    Num = input("Enter Mobile Number: ")
    cur.execute("insert into lms(Roll_Number,Name,Father_Name,Mobile_Number) values('{}','{}','{}','{}')".format(rollNum,Name,Fname,Num))
    db.commit()
    print("Data Successfully Added")
    

def show_user():
    global cur
    cur.execute("select * from lms")
    show_data=cur.fetchall()
    for show in show_data:
        print("ID: ",show[0])
        print("Roll Number: ",show[1])
        print("Name: ",show[2])
        print("Father Name: ",show[3])
        print("Mobile Number: ",show[4])
        print()
    
def delete_user():
    global cur
    r_num=input("Enter Roll Number For Delete User: ")
    cur.execute("delete from lms where Roll_Number = '{}'".format(r_num))
    print("Data Delete Successfully")
    db.commit()

def update_user():
    global cur
    rnum=input("Enter Roll Number For Searching: ")
    nam=input("Enter Name For Updating: ")
    fnam=input("Enter Father Name For Updating: ")
    num=input("Enter Mobile Number For Updating: ")
    cur.execute("update lms set Name='{}',Father_Name='{}',Mobile_Number='{}' where Roll_Number='{}'".format(nam,fnam,num,rnum))
    print("Data Successfully Changed")
    db.commit()

while 1:
    select=input("""1.) Add User \n2.) Show User \n3.) Delete User \n4.) Update User \n5.) Exit \t\t""")
    print()
    if select == '1':
        add_user()
    elif select == '2':
        show_user()
    elif select == '3':
        delete_user()
    elif select == '4':
        update_user()
    elif select == '5':
        print("Database Is Successfully Close")
        break
    else:
        print("Invalid Enter!")
```

    1.) Add User 
    2.) Show User 
    3.) Delete User 
    4.) Update User 
    5.) Exit 		1
    
    Enter Roll Number: 12345
    Enter Name: Muhammad
    Enter Father Name: Raheel
    Enter Mobile Number: 123456789
    Data Successfully Added
    1.) Add User 
    2.) Show User 
    3.) Delete User 
    4.) Update User 
    5.) Exit 		2
    
    ID:  1
    Roll Number:  45454
    Name:  Raheel
    Father Name:  Naseem
    Mobile Number:  123456789
    
    ID:  2
    Roll Number:  12345
    Name:  Muhammad
    Father Name:  Raheel
    Mobile Number:  123456789
    
    1.) Add User 
    2.) Show User 
    3.) Delete User 
    4.) Update User 
    5.) Exit 		5
    
    Database Is Successfully Close
    

********************************

<footer>

<p style="float:left; width: 85%; text-align:center;">
Copyright © Muhammad Raheel <br>
You can Contact me with this link or number <br>
mraheel.naseem@gmail.com <br>
+923452510056
</p>

</footer>
