## I'm pretty new to this docker stuff, so use it at your own risk!

# docker-mediaelch

Container for MediaElch on unraid (http://www.kvibes.de/mediaelch/)

Run MediaElch with HTTP GUI (port 5800) or RDM (port 5900).

Exported Volumes 

Based on https://github.com/Giftie/docker-mediaelch which uses the latest ppa:mediaelch/mediaelch-stable

## Usage
Containerizd MediaElch and allow remote accesss through HTTP GUI. Connect to `http://<docker_ip>:5800` to access mediaelch GUI

## Parameters
* `-p 5800:5800 -p 5900:5900` - the port(s)
* `-v /home/mediaelch/.config/kvibes` - where MediaElch should store config files. / UPDATE: actually its stored here `/config/xdg/config/kvibes`
* `-v /movies` - your movies folder
* `-v /shows` - your tv-shows folder
* `-e PGID` for GroupID - see below for explanation
* `-e PUID` for UserID - see below for explanation

## Run command

`docker run -p 5800:5800 -p 5900:5900 -v /path/to/config/folder:/config/xdg/config/kvibes -v /path/to/media:/movies -e PGID=1000 -e PUID=1000 mediaelch:latest`

### User / Group Identifiers
You can specify the user `PUID` and group `PGID`. Ensure the data volume directory on the host is owned by the same user.

### Update

Fixed the VNC resolution (1600x900) in the browser to display the full artwork with Image 1.1