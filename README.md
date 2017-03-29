# Media server docker containers
This will setup sonarr, sabnzbd, radarr, deluge and headphones as docker containers.

## Data and Storage directories:
You will need to modify the docker-compose.yml file to point to your data and storage dirs.
These are the directories on your host server that you want to expose to the docker containers.

This will give you a way to save state outside of the containers themselves, so that config and db files will persist. You can also setup a cronjob to backup these folders to the cloud incase of a drive failure.

* /mnt/storage/dockerdata=(dir where all the config files and db files will be kept)
* /media/jeff/nas=(dir where all processed downloads will be saved)
* /mnt/storage/tmp=(dir where incomplete downloads will be saved)
* /mnt/storage/downloads=(dir where unprocessed downloads will be saved)

To build and run:

`sudo docker-compose up -d`
