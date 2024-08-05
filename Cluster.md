# CLUSTER, NODE LIST/REMOVE

``` bash
pvecm status 
pvecm nodes 
pvecm delnode hp4
```

``` bash
systemctl stop pve-cluster systemctl stop corosync 
pmxcfs -l # Start the cluster filesystem again in local mode 
rm /etc/pve/corosync.conf 
rm -r /etc/corosync/* 
killall pmxcfs systemctl 
start pve-cluster
```

## CLUSTER REMOVE FROM WebGUI

``` bash
ls -l /etc/pve/nodes/ 
mv /etc/pve/nodes/NodeName /root/NodeName
```

## ADD HDD SINGLE NODE ON CLUSTER 

``` bash
lsblk 
WebGUI (Node -> Disks -> Directory -> Create)
```

