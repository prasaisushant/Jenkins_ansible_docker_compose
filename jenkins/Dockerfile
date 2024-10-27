# Dockerfile for Jenkins service
FROM jenkins/jenkins:lts

USER root
## Install relay for webhook relay
RUN apt-get install curl && \
    curl https://my.webhookrelay.com/webhookrelay/downloads/install-cli.sh | bash && \
    chmod +wx /usr/local/bin/relay

USER jenkins