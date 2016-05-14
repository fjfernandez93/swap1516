# Práctica 5

## Nueva base de datos


En primer lugar, creo una BD a la que añado una tabla:

![img1](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/1.png)

A continuación, añado algunos objetos a la tabla "datos":

![img2](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/2.png)

## Clonado manual con mysqldump

Antes de hacer la copia de la base de datos, he de bloquearla para que no se produzcan cambios (insercciones, borrados...) mientras
se está copiando:

![img3](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/4.png)

Ahora puedo proceder a hacer el "volcado" de la base de datos "expediente" en un archivo sql:

![img4](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/4.png)

Una vez hecho esto, vuelvo a desbloquear las tablas:

![img5](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/5.png)


En la máquina 2, copio el fichero sql de la máquina 1:

![img6](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/6.png)

Antes de añadir la información a mysql, tengo que crearme una base de datos con el mismo nombre (expediente):

![img7](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/7.png)

Por ultimo, con mysqldump ejecuto las sentencias sql del fichero en la nueva base de datos:

![img8](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/8.png)

## Configuración maestro-esclavo

Lo primero es hacer los cambios en el archivo /etc/mysql/my.conf tanto del maestro (máquina 1) como del esclavo (máquina 2).
Los cambios son:

- Comentar la línea bind-address 127.0.0.1
- Descomentar server-id (valor 1 para el maestro y valor 2 para el esclavo).
- Descomentar la línea log_bin = /var/log/mysql/bin.log

Como uso la versión 5.5.38, no añado información del maestro en el archivo de configuración del esclavo.

Reinicio los servicios en ambas máquinas y compruebo que no hay errores:

![img9](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/9.png)

![img10](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/10.png)

Lo siguiente es crear un usuario en el MySQL del maestro y darle permisos:

![img11](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/11.png)

Por último, añadimos la información del maestro mediante senticias SQL en el esclavo:

![img12](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/12.png)

Para comprobar que todo funciona correctamente, en primer lugar compruebo el "status" del esclavo.
La variable “Seconds_Behind_Master” tiene que ser 0:

![img13](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/13.png)

Ahoa hago unas insercciones en el maestro:

![img14](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/14.png)

Y compruebo que se han replicado los cambios en el esclavo:

![img15](https://github.com/fjfernandez93/swap1516/blob/master/pract5/img/15.png)


Nota:

- 192.168.1.30 y 192.168.1.31 son las IPs de las máquinas con el contenido web.
- 192.168.1.32 es la IP de la máquina con el balanceador de carga.
- 192.168.1.33 es la IP de la máquina que simula a un usuario accediendo a las webs.
