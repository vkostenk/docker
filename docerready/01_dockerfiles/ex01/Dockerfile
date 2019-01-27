FROM debian

ENV TS3SERVER_LICENSE=accept
# need to accept license agreament before launching

EXPOSE 9987/udp 10011 30033
  # Port 9987/udp is default TeamSpeak 3 server port
  # Port 10011 is used for Server Query
  # Port 30033 is used for File transfer
# EXPOSE instruction indicates the ports on which a container listens for connections

WORKDIR /home/teamspeak
# WORKDIR basicly = cd

RUN apt-get update
# apt-get is the command-line tool for handling packages
# like apk
RUN apt-get upgrade -y
RUN apt-get install -y wget bzip2
RUN wget http://dl.4players.de/ts/releases/3.5.1/teamspeak3-server_freebsd_amd64-3.5.1.tar.bz2
RUN tar -xvf teamspeak3-server_freebsd_amd64-3.5.1.tar.bz2
# x = Extract files from an archive, f = Use archive file, v = Operate verbosely(gets extended information)
RUN rm teamspeak3-server_freebsd_amd64-3.5.1.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

CMD ["sh", "ts3server_minimal_runscript.sh"]

# docker build -t ex01 .
# docker run -it --rm --name ex1 -e TS3SERVER_LICENSE=accept -p 9987:9987/udp -p 10011:10011 -p 30033:30033 teamspeak

# https://blog.akpwebdesign.com/2016/08/11/migrating-services-to-docker-pt-1/
# http://dl.4players.de/ts/releases/3.5.1/
