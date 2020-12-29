# Nginx-Proxy-SSL-PHP

## Install Proxy

<code>git clone https://github.com/NamwanSoftTH/docker-nginx-proxy-ssl-php.git</code>

### Proxy

edit Environment variables in <code>.env</code>

if first start run command <code>docker network create {NETWORK in .env}</code>

##### Start

<code>docker-compose up -d</code>

##### Stop

<code>docker-compose down</code>

### Site

<code>cd {SITE_DIR}</code>
edit Environment variables in <code>.env</code>

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

## Add Site

copy directory <code>site-1</code> in root directory and rename directory to <code>{SITE_DIR_NEW}</code>

<code>cd {SITE_DIR_NEW}</code>
edit Environment variables in <code>.env</code>

if first start run command <code>docker network create web_network\_{SITE_NO in .env}</code>
