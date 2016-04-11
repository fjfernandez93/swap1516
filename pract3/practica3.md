# Práctica 3

## nginx

Antes de nada, compruebo que nginx está instalado (aún no balancea carga):

![img1](https://github.com/fjfernandez93/swap1516/blob/master/pract3/img/1_-_comprobar_que_nginx_funciona.png)

Actualizo el archivo de configuración:

![img2](https://github.com/fjfernandez93/swap1516/blob/master/pract3/img/2_-_conf_nginx.png)

Ahora compruebo que nginx funciona redireccionando al html de las otras máquinas:

![img3](https://github.com/fjfernandez93/swap1516/blob/master/pract3/img/3_-_nginx_redirecciona.png)

Por último, desactivo la tarea crontab para que se aprecie el balanceo:

![img4](https://github.com/fjfernandez93/swap1516/blob/master/pract3/img/4_-_funciona_balance.png)

Nota:

- 192.168.1.30 y 192.168.1.31 son las IPs de las máquinas con el contenido web.
- 192.168.1.32 es la IP de la máquina con el balanceador de carga.
- 192.168.1.33 es la IP de la máquina que simula a un usuario accediendo a las webs.

##haproxy

Primero, hago los cambios en el archivo de configuración (/etc/haproxy/haproxy.cfg):

![img5](https://github.com/fjfernandez93/swap1516/blob/master/pract3/img/5.png)

Inicio el servicio:

![img6](https://github.com/fjfernandez93/swap1516/blob/master/pract3/img/6.png)

Compruebo que balancea:

![img7](https://github.com/fjfernandez93/swap1516/blob/master/pract3/img/7.png)
