## Comando 'xargs'

Ejemplo, por defecto el comando que utiliza xargs es 'echo', la opción 't', es para mostrar en la salida el comando en una sola línea.

	seq 5 | xargs
	seq 5 | xargs -t
		output: echo 1 2 3 4 5
		output: 1 2 3 4 5

Darle un alias a la salida del primer comando.

	ls | xargs -I {} echo '/home/luisam/{}'

Aquí hay otro ejemplo.

	ls | cut -d. -f1 | xargs -I {} mv {}.txt {}.py

Supongamos que queremos eliminar archivos de tipo texto, de esta forma se ejecuta el comando mucho más rápido que si lo hiciéramos con 'find -exec'.

	find . -type f -name "*.txt" -exec rm {} +
	find . -type f -name "*.txt" | xargs rm

Renombrando archivos usando xargs.

	find . -type -f | cut -d. -f1 | xargs -I {} mv {}.txt {}.py
	find . -type f | sed 's/\.md\.txt$//' | xargs -I {} mv {}.md.txt {}.py
	find . -type f -name "*.txt.pdf" | sed 's/\.txt\.pdf$//' | xargs -I {} mv {}.txt.pdf {}.py
