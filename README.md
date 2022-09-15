# minecraft-relase-1.13-cloud-based-server-for-fun-
google cloud/linux debian based minecraft server (just for fun)

-------------------------------------------------------------------------

1. Google Cloud setup



Compute Engine -> Create a new virtual machine

name: minecraftserver
region: europe-west-frankfurt

Series number: E2
e2 standard (2GB RAM)

boot drive: Debian/GNU Linux 9 (stretch)
10GB SSD


Advanced setting -> Network operation

tags: minecrtaft
external ip -> create an ip address: minecraftserver         /// created ipv4 will be used to connection with our minecraft server

create



Firewall rules

Create new firewall rule

name: minecraftserver
tags: minecraftserver


Protocols and ports

tcp: 25565
source ip ranges: 0.0.0.0/0


-------------------------------------------------------------------------


SSH (Secure Shell) linux commands in our compute engine/virtual machine


sudo -s        /// root entitlements

sudo apt-get update        /// updates our software

apt-get install default-jre        /// working on minecraft relases below 1.18, otherways paste: sudo apt install openjdk-17-jdk  

cd home        /// changes directory to home     

mkdir minecraftserver        /// creater minecraftserver directory

cd minecraftserver        /// changes directory to minecraftserver folder

sudo apt-get install wget        /// need to install our minecraft server engine

wget 
