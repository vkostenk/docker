FROM debian

RUN apt-get update && apt-get install -y cowsay fortune lolcat
# fortune - displays a pseudorandom message from a database
# cowsay - program that generates picture of cow with message
# lolcat - fot color

ENTRYPOINT /usr/games/fortune | /usr/games/cowsay | /usr/games/lolcat

# How to build it?
# docker build -t ex00 .

# How to run it?
# docker run --rm -t ex00
