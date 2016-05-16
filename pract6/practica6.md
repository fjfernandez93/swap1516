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

Para crear el directorio donde se montará el RAID:
    sudo mkdir /dat
    sudo mount /dev/md0 /dat

Para comprobar que todo está correcto, ejecuto:

    sudo mount

![img4](https://github.com/fjfernandez93/swap1516/blob/master/pract6/img/4.png)

y:

sudo mdadm --detail /dev/md0

![img5](https://github.com/fjfernandez93/swap1516/blob/master/pract6/img/5.png)

Para finalizar el proceso de creación del RAID, modifico el archivo /etc/fstab para que se monte al arrancar el sistema:

![img6](https://github.com/fjfernandez93/swap1516/blob/master/pract6/img/6.png)

Nota:

- 192.168.1.30 y 192.168.1.31 son las IPs de las máquinas con el contenido web.
- 192.168.1.32 es la IP de la máquina con el balanceador de carga.
- 192.168.1.33 es la IP de la máquina que simula a un usuario accediendo a las webs.
