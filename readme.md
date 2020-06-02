# Migrate Wordpress site




## Overview of actions
- Create the folder structure
- FTP your site contents down 
* Place the content into the src folder
4. Log into your mysql admin (on your website) and export your database as a SQL script
5. Place the SQL script in the initdb.d folder
6. Create 

## Detailed Instructions
1. Create the following folder structure:
```
----root 
        |--src: source folder for wordpress files
        |
        |--db: folder for db files
            |--initdb.d: folder for sql script to create db
            |--data: empty folder for db files (actually this should get created automatically)

```
So manually create folders:
* src
* db/initdb.d

2. No detail for FTP 
3. Copy files into 'src' folder

6. Create an ENV file with the contents similar to the below:
```
MYSQL_ROOT_PASSWORD=myDBPassword
MYSQL_USER=dbuser
MYSQL_PASSWORD=dbpassword
MYSQL_DB=dbname
```

