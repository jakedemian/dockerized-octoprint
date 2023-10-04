## Instructions
1. Install Raspberry Pi Lite 64bit OS onto RPi 4
	- be sure to configure the Wifi username/password before flashing the sd card
	- set SSH username/password as well
2. SSH into the Pi once its up and pingable
3. Install docker.  [Since we're using the 64 bit arch OS](https://docs.docker.com/engine/install/raspberry-pi-os/#os-requirements), we need to follow the [DEBIAN instructions](https://docs.docker.com/engine/install/debian/) not the RPi instructions for docker.
4. Now `nano` the `docker-compose.yml` into a new directory `~/dockerized-octoprint`
	- https://github.com/jakedemian/dockerized-octoprint/blob/main/docker-compose.yml
5. `docker compose up -d`
6. Open both octoprints in web browser using ports 9001 and 9002
7. Hit next then restore each from the latest octoprint backup
8. Verify octoprint working.  If webcams arent working, try unplugging them and `docker compose down` then `docker compose up -d`.  If that still doesn't work then check `/dev` for the device names.  For better info on the devices use these commands:
	-  `sudo apt-get install v4l-utils`
	-  `v4l2-ctl --list-devices`
