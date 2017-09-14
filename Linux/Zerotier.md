# Zerotier
Zerotier permite la conexion de diversos dispositivos en una red virtual(gratis hasta 100)

## Instalación

La forma segura de instalar es usando el suguiente comando:
```
curl -s 'https://pgp.mit.edu/pks/lookup?op=get&search=0x1657198823E52A61' | gpg --import && \
if z=$(curl -s 'https://install.zerotier.com/' | gpg); then echo "$z" | sudo bash; fi
```

Otra forma es usando solo:
```
curl -s https://install.zerotier.com/ | sudo bash
```

Con esto, mostrará la direccion del pc en la red _zerotier_(10 digitos) y quedara configurado para iniciar el servicio con el pc.

## Crear una red
La red virtual se puede crear en la pagina de [zerotier](www.zerotier.com)

## Unirse a una red
Usando la terminal, se puede unir a una red con
```
sudo zerotier-cli join <address>
```
donde <address\> es la id de la red con 16 digitos
