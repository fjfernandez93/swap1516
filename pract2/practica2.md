# Práctica 2


Hago el primer rsync entre los dos servidores (desde la máquina 2), lo que copia el archivo "hola.html" en la máquina 2.

![img1](https://github.com/fjfernandez93/swap1516/blob/master/pract2/img/p2_-_1.png)

Ahora genero un par de claves pública/privada DSA, y exporto la pública a la máquina 1 para poder hacer rsync sin tener
que introducir las credenciales por ssh:

![img2](https://github.com/fjfernandez93/swap1516/blob/master/pract2/img/p2_-_2.png)

Por último, añado la tarea de sincronizacion a crontab para que se haga de forma automática cada minuto:

![img3](https://github.com/fjfernandez93/swap1516/blob/master/pract2/img/p2_-_3.png)
