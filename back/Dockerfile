# Pull base image.
FROM mysql:latest


# Set the root password
ENV MYSQL_ROOT_PASSWORD password 
# Execute the SQL script at container startup
ADD script.sql /docker-entrypoint-initdb.d

# Expose ports.
EXPOSE 3306