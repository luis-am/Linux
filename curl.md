## Comando 'curl'

curl -o [FILENAME] [URL]

Establecemos el nombre del archivo descargado.

	curl -O [URL]
    curl -o hello.zip ftp://speedtest.tele2.net/1MB.zip

Descarga con el mismo nombre en el que se descarga.

	curl --O [URL]

Ver la barra de progreso.

    curl -O ftp://speedtest.tele2.net/1MB.zip
    curl --O ftp://ftp.example.com/file.zip

No mostrar la metrica de progreso.

	curl --silent [URL]
    curl --silent ftp://ftp.example.com/file.zip
    
Resume downloads cuando se descarga archivos largos y ha sido interrumpido.

	curl -C - [URL]
    curl -C - -O ftp://speedtest.tele2.net/1MB.zip

Limitamos el limite de descarga en bytes.

	curl --limit-rate [VALUE] [URL]
    curl --limit-rate 1000K -O ftp://speedtest.tele2.net/1MB.zip

Descarga archivos de servidores autenticados FTP

	curl -u {username}:{password} [FTP-URL]
    curl -u demo:password -O ftp://speedtest.tele2.net/1MB.zip
