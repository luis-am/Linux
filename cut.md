# selecciona un caracter del file, -b o -c 
	input: cut -b # [FILENAME]
	input: cut -b #,#,#,# [FILENAME]
	input: cut -b #-# [FILENAME]	
	input: cut -c # [FILENAME]
	input: cut -c #-#,#,# [FILENAME]
	input: cut -b #- [FILENAME]
	input: cut -b -# [FILENAME]

# establecer una delimitador y mostrar las columnas, usa 'tab' por defecto como delimitador
	input: cut -d ":" -f 1 /etc/passwd
	ejemplo: ls -l | cut -d " " -f 1,10
# 
