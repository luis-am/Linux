Ver el process id de un proceso

	ps -f [NUMBER]

Ver en jerarquia los procesos

	ps f

Iniciar procesos en el background 

	[COMANDO] &

Ver los tipos de kill

	kill -l

Matar un proceso con signal 'sigterm'

	kill -15 [PID]

Matar un proceso con signal 'sigkill'

	kill -9 [PID]

Suspender un proceso en el background

	kill -20 [PID]

Traer de vuelta un proceso en el background

	kill -18 [PID]
