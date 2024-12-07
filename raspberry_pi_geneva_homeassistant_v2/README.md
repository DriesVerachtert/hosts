# Info

# HW

* Raspberry Pi 4 Model B Rev 1.2, 4Gb RAM
* Ethernet MAC ends with 20
* Wlan MAC ends with f9
 
## Install

Installed with Almalinux 9.4 image without Gnome for Raspberry Pi, see
install directory for cloud config.

Missing or not working in cloudconfig: hostnamectl set-hostname pigeneva.local

Very basic k0s setup: see ansible subdir

Test k0s:

```
[dries@genevapi ~]$ sudo /usr/local/bin/k0s kubectl version
Client Version: v1.31.2
Kustomize Version: v5.4.2
Server Version: v1.31.2+k0s
[dries@genevapi ~]$ sudo /usr/local/bin/k0s kubectl get nodes
NAME             STATUS   ROLES           AGE    VERSION
genevapi.local   Ready    control-plane   134m   v1.31.2+k0s
```
