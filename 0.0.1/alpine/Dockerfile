FROM nibo/jenkins-slave:0.0.1-alpine
MAINTAINER Richard <nibocn@gmail.com>

ARG NODE_VERSION=v8.12.0

RUN \
    # Install tools
    apk add --no-cache --update-cache curl \
        \
    # Install Nodejs
    && mkdir -p /opt/nodejs \
    && curl http://nodejs.org/dist/${NODE_VERSION}/node-${NODE_VERSION}-linux-x64.tar.gz | tar -xzC /opt/nodejs --strip-components=1 \
    && ln -s /opt/nodejs/bin/* /usr/local/bin \
        \
    # Install nrm
    && npm install -g nrm \
    && ln -s /opt/nodejs/bin/nrm /usr/local/bin \
        \
    # Clean resource
    && rm -rf /root/.npm/*

VOLUME /root/.npm

ENV NODEJS_HOME /opt/nodejs
ENV PATH $NODEJS_HOME/bin:$PATH

