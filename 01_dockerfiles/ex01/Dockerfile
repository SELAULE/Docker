FROM debian

RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install -y wget
RUN apt-get install -y bzip2
RUN wget http://dl.4players.de/ts/releases/3.0.13.8/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2
RUN tar xvf teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2
RUN rm -rf teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2
# WORKDIR /teamspeak3-server_linux_amd64
# RUN ls
RUN ./teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh start
