# Raspberry Pi docker-compose files

## Model: B 

### PiA
"DockerVersion": "18.09.7"
- Nextcloud
	- Nextcloud v16
	- Postgres v13
- PiHole
	- Docker Pi-hole v4.2.2
- Brudy Nginx proxy
	- budry/jwilder-nginx-proxy-arm - https://hub.docker.com/r/budry/jwilder-nginx-proxy-arm

#### Installed OS
* <s> DietPi </s>
* Hypriot

Nextcloud doesn't seem to be well-performing as a Media server. Planned to share as <s> SMB </s> NFS and use Kodi/Plex as well as Transmission

#### Todo
* <s> Enable reverse proxy for Pihole as default host </s> Main reason it seems is to make default host to Pi
* <s> Create environment file </s>
* <s> Enable Log2Ram </s> Mounted on external hdd
* <s> Get version number of tools to avoid future breaking </s>
* <s> auto start docker containers on reboot </s> restart:always <- Docker compose
* <s> pihole disable dns, network access? </s> not needed for hyriot


### PiB
- PiHole
- Web browser
- Transmission (with VPN)
- SteamLink
- Volumio/RuneAudio?

#### Installed OS
* DietPi


### Useful links: 
* Mounting external disks - https://github.com/nextcloud/docker/issues/236
* Nginx reverse proxy - image: jwilder/nginx-proxy <- not available for arm, use budry/jwilder-nginx-proxy-arm image instead
* Environment file - https://www.techrepublic.com/article/how-to-use-docker-env-file/
* Hypriot static IP  - https://dzone.com/articles/configuring-a-static-ip-on-hypriotos-for-the-raspb
* Ext HDD mount pi - https://www.raspberrypi.org/documentation/configuration/external-storage.md
* ssh grpahical application - https://askubuntu.com/questions/886313/what-is-the-simplest-way-to-have-remote-gui-access-to-ubuntu-16-04-server-from 		(ssh -X user@ip-address)
* IPv4 docker overlap - Using VPN? - https://stackoverflow.com/questions/43720339/docker-error-could-not-find-an-available-non-overlapping-ipv4-address-pool-am
* NFS Sharing guide - https://www.raspberrypi.org/documentation/configuration/nfs.md
* Windscribe linux - https://windscribe.com/guides/linux#how-to

### Useful docker commands
* docker-compose config -> gives final docker-compose file with env variables
* ls -al -> show hidden files
* docker-compose images/containers -a

### Not required for hypriot
For debain based systems, make sure to disable dsn:
sudo systemctl disable systemd-resolved.service
sudo systemctl stop systemd-resolved

sudo systemctl start systemd-resolved
sudo systemctl enable systemd-resolved.service

### Tips
Mounting on ext_hddd requires sudo permissions?
