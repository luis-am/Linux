## Comando 'find'

 El siguiente comando lo que hace es buscar en el directorio actual los archivos que tengan como nombre [FILENAME], aquí puede haber caracteres comodines, luego de eso la opcion '-exec', seguido del comando al cual se va a ejecutar teniendo como argumentos los archivos encontrados, el marcado [] representa cada archivo encontrado. El símbolo '+' indica la finalización del comando '-exec'.
	
	find . -name [FILENAME] -exec [COMMAND] [] +

Si queremos invertir la búsqueda, es decir buscar los valores que no coincidan con la condición.

	find . -not -name [FILENAME]
