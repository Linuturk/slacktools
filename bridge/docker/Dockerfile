FROM ubuntu:vivid

ENV DEBIAN_FRONTEND noninteractive
#ENV NODE_ENV development
ENV USER root

# Usual update / upgrade
RUN apt-get update && apt-get upgrade -y && apt-get dist-upgrade -y

# Install our favorite vcs and other requirements
RUN apt-get install -y git curl wget vim supervisor build-essential libicu-dev apt-utils

# Install nodejs
RUN curl -sL https://deb.nodesource.com/setup | bash -
RUN apt-get install --fix-missing -y nodejs
RUN apt-get clean all

# Get slack-irc
RUN npm -g install npm@latest
RUN npm install -g slack-irc

# Add configurations
ADD config.json slack-irc/config.json

# Add supervisor configs
ADD supervisord.conf supervisord.conf

CMD ["-n", "-c", "/supervisord.conf"]
ENTRYPOINT ["/usr/bin/supervisord"]
