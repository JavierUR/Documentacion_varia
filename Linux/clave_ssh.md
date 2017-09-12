## Crear clave ssh
Un par de clave ssh para permitir la conexon sin contraseña a una maquina remota.
Se crea una calve con nombre <clave\> de tipo ecdsa de 521-bit

```
ssh-keygen -f ~/.ssh/<clave> -t ecdsa -b 521
```

Copiar la clave a la maquina remota

```
ssh-copy-id -i ~/.ssh/<clave> user@host
```

Agregar el host en ssh, en `~/.ssh/config` añadir:

```
Host <HOST>
        Hostname <HOSTNAME>
        User <USER>
        IdentityFile ~/.ssh/<clave>
        HostKeyAlgorithms +ecdsa-sha2-nistp521
```

Probar la configuracion con:

```
ssh <HOST>
```

### Referencia
* https://www.ssh.com/ssh/keygen/
* https://github.com/Duckietown-Chile/documentation/blob/master/Lanzando_launchs_remotos.md
