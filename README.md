## 👋 Welcome to aria2 🚀  

 aria2 is a utility for downloading files. The supported protocols are HTTP(S), FTP, SFTP, BitTorrent, and Metalink.  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update aria2
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/aria2/rootfs"
git clone "https://github.com/dockermgr/aria2" "$HOME/.local/share/CasjaysDev/dockermgr/aria2"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/aria2/rootfs/." "$HOME/.local/share/srv/docker/aria2/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-aria2 \
--hostname aria2 \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/casjaysdevdocker-aria2/rootfs/data:/data:z \
-v $HOME/.local/share/srv/docker/casjaysdevdocker-aria2/rootfs/config:/config:z \
-p 19001:80 \
casjaysdevdocker/aria2:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/aria2
    container_name: casjaysdevdocker-aria2
    environment:
      - TZ=America/New_York
      - HOSTNAME=aria2
    volumes:
      - $HOME/.local/share/srv/docker/casjaysdevdocker-aria2/rootfs/data:/data:z
      - $HOME/.local/share/srv/docker/casjaysdevdocker-aria2/rootfs/config:/config:z
    ports:
      - 19001:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/aria2
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/aria2" "$HOME/Projects/github/casjaysdevdocker/aria2"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/aria2"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
