FROM  ubuntu:23.10
LABEL maintainer="a.alnasani@outlook.com"

RUN apt update 

RUN apt install -y nginx  
RUN apt install php8.2 php8.2-fpm -y 
RUN rm -rf /var/www/html/index.html \
    && rm -rf /var/www/html/index.nginx-debian.html
RUN rm /etc/nginx/sites-available/default 
RUN rm /etc/nginx/sites-enabled/default
COPY default /etc/nginx/sites-available/
COPY default /etc/nginx/sites-enabled/
COPY index.php /var/www/html
# add php repo
#RUN add-apt-repository ppa:ondrej/php 
#RUN apt  -y --force-yes install php8.2  

EXPOSE 80
#ENTRYPOINT [ " echo" ]
#CMD ["/bin/bash", "-c", "echo FIRST COMMAND;echo SECOND COMMAND"]
#CMD ["nginx", "-g", "daemon off;"]
CMD ["/bin/bash", "-c", "php-fpm8.2 && nginx -g 'daemon off;'"]