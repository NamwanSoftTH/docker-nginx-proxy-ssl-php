### Proxy

First Start
docker network create web_proxy

#### Start Proxy

docker-compose build
docker-compose up -d
docker-compose up -d build

#### Stop Proxy

docker-compose down
docker-compose down --rmi {continer_name|all}

### Site

cd {SITE_DIR}

config Environment variables in .env
First Start
docker network create web_network\_{SITE_NO in .env}

#### Start Site

docker-compose build
docker-compose up -d
docker-compose up -d build

#### Stop Site

docker-compose down
docker-compose down --rmi {continer_name|all}
