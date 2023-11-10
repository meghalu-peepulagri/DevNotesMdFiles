1) Dev
3) Staging
3) Production

EC2 - Ubuntu
Dev Lightsail - Ubuntu
Staging Lightsail - Ubuntu

1) Create Users
    sudo add user
2) Create ssh keys
     ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
3) Add ssh key to git
     cat id_rsa.pub  to git
4) Clone git project
     git clone sshe:repo
5) Setup node using NVM

      Option 3 — Installing Node Using the Node Version Manager
      https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-20-04

6) Setup pm2 with pm2 ecosystem
    
    https://pm2.io/docs/runtime/guide/installation/

    ecosystem.config.js

 mv api-farmlogs.peepulagri.com staging-api-farmlogs.peepulagri.com

1. DEV 
   ubuntu@43.205.227.24

2. Staging
   ubuntu@3.108.161.72


130.12.23.34:3000/v1.0
dev-api-formalogs.peepul.agri .com


DNS - DOMAIN NAME SYSTEM

API1 -  3000
API2 - 4000
API3 - 5000
API4 - 6000


https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04

ngnix server

dev-api.peepuagr.com -> 3000
staging-api.peepuagr.com -> 4000
prod-api.peepuagr.com -> 4000



cd /etc/nginx/sites-available/




sudo nano staging-api-farmlogs.peepulagri.com
```
server {
    server_name staging-api-farmlogs.peepulagri.com;

    location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
        fastcgi_read_timeout 540;
        proxy_connect_timeout 3000s;
        proxy_send_timeout   3000;
        proxy_read_timeout   3000;
    }
}
server {
    listen 80;
    server_name staging-api-farmlogs.peepulagri.com;
}
```



