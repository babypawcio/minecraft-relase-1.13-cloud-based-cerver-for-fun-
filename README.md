# minecraft relase 1.13 cloud based server (for fun)
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


2. SSH (Secure Shell) linux commands in our compute engine/virtual machine


sudo -s        /// root entitlements

sudo apt-get update        /// updates our software

apt-get install default-jre        /// working on minecraft relases below 1.18, otherways paste: sudo apt install openjdk-17-jdk  

cd home        /// changes directory to home     

mkdir minecraftserver        /// creater minecraftserver directory

cd minecraftserver        /// changes directory to minecraftserver folder

sudo apt-get install wget        /// need to install our minecraft server engine

wget https://launcher.mojang.com/v1/objects/d0caafb8438ebd206f99930cfaecfa6c9a13dca0/server.jar        /// official 1.13 relase download from minecraft java launcher

ls        /// shows content of a minecraftserver directory [name of our engine: server.jar] (to show our current directory we are working on, please write command: pwd)

java -Xmx2048M -Xms2048M -jar server.jar nogui         /// engine installation (SERVER.JAR)

nano eula.txt        /// enables viewing and changing content of eula, change eula=false to eula=true, for statute confirmation, to only view eula, write cat eula.txt

apt-get install screen        /// installs screen (enables engine to work 24/7 non-stop)

screen java -Xmx2048M -Xms2048M -jar server.jar nogui        /// screen engine installation (SERVER.JAR)


now we can join to our server to generate world structures


stop        /// stops work of our serverk, we can write some changes now

nano server.properties        /// enables to show and change content of server/players entitlements



/// SERVER.PROPERTIES CONTINUATION ///

Change some things to:

enable-command-block=true
motd='YourMotto'
pvp=true
generate-structures=true
difficulty=normal
max-players='YourNumberOfPlayers(Required ~10/20)
online-mode=false       /// players with non-premium minecraft can join to our server
allow-flight=true
view-distance=8
allow-nether=true
spawn-monsters=true

///

To restart your server, write:

screen java -Xmx2048M -Xms2048M -jar server.jar nogui


///

Now you can write commands in console and in minecraft, like 'op', 'gamemode creative', etc.

///

If you want to go back to console and server files, write:


sudo -s

cd /home/minecraft


Now you are in you server directory, if you want to open console, write:

screen -ls

screen -r (paste created process process, for example: 6083.pts-0.minecraftserver) -> screen -r 6083.pts-0.minecraftserver





