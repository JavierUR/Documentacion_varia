# Mosh
[Mosh](https://mosh.org/) es una alternativa a ssh que promete ser mas robusto en la conexion.

Utiliza ssh para conectarse y establece la conexion en un puerto udp del rango 60000-61000(se debe mantener abierto en el firewall)

# Instalación
Instalar de forma simple en cliente y servidor
```
sugo apt-get install mosh
```

# Conexion
Asegurarse de que esten abiertos los puertos y conectar de la forma:
```
mosh [--ssh=COMMAND] user@host
```
COMMAND puede ser algun comando de ssh, escribir de la forma(con comillas): "ssh -i ..."
### Problema con localizacion de lenguaje
Puede ocurrir un problema si la localizacion no esta en el servidor. 
Puede ser util fijar las variables en `/etc/default/locale`

ej:
```
LC_ALL=en_US.UTF-8
LANG=en_US.UTF-8
```

### Referencias
* https://mosh.org/
