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

Nota:

- 192.168.1.30 y 192.168.1.31 son las IPs de las máquinas con el contenido web.
- 192.168.1.32 es la IP de la máquina con el balanceador de carga.
- 192.168.1.33 es la IP de la máquina que simula a un usuario accediendo a las webs.
