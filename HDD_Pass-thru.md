# HDD Pass-thru

``` bash
qm set 113 -backup=no -sata2 /dev/disk/by-id/wwn-0x5000c500639d3dcf
qm set 113 -sata3 /dev/disk/by-id/wwn-0x50014ee2078e67d4
qm set 113 -sata4 /dev/disk/by-id/wwn-0x50014ee0aeb966f3

nano /etc/pve/qemu-server/100.conf

args: -device ahci,id=ahci1,multifunction=on,bus=pci.0,addr=0xb -drive 'file=/dev/disk/by-id/ata-ST3000DM001-1CH166_W1F4ZE0L,if=none,id=drive-sata6,format=raw,aio=threads,detect-zeroes=unmap' -device ide-hd,bus=ahci1.1,drive=drive-sata6,id=sata6

args: -device ahci,id=ahci1,multifunction=on,bus=pci.0,addr=0xb -drive 'file=/dev/disk/by-id/ata-WDC_WD7501AAES-75W7A0_WD-WCATR2260936,if=none,id=drive-sata7,format=raw,aio=threads,detect-zeroes=unmap' -device ide-hd,bus=ahci1.1,drive=drive-sata7,id=sata7

args: -device ahci,id=ahci1,multifunction=on,bus=pci.0,addr=0xa -drive 'file=/dev/disk/by-id/ata-ST3000DM001-1CH166_W1F4ZE0L,if=none,id=drive-sata8,format=raw,aio=threads,detect-zeroes=unmap' -device ide-hd,bus=ahci1.1,drive=drive-sata8,id=sata8 -device 

ahci,id=ahci2,multifunction=on,bus=pci.0,addr=0xb -drive 'file=/dev/disk/by-id/ata-WDC_WD7501AAES-75W7A0_WD-WCATR2260936,if=none,id=drive-sata9,format=raw,aio=threads,detect-zeroes=unmap' -device ide-hd,bus=ahci1.2,drive=drive-sata9,id=sata9 -device 

ahci,id=ahci3,multifunction=on,bus=pci.0,addr=0xc -drive 'file=/dev/disk/by-id/ata-SAMSUNG_HD642JJ_S1AFJDWQ527971,if=none,id=drive-sata7,format=raw,aio=threads,detect-zeroes=unmap' -device ide-hd,bus=ahci1.3,drive=drive-sata7,id=sata7
```

