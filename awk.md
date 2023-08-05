## Comando 'awk'

Visualizar una columna en especifico con el comando 'awk'

	ls -l | awk '{print $n}'
		n: es el numero de la columna que deseo visualizar

	awk -F ',' '{print $#}' [FILENAME]
		-F: delimitador

	awk '{print $1, $3}' [FILENAME]
	
Contar el numero de columnas tomando como referencia la primera linea 'NR==1'

	ps aux | awk 'NR==1 {print NF}'

Si quiero imprimir el tercer campo de la linea 1

	ps aux | awk 'NR==1 {print $2}'

Si quiero imprimir el ultimo campo de la linea 1

	ps aux | awk 'NR==1 {print $NF}'

Imprimir el cuarto campo de la linea 3, tomando en cuenta como delimitador el caracter '-'

	awk -F '-' 'NR==3 {print $4}' [FILENAME]

Imprimir el file tal como si fuera el comando 'cat'

	awk '{print $0}' [FILENAME]
	awk '{print $}' [FILENAME]

Imprimir las columnas 1, 2 y 3 separados de un guion '-', teniendo como delimitador ':' del archivo /etc/passwd; importante dentro de los brackets se pone entre comillas.

	awk -F ':' '{print $1"-"$2"-"$3}' [FILENAME]
	awk -F ':' '{print $1"-"$2"-"$3}' /etc/passwd

Cambiar el delimitador ":" por '_' en la salida de los campos 1, 3 y 5 del archivo /etc/password

	awk 'BEGIN{FS=":"; OFS="_"} {print $1,$3,$5}' [FILENAME]
	awk 'BEGIN{FS=":"; OFS="_"} {print $1,$3,$5}' /etc/passwd

Mostrar la salida del ultimo campo 'NF' tomando como condicion las lineas que solo empiezen con '/'; si queremos que solo salgan salidas unicas agregamos al final la opcion 'uniq'

	awk -F "/" '/^\// {print $NF}' /etc/shells
	awk -F "/" '/^\// {print $NF}' /etc/shells | uniq
