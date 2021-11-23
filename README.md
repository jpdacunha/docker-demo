Docker DEMONSTRATION
==========================================================
Attached files for Docker in a nutshell presentation

CLEANING DOCKER INSTALLATION
==========================================================

sudo docker system prune

sudo docker system prune -a

sudo docker volume prune

sudo docker images ls -a

sudo docker container ls -a

sudo docker volume ls

DEMO 01
==========================================================

sudo docker version

sudo docker images ls

sudo docker pull httpd

sudo docker run -dit --name httpd-jp -p 80:80 httpd

==> http://localhost

sudo docker container ls -a

sudo docker container stop httpd-jp

sudo docker container start httpd-jp

==> http://localhost

sudo docker container stop http-jp


DEMO 02 - Docker File
==========================================================

cd /home/dev/docker-demo/node-app/

npm install

sudo docker build -t dev/node-app .

sudo docker image ls

sudo docker run -p 49160:8080 -d --name node-app-jp dev/node-app

sudo docker ps

sudo docker logs node-app-jp

==> http://127.0.0.1:49160/

sudo docker exec -it node-app-jp /bin/bash

ps -aux

exit

sudo docker container stop node-app-jp


DEMO 03
==========================================================

sudo docker run -dit --name httpd-jp-volume -p 80:80 -v /home/dev/docker-demo/httpd-volume/:/usr/local/apache2/htdocs/ httpd:2.4

==> http://localhost

sudo docker volume ls

sudo docker container stop httpd-jp-volume


DEMO 04
==========================================================

cd /home/dev/docker-demo/docker-elk

docker-compose up -d

==> http://localhost:9200/

==> http://localhost:5601/

docker-compose up -d
