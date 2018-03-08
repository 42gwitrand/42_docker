FROM debian

# Update 
RUN apt-get update && apt-get upgrade -y

# Requirements installs
RUN apt-get install wget -y

# Install teamspeak
RUN mkdir -p /teamspeak/data
RUN mkdir -p /teamspeak/logs
RUN wget http://dl.4players.de/ts/releases/3.0.11.4/teamspeak3-server_linux-amd64-3.0.11.4.tar.gz -O /tmp/ts.tar.gz
RUN tar zxf /tmp/ts.tar.gz -C /tmp
RUN mv /tmp/teamspeak3-server_linux-amd64 /teamspeak/data/teamspeak-server
RUN rm -rf /tmp/*

# Virtual voice server port : 9987
# Server Query port : 10011
# File transfer port : 30033
EXPOSE 9987/udp
EXPOSE 10011
EXPOSE 30033

# Volumes
VOLUME /teamspeak/data
VOLUME /teamspeak/logs

CMD "/teamspeak/data/teamspeak-server/ts3server_minimal_runscript.sh"
