# Migrate Wordpress site

## Instructions
Create the following folder structure:
 
```
----root 
        |--src: source folder for wordpress files
        |
        |--db: folder for db files
            |--initdb.d: folder for sql script to create db
            |--data: empty folder for db files (actually this should get created automatically)

```

## Overview of actions
1. FTP your site contents down 
2. Place the content in the src folder
3. Log into your mysql admin (on your website) and export your database as a SQL script
4. Place the SQL script in the initdb.d folder
5. Create 



So manually create folders:
* src
* db/initdb.d

Create an ENV file with the contents similar to the below:
```
MYSQL_ROOT_PASSWORD=myDBPassword
MYSQL_USER=dbuser
MYSQL_PASSWORD=dbpassword
MYSQL_DB=dbname
```

