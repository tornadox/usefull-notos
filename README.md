# usefull-notos


Installation is quite simple.

    Install dependencies

    apt-get install -y apt-transport-https


    Add respository key
    Code:

    wget -q https://packagecloud.io/gpg.key -O - | sudo apt-key add -


    Add repository
    Code:

    echo 'deb https://packagecloud.io/Hypriot/Schatzkiste/debian/ jessie main' | sudo tee /etc/apt/sources.list.d/hypriot.list
    apt-get update


    Install Hypriot 
    Code:

    apt-get install -y docker-hypriot
    systemctl enable docker



Afterwards docker is ready to use.


You can test your docker installation:


docker info

Code:

Containers: 0
 Running: 0
 Paused: 0
 Stopped: 0
Images: 0
Server Version: 1.11.1
Storage Driver: devicemapper
 Pool Name: docker-179:1-395364-pool
 Pool Blocksize: 65.54 kB
 Base Device Size: 10.74 GB
 Backing Filesystem: ext4
 Data file: /dev/loop0
 Metadata file: /dev/loop1
 Data Space Used: 305.7 MB
 Data Space Total: 107.4 GB
 Data Space Available: 13.8 GB
 Metadata Space Used: 729.1 kB
 Metadata Space Total: 2.147 GB
 Metadata Space Available: 2.147 GB
 Udev Sync Supported: true
 Deferred Removal Enabled: false
 Deferred Deletion Enabled: false
 Deferred Deleted Device Count: 0
 Data loop file: /var/lib/docker/devicemapper/devicemapper/data
 WARNING: Usage of loopback devices is strongly discouraged for production use. Either use `--storage-opt dm.thinpooldev` or use `--storage-opt dm.no_warn_on_loop_devices=true` to suppress this warning.
 Metadata loop file: /var/lib/docker/devicemapper/devicemapper/metadata
 Library Version: 1.02.90 (2014-09-01)
Logging Driver: json-file
Cgroup Driver: cgroupfs
Plugins:
 Volume: local
 Network: null host bridge
Kernel Version: 4.6.3-sunxi
Operating System: Debian GNU/Linux 8 (jessie)
OSType: linux
Architecture: armv7l
CPUs: 2
Total Memory: 493.9 MiB
Name: a20
ID: LFI7:LG2C:WHZD:SB5F:3JFW:TI56:WCFF:IFJH:MZJ5:NK45:MVG7:FN7D
Docker Root Dir: /var/lib/docker
Debug mode (client): false
Debug mode (server): false
Registry: https://index.docker.io/v1/

Code:

docker version

Code:

Client:
 Version:      1.11.1
 API version:  1.23
 Go version:   go1.4.3
 Git commit:   5604cbe
 Built:        Mon May  9 00:50:14 2016
 OS/Arch:      linux/arm

Server:
 Version:      1.11.1
 API version:  1.23
 Go version:   go1.4.3
 Git commit:   5604cbe
 Built:        Mon May  9 00:50:14 2016
 OS/Arch:      linux/arm


Keep in mind that only ARM-based containers will run on ARM devices. You can search for valid containers with tags like "armhf" or "hypriot":

Code:

docker search armhf

Code:

