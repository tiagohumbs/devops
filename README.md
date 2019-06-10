# devops links

https://labs.play-with-docker.com/

https://dev.azure.com

https://hub.docker.com/




#abra o site https://labs.play-with-docker.com/,  faça login e crie uma instância.

#COMANDOS DOCKER

docker container run hello-world

docker container run debian bash --version


docker container run -it debian bash 
touch /arquivo.txt 
exit 


docker container run -it debian bash 
ls /c arquivo.txt 
ls: cannot access / arquivo.txt: No such file or directory 
exit

docker container ps


docker container run -p 8080:80 nginx 
# acompanhar logs de acesso 
# exemplo: 172.17.0.1 - - [09/Apr/2017:19:28:48 +0000] "GET / HTTP/1.1" 304 0 "-" "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/57.0.2987.133 Safari/537.36" "-" 
# CTRL-C para sair 


docker container run -p 8080:80 -v $(pwd)/not-found:/usr/share/nginx/html nginx
docker container run -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx


docker container run -d --name ex-daemon-basic -p 8080:80 -v $(pwd)/html:/usr/share/nginx/html nginx
docker container ps

docker container restart ex-daemon-basic

docker container os
# STATUS: Up 5 seconds

docker container stop ex-daemon-basic

docker container ps
# <nenhum container em execução>

docker container start ex-daemon-basic

docker container ps
# CONTAINER ID IMAGE COMMAND CREATED
STATUS PORTS NAMES
# 20536baa3d86 nginx "nginx -g 'daemon ..." 15 minutes ago Up 1 second 443/tcp, 0.0.0.0:8080->80/tcp ex-daemon-basic
