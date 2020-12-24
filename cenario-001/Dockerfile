# docker image build --tag teste-allan-ecs .
# docker container run -it --rm -p 8080:80 --name teste-allan-ec2-v1 teste-allan-ecs
FROM php:5.6-apache

LABEL maintainer="Allan Gonçalves da Cruz <allangcruz@gmail.com>"

COPY index.html /var/www/html

WORKDIR /var/www/html

EXPOSE 80

RUN service apache2 start