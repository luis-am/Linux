## Expresiones regulares

Trabajando con expresiones regulares con el comando grep.

Match any one character

	grep 'f.x' [FILE]

\* match any number of previous (including 0)

	grep 'f.*x' [FILE]

\+: match any number of previous

	grep 'fo\+x' [FILE]

$: end of the line

	grep 'x$' [FILE]

^: beginning of the line

	grep '^sp' [FILE]

\s: any whitespace character

	grep '\s+word' [FILE]

\?: optional

	grep 'https\?' [FILE]

	[a-z]
	[A-Z]
	[A-Za-z]

Ejemplo de coincidencia de un correo

	grep '\S\+@\S\+.[A-Za-z]\+' [FILE]