NAME                                  DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
armv7/armhf-ubuntu                    'official' Ubuntu Docker images for the AR...   30
container4armhf/armhf-alpine          Automatically built base images of Alpine ...   22                   [OK]
ioft/armhf-ubuntu                     [ABR] Ubuntu Docker images for the ARMv7(a...   14                   [OK]
mazzolino/armhf-ubuntu                Ubuntu-Core images for armhf (ARMv7) devices    6
armhf/ubuntu                          Ubuntu is a Debian-based Linux operating s...   5
werwolfby/armhf-alpine-transmission   Minimal alpine docker image for transmissi...   2                    [OK]
cburki/armhf-dev                      Armhf (Raspberry Pi) cross development wit...   2                    [OK]
moul/armhf-busybox                                                                    2                    [OK]
werwolfby/armhf-alpine-gogs           ARM hf compatible Docker Image with a mini...   1                    [OK]
ioft/armhf-debian                     Debian Docker images for the ARMv7(armhf) ...   1                    [OK]
ivanmarban/armhf-gogs                 Gogs - Go Git Service Docker images for AR...   1
werwolfby/armhf-alpine-nginx          ARM hf compatible Docker Image with a mini...   1                    [OK]
msvb/armhf-iotempire                  Collection of software packages to accompa...   0                    [OK]
lalyos/armhf-syncthing                http://docs.syncthing.net in a container f...   0                    [OK]
sheenhx/armhf-concentrator            CC3200 serial concentrator for Beagle Bone...   0                    [OK]
container4armhf/armhf-busybox         Automated build of Busybox for armhf devic...   0                    [OK]
ijoijo/armhf-alpine                   Alpine Linux image for armhf devices (like...   0                    [OK]
armv7/armhf-ubuntu_automated-build    This repo has moved to https://registry.hu...   0                    [OK]
kennethlimcp/armhf-ghost              The awesome Ghost blog, on armhf                0                    [OK]
wontfix/gecko-armhf-dev               Linux/armhf cross build environment for Gecko   0                    [OK]
mathewpeterson/armhf-php7             This image extends the official armhf php ...   0                    [OK]
cailloumajor/debian-armhf-qemu        Debian armhf image with qemu-user-static        0                    [OK]
cricketeerone/armhf-logspout          A fork of gliderlabs/logspout using armhfb...   0                    [OK]
mjschultz/ubuntu-armhf                                                                0                    [OK]
fish/alpine-armhf-dumb-init           alpine-armhf-docker image with "dumb-init"...   0                    [OK]

Code:

docker search hypriot

Code:

NAME                              DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
hypriot/rpi-node                  RPi-compatible Docker Image with Node.js        78
hypriot/rpi-java                  RPi-compatible Docker Image with Java           28
hypriot/rpi-mysql                 RPi-compatible Docker Image with Mysql          24
hypriot/rpi-dockerui              An ARM compatible Docker image of https://...   23
hypriot/rpi-swarm                 Raspberry Pi compatible Docker image with ...   22
hypriot/rpi-python                RPi-compatible Docker Image with Python         22
hypriot/rpi-alpine-scratch        Raspberry Pi compatible Docker Image with ...   22
hypriot/rpi-golang                                                                21
hypriot/rpi-busybox-httpd         Raspberry Pi compatible Docker Image with ...   15
hypriot/rpi-iojs                  RPi-compatible Docker Image with io.js          15
hypriot/rpi-gogs-raspbian         Raspberry Pi compatible Docker Image with ...   14
hypriot/rpi-redis                 Raspberry Pi compatible redis image             12
hypriot/rpi-ruby                  RPi-compatible Docker Image with Ruby           11
hypriot/rpi-hugo                  Raspberry Pi compatible Docker Image with ...   10
hypriot/rpi-haproxy               Haproxy Dockerfile                              10
hypriot/rpi-registrator           An ARM compatible Docker image of https://...   4
hypriot/rpi-crate                 RPi-compatible Docker Image with Crate.io       4
hypriot/rpi-consul                ARM compatible Docker Image with Consul         3
np83/rpi2-hypriot-nodejs          Raspberry PI 2 can run hypriot Docker host...   2                    [OK]
hypriot/rpi-nano-httpd            Raspberry Pi nano sized HTTP server             2
calou/hypriot-zookeeper           Zookeeper on Raspberry Pi                       1
configman/hypriot-jenkins-slave   jenkins docker slave for running on a hypr...   0
calou/hypriot-solr                Solr on Raspberry Pi                            0
emyann/hypriot-flash                                                              0
hypriot/image-builder             Base image for several hypriot/image-build...   0

