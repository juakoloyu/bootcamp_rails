# README

Este es un proyecto base para trabajar con Ruby on Rails en Docker. 

* Ruby version: 3.0.3 & Rails 7.0.2

Generamos una vez los contenedores para postgres y para el servidor de aplicaciones.

* docker-compose build

Corremos los contenedores

* docker-compose up

Para ingresar a la consola del docker y/o consola interactiva de Rails:
Desde VSCode (con la extensión de Docker instalada) nos dirigimos al menú de Docker y damos clic derecho sobre el servidor de aplicación y luego "Attach Shell"

![Image text](https://github.com/juakoloyu/bootcamp_rails/blob/main/public/docker.jpg)