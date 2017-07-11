# openmrs

**Docker commands:**
```
docker run --name openmrs-mysql -v /var/lib/mysql -e MYSQL_ROOT_PASSWORD=test -d mysql:5.6
docker run --name openhmis-test --link openmrs-mysql:mysql -it -p 8080:8080 openhmis/openmrs-docker:latest
```

**Initial setup:**

Check that tomcat is running in [http://localhost:8080].

Go to [http://localhost:8080]

Select Advanced installation

Change database connection string to: jdbc:mysql://mysql:3306/@DBNAME@?autoReconnect=true&sessionVariables=default_storage_engine=InnoDB&useUnicode=true&characterEncoding=UTF-8

Select 'No' when asked for existing OpenMRS database. Enter username/password as root/$MY_SQL_ROOT_PASSWORD

Select 'No' when asked for existing OpenMRS user. Enter username/password as root/$MY_SQL_ROOT_PASSWORD

Change default password for admin user
