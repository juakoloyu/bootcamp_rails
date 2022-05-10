# Rails 7 Base con Docker

Este es un proyecto base para trabajar con Ruby on Rails en Docker. 

* Ruby version: 3.0.3 & Rails 7.0.2

## Pasos para la ejecución y uso 
Generamos una vez los contenedores para postgres y para el servidor de aplicaciones.
```
$ docker-compose build
```
Corremos los contenedores. Con esto ya debería funcionar el servidor (puma) y postgres.

```
$ docker-compose up
```

## Aclaración 1
Este proyecto está configurado para trabajar con Postgres, por lo tanto, hay que ejecutar los comandos correspondientes para crear la o las bases de datos de desarrollo, prueba o producción que se especifican en el archivo database.yml.

Para ingresar a la consola del docker y/o consola interactiva de Rails:
Desde VSCode (con la extensión de Docker instalada) nos dirigimos al menú de Docker y damos clic derecho sobre el servidor de aplicación y luego "Attach Shell".

![Image text](https://github.com/juakoloyu/bootcamp_rails/blob/main/public/docker.jpg)

```
$ bundle exec rails db:create

# Si tuvieramos migraciones:

$ bundle exec rails db:migrate
```
## Aclaración 2: Para tener en cuenta a futuro
Si se cambia algun archivo de configuración como database.yml, config.rb, development.rb, etc. será necesario reiniciar el contenedor de rails.

## Aclaración 3: Si no se desea utilizar Postgres
Si se desea trabajar con SQLite u otro motor de bases de datos habría que agregar la gema correspondiente en el Gemfile, adaptar la configuración en el database.yml; y reiniciar el contenedor (Como se aclaró en el paso 2).

## Aclaración 4: Cuando se añade una nueva gema
Por cada gema nueva que se añada es necesario apagar el contenedor de Rails y ejecutar nuevamente 
```
$ docker-compose build

$ docker-compose up
```
