Full stack DevOps Setup

this repository includes a multi-stack setup for Laravel, wordPress and node.js app. Additionally, it has a docker compose file to deploy three containers WordPress, DB (MySQL) and a reverse proxy (Nginx). lastly, we have a CI/CD pipeline to test and deploy a node.js app by using GitHub actions.

###Service Included###
- WordPress
- MariaDB
- Nginx
- Env variables

###Clone the Repo by####

git clone https://github.com/jgamboa7/RevPanda.git
cd RevPanda

###Start Services###

docker-compose up -d

###Access to services###

http://localhost:8080

###SSL termination###
- set domain to point to cloudflare
- use "full (strict)"
- nginx need to be configure to forward X-Forwarded-Proto and respect HTTPS
- Block direct IP access on the server and allow only CloudFlare IPs

###Laravel####
- rooot: /var/www/laravel/public
- uses fastcgi_pass to PHP-FPM socket
- security headers added
- content caching enabled

###WordPress and Apache###
- security headers
- static file caching via mod_expires
- .htaccess support enabled

