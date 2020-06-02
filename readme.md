# Migrate Wordpress site




## Overview of actions
- Create the folder structure
- FTP your site contents down 
- Place the content into the `src` folder
- Log into your mysql admin (on your website) and export your database as a SQL script
- Place the SQL script in the `initdb.d` folder
- Create the `.env` file
- Alter the `nginx-conf` with your domain name

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
2. So manually create folders:
- src
- db/initdb.d

3. Copy files into `src` folder
4. Generate your SQL script
5. Copy SQL script into the `initdb.d` folder
6. Create an `.env` file at the root folder, with the contents similar to the below:
```
MYSQL_ROOT_PASSWORD=myDBPassword
MYSQL_USER=dbuser
MYSQL_PASSWORD=dbpassword
MYSQL_DB=dbname
```
7. Alter the line `server_name www.example.co.uk;` in the `nginx-conf/nginx.conf` to your domain name
8. The solution should now look like:
```
----root 
        |--db: folder for db files
            |--initdb.d: folder for sql script to create db
                db.sql: a sql script to create your database
            |--data: empty folder for db files (actually this should get created automatically)
        |--src: source folder for wordpress files
        .env: environment variables file
        docker-compose.yml: the docker compose file
        readme.md: this readme file   
```
9. Change directory to your solution folder and enter: `docker-compsoe up -d`
10. if something goes wrong, stop the container and clear the contents of the folder:
- db/data/
