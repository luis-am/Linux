## Comando 'lsof'

Diferentes formas de usar el comando lsof.

	sudo lsof -i tcp
	sudo lsof -i tcp -P
	sudo lsof -iTCP -sTCP:LISTEN -P
	sudo lsof -iTCP -sTCP:ESTABLISHED -P
	sudo lsof -iTCP:22
	sudo lsof -i4TCP:22
	sudo lsof -i4TCP -sTCP:LISTEN

	-i: internet address
	-s: state 
	-P: muestra puertos en formato numerico
