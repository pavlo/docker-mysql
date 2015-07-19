# docker-mysql

Base image to run 5.6 MySQL database

## Thanks to tumtumcloud!

This stuff is based on excellent `https://github.com/tutumcloud/tutum-docker-mysql` image.


## Features

At start time the image creates a MySQL database and a user for it. The database name and user credentials are passed in as envirnment variables as shown below.

It can also create a second database, usually for tests which is sometimes handly if you need to run tests. Use `MYSQL_DB_TEST` envirnonment variable to give the test database a name.


## Environment variables

* `MYSQL_USER`: Set a specific username for the admin account (default 'admin').
* `MYSQL_PASS`: Set a specific password for the admin account.
* `MYSQL_DB`: Database name
* `MYSQL_DB_TEST`: Test database name
* `STARTUP_SQL`: Defines one or more SQL scripts separated by spaces to initialize the database. Note that the scripts must be inside the container, so you may need to mount them.

## Build image

`docker build -t yourid/mysql:latest .`

## Run it

Create data container:

`docker create -v /var/lib/mysql --name mysql_data ubuntu:14.04`

Run the MySQL container:

`docker run -d \
  --volumes-from mysql_data \
  -p 3306:3306 \
  -e "MYSQL_USER=auser" \
  -e "MYSQL_PASS=apass" \
  -e "MYSQL_DB=myappdb" \
  yourid/mysql:latest
