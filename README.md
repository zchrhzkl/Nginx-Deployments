# NodeJS + Nginx + LetsEncrypt
Reverse Proxy using Nginx and SSL using LetsEncrypt

## Configure the Variables
```/.env```
## Configure the Nginx hosts
```/data/nginx/example.com.conf```

```/data/nginx-init/example.com.conf```

## Start the web apps Container
```docker-compose up -d app```

## Initialize the SSL configuration
```docker compose -f docker-compose-init.yml up -d```

## Start the Nginx Container
```docker-compose up -d nginx --remove-orphans```

## Setup Crontab
```sudo crontab -e```

Change the {USER} with the active user 

```15 3 * * * docker compose up -f /home/{USER}/deploy-web/docker-compose.yml certbot-renew```