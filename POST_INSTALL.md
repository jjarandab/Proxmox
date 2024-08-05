# POST INSTALL CONFIG

``` bash
#ADD NO-SUBSCRIPTION
REPOSITURY FOR UPDATES

echo "deb http://download.proxmox.com/debian
buster pve-no-subscription" >> /etc/apt/sources.list

#COMMENTS OUT PAID
REPOSITORY

echo "# deb https://enterprise.proxmox.com/debian/pve
buster pve-enterprise" > /etc/apt/sources.list.d/pve-enterprise.list

#APPLY UPDATES,
UPGRADES & RESTARTS

apt-get update
&& apt-get upgrade -y && apt-get dist-upgrade -y &&
reboot

#ON CLOSE LAPTOP LID

echo -e
"HandleLidSwitch=ignore \nHandleLidSwitchDocked=ignore
\nHandleLidSwitchDocked=ignore" >> /etc/systemd/logind.conf

systemctl restart
systemd-logind.service
```

