## Crear clave ssh
Un par de clave ssh para permitir la conexon sin contraseña a una maquina remota.
Se crea una clave con nombre _key_ de tipo ecdsa de 521-bit

```
ssh-keygen -f ~/.ssh/key -t ecdsa -b 521
```

Copiar la clave a la maquina remota

```
ssh-copy-id -i ~/.ssh/key user@host
```

Agregar el host en ssh, en `~/.ssh/config` añadir:

```
Host host
        Hostname hostname
        User user
        IdentityFile ~/.ssh/key
        HostKeyAlgorithms +ecdsa-sha2-nistp521
```
Notar que el nombre _host_ es de libre elección

Probar la configuracion con:

```
ssh host
```

### Referencia
* https://www.ssh.com/ssh/keygen/
* https://github.com/Duckietown-Chile/documentation/blob/master/Lanzando_launchs_remotos.md
