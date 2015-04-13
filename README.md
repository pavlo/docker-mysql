# docker-mysql

Base image to run 5.6 MySQL database

## Thanks to tumtumcloud

This stuff is based on excellent `https://github.com/tutumcloud/tutum-docker-mysql` image.


## Features

It creates two databases based on `MYSQL_DB` and `MYSQL_DB_TEST` environment variables. It also creates a user based on `MYSQL_USER` and `MYSQL_PASS` variables. The `root` with no password is also created but it allows to login from `localhost` only.


## Environment variables

`MYSQL_USER`: Set a specific username for the admin account (default 'admin').

`MYSQL_PASS`: Set a specific password for the admin account.

`MYSQL_DB`: Database name

`MYSQL_DB_TEST`: Test database name

`STARTUP_SQL`: Defines one or more SQL scripts separated by spaces to initialize the database. Note that the scripts must be inside the container, so you may need to mount them.




