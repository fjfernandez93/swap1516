# Práctica 4

## Apache Benchmark


Ejecuto 10 veces el comando

    ab -n 1000 -c 5 http://192.168.1.30

indicando que haga 1000 peticiones de 5 en 5 concurrentemente, a la IP de la máquina servidora 1.
Los datos relevantes son:

![img1](https://github.com/fjfernandez93/swap1516/blob/master/pract4/ab-M1.png)

Vuelvo a ejecutar el comando 10 veces, esta vez sobre la IP de la máquina que balancea (192.168.1.32), corriendo Nginx:

![img3](https://github.com/fjfernandez93/swap1516/blob/master/pract4/ab-granja-nginx.png)

Por último, lo vuelvo a ejecutar sobre el balanceador, con haproxy:

![img4](https://github.com/fjfernandez93/swap1516/blob/master/pract4/ab-granja-haproxy.png)


##haproxy






Nota:

- 192.168.1.30 y 192.168.1.31 son las IPs de las máquinas con el contenido web.
- 192.168.1.32 es la IP de la máquina con el balanceador de carga.
- 192.168.1.33 es la IP de la máquina que simula a un usuario accediendo a las webs.
