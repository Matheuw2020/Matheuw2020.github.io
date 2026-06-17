---
layout: '../../layouts/BlogPost.astro'
title: 'Redes y Conexion'
description: 'Comandos utilizados para gestionar interfaces de red, comprobar la conectividad, analizar el tráfico y obtener información sobre las comunicaciones del sistema.'
date: '2026-06-18'
tags: ['linux', 'comandos', 'redes', 'conexion']
---

# **ping** → Verifica conectividad con otro host mediante traza ICMP[1](https://github.com/HackMafia404/CIBERSEGURIDAD/blob/main/APUNTES/1.%20LINUX/1.%20COMANDOS/1.6%20REDES%20Y%20CONEXION.md#user-content-fn-1-cccf4bd52c6820dfd1534fdf2f7ed6d6).

> - ping google.com → Probar conexión con Google
> - ping -c 4 8.8.8.8 → Enviar 4 paquetes
> - ping -i 2 google.com → Intervalo de 2 segundos
> - ping -s 1000 8.8.8.8 → Paquetes de 1000 bytes
> - ping -W 2 192.168.1.1 → Tiempo máximo de espera

# **curl** → Descarga contenido web e interactúa con APIs

> - curl [http://example.com](http://example.com/) → Descarga pagina
> - curl -O URL → Guardar con mismo nombre
> - curl -o archivo.html URL → Guardar con nombre específico
> - curl -I URL → Mostrar cabeceras HTTP
> - curl -L URL → Seguir redirecciones
> - curl -X POST -d "param=valor" URL → Enviar datos por POST
> - curl -H "User-Agent: Custom" URL → Usar cabecera personalizada

```shell
> curl http://example.com          # descargar página
> curl -O http://server/file.txt   # guardar archivo
> curl -X POST -d "a=1&b=2" api    # enviar datos POST
```

# **wget** → Descarga archivos desde internet.


> - wget URL → Descargar archivo
> - wget -O salida.txt URL → Guardar con nombre específico
> - wget -c URL → Reanudar descarga interrumpida
> - wget -r URL → Descarga recursiva
> - wget -i lista.txt → Descargar varias URLs
> - wget --limit-rate=200k URL → Limitar velocidad

```shell
> wget https://ejemplo.com/file.zip     # descarga archivo
> wget -c file.zip                      # reanudar descarga
> wget -r https://sitio.com             # clonar sitio recursivo
```

# **ifconfig | ip** → Mostrar y gestionar interfaces de red.

> - ifconfig → Listar interfaces (obsoleto)
> - ifconfig eth0 192.168.1.100 → Asignar IP
> - ifconfig eth0 down → Desactivar interfaz
> - ip a → Mostrar interfaces con IP
> - ip addr add 192.168.1.50/24 dev eth0 → Añadir IP
> - ip link set eth0 up → Activar interfaz
> - ip route show → Ver tabla de rutas

```shell
> ifconfig eth0 down                   # desactivar interfaz
> ip a                                 # mostrar interfaces
> ip addr add 10.0.0.5/24 dev wlan0    # añadir IP
```

# **netstat / ss** → Mostrar conexiones y sockets de red.

> - netstat -tulnp → Puertos abiertos
> - netstat -an → Todas las conexiones
> - ss -tulnp → Puertos abiertos (moderno)
> - ss -s → Resumen de conexiones
> - ss -tn sport = :22 → Conexiones TCP puerto 22
> - ss -u estado → Conexiones UDP

```shell
> netstat -tulnp          # listar puertos y procesos
> ss -s                   # resumen de conexiones
> ss -tn dst :80          # conexiones TCP hacia puerto 80
```

# **scp** → Copiar archivos entre equipos mediante SSH.

> - scp archivo usuario@host:/destino → Copiar archivo remoto
> - scp usuario@host:/archivo ./ → Descargar archivo
> - scp -r carpeta usuario@host:/destino → Transferir directorios
> - scp -P 2222 archivo usuario@host:/destino → Usar puerto alternativo
> - scp -i clave.pem archivo usuario@host:/destino → Usar clave privada

```shell
> scp archivo.txt user@192.168.1.10:/tmp/   # subir archivo
> scp -r carpeta user@servidor:/var/www     # subir carpeta
> scp -P 2222 archivo user@host:/home/user  # usar puerto 2222
```

# **ssh** → Conexión remota segura.

> - ssh usuario@ip → Conexión estándar
> - ssh -p 2222 usuario@ip → Usar puerto alternativo
> - ssh -i clave.pem usuario@ip → Usar clave privada
> - ssh -L 8080:localhost:80 usuario@ip → Túnel local
> - ssh -X usuario@ip → Reenvío gráfico (X11)
> - ssh-copy-id usuario@ip → Copiar clave pública para acceso sin contraseña

```shell
> ssh user@192.168.1.20              # conectarse al servidor
> ssh -i id_rsa.pem user@servidor    # autenticación con clave
> ssh -L 8080:localhost:80 user@ip   # tunel de puerto local
```

# **traceroute / tracepath** → Rastrea la ruta de los paquetes.

> - traceroute google.com → Mostrar ruta
> - traceroute -I google.com → Usar ICMP
> - traceroute -T google.com → Usar TCP
> - traceroute -m 5 google.com → Limitar a 5 saltos
> - traceroute -q 1 google.com → Una consulta por salto
> - tracepath 8.8.8.8 → Alternativa sin root

```shell
> traceroute google.com       # mostrar ruta
> traceroute -I 1.1.1.1       # ruta con ICMP
> tracepath 8.8.8.8           # alternativa moderna
```