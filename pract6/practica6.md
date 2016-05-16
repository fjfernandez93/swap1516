# Práctica 6

## Nueva base de datos

Después de instalar mdadm ejecutamos el comando:

    sudo fdisk -l

para ver que nombre tienen los discos que hemos añadido:

![img1](https://github.com/fjfernandez93/swap1516/blob/master/pract6/img/1.png)

Creamos el RAID 1 con el comando:

    sudo mdadm -C /dev/md0 --level=raid1 --raid-devices=2 /dev/sdb /dev/sdc

![img2](https://github.com/fjfernandez93/swap1516/blob/master/pract6/img/2.png)

Y le damos formato con:

    sudo mkfs /dev/md0

![img3](https://github.com/fjfernandez93/swap1516/blob/master/pract6/img/3.png)
Nota:

- 192.168.1.30 y 192.168.1.31 son las IPs de las máquinas con el contenido web.
- 192.168.1.32 es la IP de la máquina con el balanceador de carga.
- 192.168.1.33 es la IP de la máquina que simula a un usuario accediendo a las webs.
