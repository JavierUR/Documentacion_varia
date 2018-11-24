# Nvidia solo para CUDA

¡Pasos sin interfaz gráfica!

## Descargar driver de nvidia
https://www.nvidia.com/Download/index.aspx

##Desintalar driver actual
`sudo apt purge nvidia*`

## Desactivar x server
* cambiar configuración por defecto del sistema
 `sudo systemctl set-default multi-user.target`

* Reiniciar( **siguientes pasos sin interfaz gráfica**)

## Desactivar nouvou
Seguir pasos [aquí](https://linuxconfig.org/how-to-disable-nouveau-nvidia-driver-on-ubuntu-18-04-bionic-beaver-linux)

## Instalar driver

Ir a la carpeta e intalar el driver de esta forma reemplazando el nomre del driver:
`sudo sh <archivo_driver> --no-opengl-files --dkms --no-drm`

Opciones a usar:

* *The distribution-provided pre-installed script failed! Are you sure you want to continue?*: **Continue installation**
* *WARNING: The nvidia-drm module will not be installed. As a result, DRM-MMS will not function with this installation of the NVIDIA driver* **OK**
* *Would you like ton register the kernel module sources with DKMS? This will all DKMS to automatically build a new module, il fou install a different kernel later?* **Yes**
* *Install NVIDIA’s 32-bit compatibility libraries* **No**

## Configuración final
* instalar prime-select
`sudo apt intall nvidia-prime`

* Activar tarjeta intel y nvidia
`sudo prime-select intel`
`sudo prime-select nvidia`

* Recativar xserver
`sudo systemctl set-default graphical.target`

* Reiniciar
`sudo reboot`

* Probar si funciona: lo siguiente debería mostrar el estado de la tarjeta y un uso de 0% de la memoria
`nvidia-smi`
#### Referencias
* https://towardsdatascience.com/how-to-use-tensorflow-on-the-gpu-of-your-laptop-with-ubuntu-18-04-554e1d5ea189
* https://linuxconfig.org/how-to-disable-nouveau-nvidia-driver-on-ubuntu-18-04-bionic-beaver-linux
