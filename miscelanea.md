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
