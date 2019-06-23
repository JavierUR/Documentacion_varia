# Manual fix NVIDIA driver after kernel update

## Steps
* Open terminal as sudo
```
sudo su
```
* Check if driver surces are available 
```
ls /usr/src
```
* rebuild kernel module
```
dkms build -m nvidia -v [version]
```
* install module
```
dkms install -m nvidia -v [version]
```
* Reboot or load with modprobe
```
modprobe nvidia
```

