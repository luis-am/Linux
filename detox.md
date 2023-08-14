### Comando 'detox'

Para renombrar directorios, subdirectorios y archivos de manera recursiva, en el cual contengan espacios en sus nombres, ejecutamos el siguiente comando, esto reemplará los espacios por underscore, bastante útil cuando hay muchos files de por medio con espacios en sus nombres.

	detox -nrv [PATH]
	detox -rv [PATH]

	-n: vista previa de cómo se van a hacer los cambios, útil antes de ejecutar el comando.
	-r: recursivo
	-v: verbose
