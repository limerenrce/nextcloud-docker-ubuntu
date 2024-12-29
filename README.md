# Nextcloud with MariaDB - Docker Setup

This project sets up a Nextcloud instance using Docker with MariaDB as the database. The configuration uses Docker Compose to deploy both services: the database (MariaDB) and the Nextcloud application.

## Requirements

Before running the setup, ensure you have the following:

- Docker installed on your system.
- Docker Compose installed.
- Ubuntu or a Linux-based system (the paths are configured for Ubuntu).
- An internet connection to download the required Docker images.

## Setup Instructions

1. **Clone this repository**

```
git@github.com:limerenrce/nextcloud-docker-ubuntu.git
```

Inside your home directory. create a file named docker-compose.yml. I provide the example file. Please check it. 2. **Adjust the paths**
Replace /home/user/ with your actual Ubuntu username.
For example, if your username is lime, you should change the paths to:
/home/lime/nextcloud/datadb:/var/lib/mysql
/home/lime/nextcloud/data:/var/www/html

3. **Change environment variable values**
   Adjust the following environment variables to match your desired configuration:

- MYSQL_ROOT_PASSWORD: Set a secure password for the MariaDB root user.
- MYSQL_PASSWORD: Set a password for the Nextcloud database user.
- MYSQL_DATABASE: Set the name of the database that Nextcloud will use.
- MYSQL_USER: Set the database user that Nextcloud will use

4. **Start the containers**
   Run the following command in the directory where the docker-compose.yml file is located:

```
docker-compose up -d
```

This command will download the necessary Docker images and start the Nextcloud and MariaDB containers in the background.

5. **Access Nextcloud**
   After the containers are up and running, you can access the Nextcloud instance by opening your web browser and going to:
   http://localhost:8080
   The first time you access Nextcloud, you'll be prompted to complete the setup. Use the database credentials you've set in the environment variables during the setup process.

## Cuztomizing Your Setup

You can customize this Docker Compose configuration further by adding more services, changing port mappings, or modifying volumes.

For more advanced Nextcloud configurations, refer to the [official documentation](https://hub.docker.com/_/nextcloud).
