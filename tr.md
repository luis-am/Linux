## Comando 'tr'

tr = translate caracters

	input: echo 'This is a line of text' | tr 'i' 'I'
	output: ThIs Is a lIne of text

Elimina caracteres.

	input: echo 'This is a line of text' | tr - d 'e'
	output: This is a lin of txt

Squeeze caracteres repetidos.

	input: echo 'Thiiis is aaaaa line ooooof text' | tr - s 'aeio'
	output: This is a line of text

Convertir de mayusculas a minusculas o viceversa.

	input: echo 'This is a line of text' | tr '[:lower:]' '[:upper:]'
	output: THIS IS A LINE OF TEXT

Eliminar caracter excepto el especificado.

	input: echo 'This is a line of text' | tr -cd 'text'
	output: etext

Separa todo lo que es numero.

	input: echo 'This is a strong and complicated password - 1234' | tr -cd '[:digit:]'
	output: 1234
