# local-php-dev-server
A small php dev server you can run locally with docker

## Setup 

### Generate SSL Certificate

By default this will generate certificates for `localhost` if you wanted to change the domain then update the `domain` key in the `mkcert-docker-compose.yaml` file.

> Keep in mind if you do change the domain you will need to either update the name of the generated certificates or the `000-default.conf` file located in `./docker/php/apache`  
> - SSLCertificateFile /etc/apache2/ssl/localhost.pem
> - SSLCertificateKeyFile /etc/apache2/ssl/localhost-key.pem

Run the following command

    docker compose -f mkcert-docker-compose.yaml up 

This will generate the certificates in the `./docker/php/ssl` folder. Sometimes this can hang, if so just `Ctrl + C` a few times and should be good

Read the `README.md` in the `./docker/php/ssl` folder on how to stop the browser showing invalid certificate when using HTTPS

### Database Info
You can update the inital values in the `docker-compose.yaml` file under the `Setup the Database (mysql)` section.

    MYSQL_ROOT_PASSWORD: <Root Password>
    MYSQL_DATABASE: <Datebase Name>
    MYSQL_USER: <username>
    MYSQL_PASSWORD: <user password>

#### Start-up Scripts 
For scripts you would like to run on startup read the `README.md` in the `./db-dump` folder

## Running the Environment

### Create the environment

Run the following command to start the system

    docker compose up -d

You should now be able to 

### Tear down the environment
Run the following command to destory everything - Unless you have backed up the database you will lose everything when running this.

    docker compose down
