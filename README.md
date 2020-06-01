Raspberry Pi docker-compose files

Model: B 

Installed OS
	* <s> DietPi </s>
	* Hypriot

Todo
* <s> Enable reverse proxy for Pihole as default host </s>
* <s> Create environment file </s>
* Enable Log2Ram
* Get version number of tools to avoid future breaking
* auto start docker containers on reboot
* pihole disable dns, network access?

PiA
- Nextcloud
- PiHole


PiB
- PiHole
- Transmission (with VPN)
- SteamLink


Volumio/RuneAudio?

Useful links: 
* Mounting external disks - https://github.com/nextcloud/docker/issues/236
* Nginx reverse proxy - 
* Environment file - https://www.techrepublic.com/article/how-to-use-docker-env-file/

Useful docker commands
* docker-compose config -> gives final docker-compose file with env variables
* ls -al -> show hidden files
* docker-compose images/containers -a

For debain based systems, make sure to disable dsn:
sudo systemctl disable systemd-resolved.service
sudo systemctl stop systemd-resolved

sudo systemctl start systemd-resolved
sudo systemctl enable systemd-resolved.service
