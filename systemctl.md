## Comando systemctl.md

# Listar todas las unidades que fallaron en el último reinicio de sistema

    systemctl --failed

# Servicios miscelánea

    systemctl is-enabled [service]
    systemctl is-active [service]
    systemctl status [service]
    systemctl start [service]
    systemctl stop [service]
    systemctl restart [service]
    systemctl enable [service]
    systemctl disable [service]
    systemctl show [service]
    systemctl mask [service]
    systemctl unmask [service]

# Lista todas las unidades (por defecto systemctl solo lista todas las unidades activas.)

    systemctl -all

# Listar todos los sockets

    systemctl list-sockets

# Listar todas las unit files con su status actual

    systemctl list-unit-files

# Listar las unidades de tipo target

    systemctl -t target
    systemctl -t target --all

# Ver el default boot target

    systemctl get-default
