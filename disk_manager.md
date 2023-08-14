Cambiar el label del dispositivo USB

    sudo mlabel -i /dev/sda -s ::[NAME]
    sudo mlabel -i /dev/sda -s ::mediaLuis

    mlabel → comando que se usa para realizar operaciones en el sistema de archivos FAT
    -i → interactuar con la partición especificada
    -s ::"Label Here" → asignar la etiqueta a la partición.

---

Procedimiento para montar, desmontar. Al introducir el usb, podemos verificar con el comando 'df -h', que está montado, y con el comando 'lsblk', podemos ver todos los discos estén o no estén montados. Si queremos desmontar el usb, ejecutamos lo siguiente:

    sudo umount /media/luisam/usb

Si quiero volver a montar el usb

    sudo mount [path device] [path mountpoint]
    sudo mount /dev/sdc /media/luisam

Si quiero montar el disco o usb con permisos en específico, como por ejemplo el usuario 'Luis'

    sudo mount -o uid=1000,gid=1000 /dev/sdc /media/luisam

    -o → opciones de montaje

Si quiero que todos tengan permisos, ejecutamos lo siguiente:

    sudo mount -o umask=000 /dev/sdc /media/luisam

Para formatear un usb, primero lo desmontamos, luego establecemos el tipo de formato (en este caso es vfat, que corresponde a 'fat32'), y finalmente podríamos cambiarle la etiqueta(nombre) a nuestro usb.

    sudo umount /dev/sdc
    sudo mkfs.vfat /dev/sdc
    sudo mlabel -i /dev/sda -s ::mediaLuis
