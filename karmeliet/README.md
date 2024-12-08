# Notes

## Install

* AlmaLinux 9.4
* Install rpmfusion-free, rpmfusion-nonfree
* Rpmfusion nvidia driver: https://rpmfusion.org/Howto/NVIDIA
* To get ffmpeg working: dnf config-manager --set-enabled crb
* Video in firefox: install ffmpeg https://rpmfusion.org/Howto/Multimedia

## HW

* Intel i7-3770, 16Gb RAM, Nvidia GTX960
* Use the 82579LM network card at the top, the 82574L below has issues
* MAC ending in 1c

## Old disk

AlmaLinux 9 doesn't support older LVM. Vgconvert isn't included, to convert:

```
# assuming a pv of the old vg is /dev/sdb6

$ vgscan -d -v --devices /dev/sdb6
WARNING: PV /dev/sdb6 in VG karmeliet is using an old PV header, modify the VG to update.
Found volume group "karmeliet" using metadata type lvm2
Archiving volume group "karmeliet" metadata (seqno 3).
Creating volume group backup "/etc/lvm/backup/karmeliet" (seqno 3).

$ vgcfgrestore karmeliet --devices /dev/sdb6
Restored volume group karmeliet.

$ vgscan --devices /dev/sdb6
Found volume group "karmeliet" using metadata type lvm2

$ vgchange -ay karmeliet --devices /dev/sdb6
2 logical volume(s) in volume group "karmeliet" now active

# devices now accessible at /dev/mapper/ and /dev/karmeliet/
```
