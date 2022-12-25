# using vNext image
FROM mcr.microsoft.com/mssql/server:2019-latest

#ARG SA_PASSWORD
#WORKDIR /tmp
# create directory within SQL container for database files
#RUN powershell -Command (mkdir C:\\SQLServer)

#copy the database files from host to container
#COPY ["mystore.mdf", "."]
#COPY ["mystore_log.ldf", "."]

# set environment variables
#ENV SA_PASSWORD=OneThing$123
#ENV ACCEPT_EULA=Y
#ENV attach_dbs="{'dbName':'mystore','dbFiles':['/tmp/mystore.mdf','/tmp/mystore_log.ldf']}"

#RUN apt-get update
#COPY . /tmp
COPY run-initialization.sh /tmp
COPY create-database.sql /tmp
COPY entrypoint.sh /tmp

CMD /bin/bash /tmp/entrypoint.sh
################################################
# Choose ubuntu version
#FROM mcr.microsoft.com/mssql/server:2019-latest

# Create app directory
#WORKDIR /usr/src/app

# Copy initialization scripts
#COPY . /usr/src/app
             
# Set environment variables, not to have to write them with docker run command
# Note: make sure that your password matches what is in the run-initialization script 
#ENV SA_PASSWORD OneThing$123
#ENV ACCEPT_EULA Y
#ENV MSSQL_PID Express

# Expose port 1433 in case accessing from other container
# Expose port externally from docker-compose.yml
#EXPOSE 1433

# Run Microsoft SQl Server and initialization script (at the same time)
#CMD /bin/bash ./entrypoint.sh
################################################
