### Raspberry Pi docker-compose files

## Model: B 

# Installed OS
	* <s> DietPi </s>
	* Hypriot

# Todo
* <s> Enable reverse proxy for Pihole as default host </s>     
* <s> Create environment file </s>
* Enable Log2Ram
* Get version number of tools to avoid future breaking
* auto start docker containers on reboot
* pihole disable dns, network access?

# PiA
"DockerVersion": "18.09.7"
- Nextcloud
	- Nextcloud v16
	- Postgres v13
- PiHole
	- Docker Pi-hole v4.2.2
- Brudy Nginx proxy
	- budry/jwilder-nginx-proxy-arm - https://hub.docker.com/r/budry/jwilder-nginx-proxy-arm

# PiB
- PiHole
- Transmission (with VPN)
- SteamLink


Volumio/RuneAudio?

# Useful links: 
* Mounting external disks - https://github.com/nextcloud/docker/issues/236
* Nginx reverse proxy - image: jwilder/nginx-proxy <- not available for arm, use budry/jwilder-nginx-proxy-arm image instead
* Environment file - https://www.techrepublic.com/article/how-to-use-docker-env-file/
* Hypriot static IP  - https://dzone.com/articles/configuring-a-static-ip-on-hypriotos-for-the-raspb
* Ext HDD mount pi - https://www.raspberrypi.org/documentation/configuration/external-storage.md

# Useful docker commands
* docker-compose config -> gives final docker-compose file with env variables
* ls -al -> show hidden files
* docker-compose images/containers -a

## Not required for hypriot
For debain based systems, make sure to disable dsn:
sudo systemctl disable systemd-resolved.service
sudo systemctl stop systemd-resolved

sudo systemctl start systemd-resolved
sudo systemctl enable systemd-resolved.service

# Tips
Mounting on ext_hddd requires sudo permissions?
