## Comando 'dd'

Copiar y pasar a mayuscula el contenido de un archivo

	dd if=test of=out conv=ucase

	if: input file
	of: outpu file
	conv: convertir

Copiar y cambiar a unicode europeo

	dd if=test of=test2 conv=ebcdic
