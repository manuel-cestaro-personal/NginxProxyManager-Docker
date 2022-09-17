# NginxProxyManager with Docker
Example of Nginx Proxy Manager (NPM) with Docker container.<br>
References: https://nginxproxymanager.com/guide/

## Objective
The goal is to create an NPM container that saves data persistently and easily copied to a backup. I also followed the best practices and insights from the official website.

## Start the containers
- clone the repo
- `mkdir .secrets && cd .secrets`
- `nano db_root_pwd.txt` --> write the pwd of the root user of mysql db
- `nano mysql_pwd.txt` --> write the pwd of the user used from NPM container
- `cd ..`
- `docker network create <Your_Network_Name>` --> create your docker network
- `nano docker-compose.yml` --> edit the file with `<Your_Network_Name>`
- if you want edit the `docker-compose.yml` with differents paths for the `.secret` directory or the `mount bind` volumes
- `docker-compose up -d`
- use `docker ps -a` to check the containers

## Other information about NPM
### Features
- Beautiful and Secure Admin Interface based on Tabler
- Easily create forwarding domains, redirections, streams and 404 hosts without knowing anything about Nginx
- Free SSL using Let's Encrypt or provide your own custom SSL certificates
- Access Lists and basic HTTP Authentication for your hosts
Advanced Nginx configuration available for super users
User management, permissions and audit log
### Hosting your home network
- Your home router will have a Port Forwarding section somewhere. Log in and find it
- Add port forwarding for port 80 and 443 to the server hosting this project
- Configure your domain name details to point to your home, either with a static ip or a service like DuckDNS or Amazon Route53
- Use the Nginx Proxy Manager as your gateway to forward to your other web based services

## Conclusions
A very simple but functional tool for hosting but also as a reverse proxy of an application!  &#128521;&#128406;