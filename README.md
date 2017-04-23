[![](https://images.microbadger.com/badges/image/sgtsquiggs/nzbhydra.svg)](https://microbadger.com/images/sgtsquiggs/nzbhydra)

# nzbhydra

This image is derived from [sgtsquiggs/alpine](https://hub.docker.com/r/sgtsquiggs/alpine/).

[NZBHydra](https://github.com/theotherp/nzbhydra) is a meta search for NZB indexers.

## Usage
```
docker run \
    --name=nzbhydra \
    -v <path to data>:/config \
    -e PGID=<gid> -e PUID=<uid> \
    -p 5075:5075 \
    sgtsquiggs/nzbhydra
```

## Parameters
* `-p 5075:5075` external port 5075 mapping to internal port 5075
* `-v <path>:/config` where configuation files are stored.
* `-v <path>:/downloads` where complete downloads are stored.
* `-v <path>:/incomplete-downloads` where incomplete downloads are stored.
* `-e PGID=<gid>` for Group ID (see below)
* `-e PUID=<uid>` for User ID (see below)

## User and Group ID
Set these to match the user/group ID of shared data volumes. Files written to these volumes will match the
provided uid/gid.

## Acknowledgements

* [linuxserver/hydra](https://github.com/linuxserver/docker-hydra)
