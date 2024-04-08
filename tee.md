## Comando 'tee'

# Guardar la salida de un comando en un archivo

	ls -l | tee resultado.txt

# Concatenar resultados

	ip add | tee -a resultado.txt

# Ver y almacenar la salida de un comando en tiempo real

	tail -f /var/log/syslog | tee -a resultado
