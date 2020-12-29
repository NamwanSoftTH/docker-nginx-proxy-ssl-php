# Nginx-Proxy-SSL-PHP

## Install Proxy

<code>git clone https://github.com/NamwanSoftTH/docker-nginx-proxy-ssl-php.git</code>

### Proxy

Environment variables in <code>.env</code>
if first start run command <code>docker network create {NETWORK in .env}</code>

##### Start

<code>docker-compose up -d</code>

##### Stop

<code>docker-compose down</code>

### Site

cd {SITE_DIR}
Environment variables in <code>.env</code>
if first start run command <code>docker network create web_network\_{SITE_NO in .env}</code>

##### Start

<code>docker-compose build</code>
<code>docker-compose up -d</code>
or
<code>docker-compose up -d build</code>

##### Stop

<code>docker-compose down</code>
or
<code>docker-compose down --rmi {continer_name|all}</code>
