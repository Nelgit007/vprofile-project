#DB base image
FROM mysql:8.0.33
LABEL "Project"="containerdd"
LABEL "Author"="Nelson"

#set en variable
ENV MYSQL_ROOT_PASSWORD="vprodbpass"
#Create a DB with the name accounts
ENV MYSQL_DATABASE="accounts"

#Deploy sql file into the image being built (i.e initialiaze an instance)
ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql

