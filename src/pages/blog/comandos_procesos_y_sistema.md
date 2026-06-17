---
layout: '../../layouts/BlogPost.astro'
title: 'Permisos y Usuarios'
description: 'Comandos que permiten monitorear el estado del sistema, gestionar procesos en ejecución y analizar el uso de recursos como CPU, memoria y almacenamiento.'
date: '2026-06-17'
tags: ['linux', 'comandos', 'procesos', 'sistema']
---

# **ps** → Muestra los procesos activos en el sistema.

> - ps → Lista procesos de la terminal actual
> - ps -e → Muestra todos los procesos
> - ps -f → Formato completo (PID, PPID, CMD)[1](https://github.com/HackMafia404/CIBERSEGURIDAD/blob/main/APUNTES/1.%20LINUX/1.%20COMANDOS/1.4%20PROCESOS%20Y%20SISTEMA.md#user-content-fn-1-fc66885095cac66c2406cb4600445b65).
> - ps aux → Listado detallado con usuario, %CPU, %MEM, etc.
> - ps -ef --forest → Arbol de procesos

```shell
> ps aux | grep ssh          # buscar procesos que contengan ssh
> ps -ef --forest            # mostrar árbol de procesos
```

# **top** → Muestra en tiempo real procesos y consumo de recursos.

> - top → abre el monitor interactivo
>     - M → ordenar por memoria
>     - P → ordenar por CPU
>     - k → matar proceso introduciendo el PID

```shell
> top                       # ver procesos en tiempo real
> htop                      # versión mejorada (si está instalada)
```

# **pgrep | pkill | kill** → Busca y mata procesos

> - pgrep nombre → Devuelve PID de procesos
> - pkill nombre → Termina procesos que coincidan
> - pkill -9 nombre → Matar forzado con SIGKILL
> - kill PID → Envía señal por defecto (SIGTERM, 15)
> - kill -9 PID → Señal SIGKILL, fuerza terminación
> - kill -15 PID → Señal SIGTERM, termina de forma segura

```shell
> pgrep firefox             # devuelve PIDs de firefox
> pkill -9 firefox          # matar firefox a la fuerza
> kill -9 1234              # matar proceso con PID 1234
```

# **jobs | fg | bg** → Control de procesos en segundo plano en la shell.

> - jobs → Lista trabajos en segundo plano
> - fg %n → Trae el trabajo n al primer plano
> - bg %n → Reanuda en segundo plano

```shell
> sleep 100 &               # ejecutar en segundo plano
> jobs                      # ver trabajos en background
> fg %1                     # traer trabajo 1 al foreground
```

# **uname | uptime** → Informacion del sistema y tiempo de encendido

> - uname -r → Versión del kernel
> - uname -a → Información completa (SO, kernel, arquitectura)
> - uptime → Usuarios conectados + carga media
> - uptime -p → Formato legible
> - uptime -s → Fecha y hora de arranque

```shell
> uname -r                  # versión del kernel
> uname -a                  # info completa del sistema
> uptime -p                 # sistema encendido durante X tiempo
> uptime -s                 # hora exacta de arranque
```

# **free | df** → Uso de RAM, swap[2](https://github.com/HackMafia404/CIBERSEGURIDAD/blob/main/APUNTES/1.%20LINUX/1.%20COMANDOS/1.4%20PROCESOS%20Y%20SISTEMA.md#user-content-fn-2-fc66885095cac66c2406cb4600445b65) y disco duro.

> - free → Mostrar memoria en KB
> - free -h → Formato legible (MB/GB)
> - df → Espacio en bloques
> - df -h → Formato legible
> - df -i → Muestra uso de inodos

# **hostname | hostnamectl** → Información del sistema y nombre del host.

> - hostname → Nombre del host
> - hostnamectl → Detalles de la máquina (distro, kernel, etc.)

# **journalctl** → Logs en sistemas.

> - journalctl → Todos los logs
> - journalctl -xe → Ultimos errores
> - journalctl -u servicio → Logs de un servicio específico

```shell
> journalctl -u ssh         # logs del servicio ssh

```

# **systemctl** → - Gestión de servicios y sistema

> - systemctl status servicio → Estado del servicio
> - systemctl start servicio → Iniciar servicio
> - systemctl stop servicio → Detener servicio
> - systemctl restart servicio → Reiniciar servicio
> - systemctl enable servicio → Habilitar al arranque
> - systemctl disable servicio → Deshabilitar al arranque

```shell
> systemctl status ssh        # Muestra el estado del servicio SSH
> systemctl start apache2     # Inicia el servicio Apache2
> systemctl stop apache2      # Detiene el servicio Apache2
> systemctl restart apache2   # Reinicia el servicio Apache2
> systemctl enable apache2    # Habilita Apache2 para iniciar al arranque
> systemctl disable apache2   # Deshabilita Apache2 del arranque