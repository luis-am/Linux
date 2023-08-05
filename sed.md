## Comando 'sed'

Reemplazar directamente la primera coincidencia en cada linea.

	sed -i 's/oldword/newword/' [FILE]
	i- : input in place

Reemplazar de maner global.

	sed -i 's/oldword/newword/g' [FILE]

Para reemplazar comentarios por ejemplo con caracteres especiales.

	sed 's/#.*//g' [FILE]

Para reemplazar espacios por cualquier otro caracter.

	sed 's/\s/newword/g' [FILE]

Para eliminar cuando se encuentra una coincidencia en la linea.

	sed '/[OLDWORD]/d' [FILE]

Para visualizar hasta la linea especificada.

	sed 'q' [FILE]

Para eliminar las lineas en blanco.

	sed '/^$/d' [FILE]
