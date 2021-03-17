#Comandos Docker

Para contruir el contenedor
docker build --no-cache -t mymaria -f Dockerfile .


Para hacer correr el contenedor
docker run -p 3306:3306  --name dbalpine -e MYSQL_ROOT_PASSWORD=pwd -d mymaria

MYSQL_ROOT_PASSWORD representa la contraseña del usuario "root" que puede ser cambiada de ser necesario.


Para crear y llenar la base de datos de la aplicación "bd_hosp"
docker exec -i dbalpine sh -c 'exec mysql -uroot -p"$MYSQL_ROOT_PASSWORD" < /home/data/dbhlocalidades.sql -v'

# Valdación base de datos

Ingresar al contendeor:
docker exec -ti dbalpine sh

Ingresar a MariaDB

mysql -p -> (Luego escribir la contraseña asignada)

show databases; (Validar que la bd ese creada)


#Fuente principal:

https://hub.docker.com/_/mariadb
