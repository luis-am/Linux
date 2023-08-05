## Comando 'sort'

Este es un ejemplo para contar el numero de columnas con awk

	sudo lsof -itcp | awk '{print NF}' | sort | head -1
	ps -aux | awk '{print NF}' | sort | head -1

