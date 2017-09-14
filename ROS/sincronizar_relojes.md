# Sincronizar los relojes
Para el correcto funcionamiento de ROS en multiples maquinas, los relojes de estas deben estar sincronizados.

## Instalar chrony
chrony se necarga de sincronizar el reloj del computador segun una referencia.

instalar usando:
```
sudo apt-get install chrony
```

## Fijar referencia
Se debe elegir un computador como referencia( deberia ser el que corra el roscore)
Detener el servivio de chrony
```
sudo service chrony stop
```
Agregar la referencia(hostname, en este caso master) en el archivo de configuracion (*/etc/chrony/chrony.conf*)
```
server master minpoll 0 maxpoll 5 maxdelay .05
```
y comentar el resto de los servidores.
Finalmente, reiniciar chrony
```
sudo service chrony start
```
