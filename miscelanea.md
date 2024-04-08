input: bash -c '[COMANDO]'
input: bash -c 'echo Hola mundo'

Imprimir la información de la distribución, 'lsb' significa 'Linux Standard Base'.

	cat /etc/os-release
	cat /etc/lsb-release

Verificar el modo de booteo, si el resultado arroja '64' significa que está en modo x64 UEFI, si arroja 32 está 32-bit UEFI

	cat /sys/firmware/efi/fw_platform_size

---

### Variables de entorno

Ver el valor de la variable.

	prinenv [VARIABLE]

	printenv SHELL
	printenv HOME
	printenv USER

Crear una variable local.

	[VARIABLE]:[VALOR]

	minombre=luis
	echo $minombre
	string='Esta es una linea de texto.'
	echo $string

Para convertir una variable a variable global.

	export [VARIABLE]

	export minombre
	export mystring

Eliminar una variable de entorno.

	unset [VARIABLE]
	unset minombre
	unset mystring

Variables de entorno globales más comunes.

	echo $USER
	echo $LANG
	echo $HOME
	echo $RANDOM
	echo $UID
	echo $PATH

Editar archivos que tienen permisos de root con la variable de entorno local.

    SUDO_EDITOR=/usr/bin/vim
    SUDO_EDITOR=/usr/local/bin/nvim
    export SUDO_EDITOR
    echo 'export SUDO_EDITOR=/usr/bin/vim >>' ~./bashrc

Editar un archivo remoto:

    nvim scp://user@x.x.x.x//home/remote_user/file



Editar el tamaño de fuente:

    setfont Lat38-TerminusBold28x14.psf.gz

Ruta de default console fonts:

	/etc/default/console-setup

---

### VIRSH

Crear una nueva red nat

    sudo virsh net-create [PATH XML FILE]
    sudo virsh net-create ~/nat2.xml
    sudo virsh net-list

Configurar interface virtual 'virbr1', una vez editada tenemos que redefinirla

    sudo virsh net-edit --network [NETWORK]
    sudo virsh net-edit --network nat2
    sudo virsh net-define [PATH]
    sudo virsh net-define /etc/libvirt/qemu/networks/nat2.xml

Listar todas las redes disponibles

    sudo virsh net-list --all

Iniciar una red virtual

    sudo virsh net-start --network [NETWORK]
    sudo virsh net-start --network nat2

Detener la red virtual

    sudo virsh net-destroy --network [NETWORK]
    sudo virsh net-destroy --network nat2

Desactiva el autostart de una red

    sudo virsh net-autostart --network [NETWORK] --disable
    sudo virsh net-autostart --network nat2 --disable

Eliminar por completo la red virtual

    sudo virsh net-undefine --network [NETWORK]
    sudo virsh net-undefine --network nat2

Ruta de los archivos de red

    /etc/libvirt/qemu/networks

Listar todas las máquinas virtuales, así como también las máquinas que están corriendo

    sudo virsh list --all
    sudo virsh --state-running

Iniciar una máquina virtual

    sudo virsh start [MV NAME]
    sudo virsh start Alma

---

### Generador de UUID's

Generar UUID's

    uuidgen

---

### Cambiar contraseña

Cambiar contraseña recibiendo entrada stdin

    echo 'user:user' | chpasswd
    echo 'luisam:luisam' | chpasswd

---

### Uso de sshpass

Uso básico

    sshpass -p [PASSWORD] ssh [USER@IP]
    sshpass -p root ssh root@10.0.0.1

Uso básico sin preguntar el hostchecking

    sshpass -p [PASSWORD] ssh -o StrictHostKeyChecking=no [USER:IP]
    sshpass -p root ssh -o StrictHostKeyChecking=no root@10.0.0.12

Tomando como entrada un file

    sshpass -f [FILE] ssh [USER:IP]
    sshpass -f passw.txt ssh root@10.0.0.12

Tomando como entrada el valor de una variable

    SSHPASS="[FILE]" sshpass -e [USER:IP]
    SSHPASS="passwd" sshpass -e root@10.0.0.12

---

### Gestión de trusted-keys

Listar todas las GPG keys

    sudo apt-key list
