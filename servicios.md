## Servicios

Ver la lista de servicios que se están ejecutando.

	sudo systemctl --type=service --state=running

Ver la lista de servicios en diferentes estados.

	sudo systemctl --type=service --state=failed,exited

Ver la lista de servicios habilitados o deshabilitados.

	sudo systemctl -list-unit-files --state=enabled
	sudo systemctl -list-unit-files --state=disabled

Ver que servicios han fallado en el arranque.

	sudo systemctl -list-unit-files --state=enabled,failed

Directorios en donde se encuentran las unidades de systemd.

	/etc/systemd/system
	/run/systemd/system
	/lib/systemd/system

Para editar un unit file de un servicio.

	systemctl edit [SERVICE]
