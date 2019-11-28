FROM		debian
MAINTAINER	matheme <matheme@student.le-101.fr>
EXPOSE		9987/udp 10011 30033
WORKDIR 	/home/teamspeak
RUN			apt-get update
RUN			apt-get upgrade -y
RUN			apt-get install -y wget bzip2 

RUN wget -O teamspeak_serveur.bz2 https://files.teamspeak-services.com/releases/server/3.9.1/teamspeak3-server_linux_amd64-3.9.1.tar.bz2
RUN	tar -xvf teamspeak_serveur.bz2
RUN rm teamspeak_serveur.bz2

WORKDIR		teamspeak3-server_linux_amd64
RUN			touch .ts3server_license_accepted
ENTRYPOINT	sh ts3server_minimal_runscript.sh

# docker build -t ex01 .
# docker run --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 -it ex01 /bin/sh
