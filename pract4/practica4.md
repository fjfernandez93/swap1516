# Práctica 4

## Apache Benchmark

En primer lugar creo el documento HTML de prueba:

![img1](https://github.com/fjfernandez93/swap1516/blob/master/pract4/1.png)

Ejecuto el comando de Apache Benchmark, indicando que haga 1000 peticiones de 5 en 5 concurrentemente, a la IP de la máquina que balancea:

![img2](https://github.com/fjfernandez93/swap1516/blob/master/pract4/2.png)

La salida que produce es:

![img3](https://github.com/fjfernandez93/swap1516/blob/master/pract4/3.png)

Por último, ejecuto el benchmark 10 veces y hago la media y la desviación típica de los resultados interesantes:

![img4](https://github.com/fjfernandez93/swap1516/blob/master/pract4/4.png)


##haproxy

Primero, hago los cambios en el archivo de configuración (/etc/haproxy/haproxy.cfg):

![img5](https://github.com/fjfernandez93/swap1516/blob/master/pract3/img/5.png)

Inicio el servicio:

![img6](https://github.com/fjfernandez93/swap1516/blob/master/pract3/img/6.png)

Compruebo que balancea:

![img7](https://github.com/fjfernandez93/swap1516/blob/master/pract3/img/7.png)





Nota:

- 192.168.1.30 y 192.168.1.31 son las IPs de las máquinas con el contenido web.
- 192.168.1.32 es la IP de la máquina con el balanceador de carga.
- 192.168.1.33 es la IP de la máquina que simula a un usuario accediendo a las webs.
