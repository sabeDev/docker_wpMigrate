# Migrate Wordpress site




## Overview of actions
- Create the folder structure
- FTP your site contents down 
- Place the content into the 'src' folder
- Log into your mysql admin (on your website) and export your database as a SQL script
- Place the SQL script in the 'initdb.d' folder
- Create 

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

Copy files into 'src' folder
Generate your SQL script
Copy SQL script into the 'initdb.d' folder

Create an '.env' file at the root folder, with the contents similar to the below:
```
MYSQL_ROOT_PASSWORD=myDBPassword
MYSQL_USER=dbuser
MYSQL_PASSWORD=dbpassword
MYSQL_DB=dbname
```

