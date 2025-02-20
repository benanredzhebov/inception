#The Dockerfile sets up a MariaDB database server
#Defines build arguments for the database
#Installs MariaDB(server+client).Creates a directory for MySQL and gives gull permissions.
#Configures MariaDB(1.Improves performens by disabling DNS, 2.Allow connection for any IP, 3.Enable network access)
#Initialize MariaDB database
#Copy a script for setting up the database
FROM alpine:3.21.2

ARG DB_NAME \
    DB_USER \
    DB_PASS \
    DB_ROOT

RUN apk update && apk add --no-cache mariadb mariadb-client

RUN mkdir /var/run/mysqld; \
    chmod 777 /var/run/mysqld; \
    { echo '[mysqld]'; \
      echo 'skip-host-cache'; \
      echo 'skip-name-resolve'; \
      echo 'bind-address=0.0.0.0'; \
    } | tee  /etc/my.cnf.d/docker.cnf; \
    sed -i "s|skip-networking|skip-networking=0|g" \
      /etc/my.cnf.d/mariadb-server.cnf

RUN mysql_install_db --user=mysql --datadir=/var/lib/mysql

EXPOSE 3306

COPY requirements/mariadb/conf/create_db.sh /tmp/create_db.sh
RUN sh /tmp/create_db.sh && rm /tmp/create_db.sh

#Runs the container as the mysql user for security
USER mysql
CMD ["/usr/bin/mysqld", "--skip-log-error"]
