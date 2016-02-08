FROM node
MAINTAINER Justin Phelps <linuturk@onitato.com>

# Set various options
USER root
WORKDIR /root

# Clone down the code
RUN git clone https://github.com/outsideris/slack-invite-automation.git

# Change into the directory
WORKDIR /root/slack-invite-automation

# Install
RUN npm install

# Add configuration file
ADD config.js config.js

EXPOSE 3000
ENTRYPOINT /root/slack-invite-automation/bin/www
