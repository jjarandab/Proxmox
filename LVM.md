# CREATE LVM (NEW LOCAL STORAGE)

``` bash
fdisk -l
cfdisk /dev/sda //New->Write->Quit
pvcreate /dev/sda1
vgcreate local-hdd /dev/sda1
```

on WebUI Datacenter->Storage->Add->LVM

## DELETE LVM STORAGE

``` bash
lvdisplay
lvremove %nameofvolume%
vgdisplay
vgremove %nameofvolumegroup%
pvdisplay
pvremove /dev/sdxxxxx
```

