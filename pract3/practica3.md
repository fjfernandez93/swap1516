# Práctica 3


Antes de nada, compruebo que nginx está instalado (aun no balancea carga):

![img1](https://github.com/fjfernandez93/swap1516/blob/master/pract3/img/1_-_comprobar_que_nginx_funciona.png)

Actualizo el archivo de configuración:

![img2](https://github.com/fjfernandez93/swap1516/blob/master/pract3/img/2_-_conf_nginx.png)

Ahora compruebo que nginx funciona redireccionando al html de las otras máquinas:

![img3](https://github.com/fjfernandez93/swap1516/blob/master/pract3/img/3_-_nginx_redirecciona.png)

Por último, desactivo la tarea crontab para que se aprecie el balanceo:

![img4](https://github.com/fjfernandez93/swap1516/blob/master/pract3/img/4_-_funciona_balance.png)
