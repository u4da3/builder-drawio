FROM ubuntu:latest
RUN \
    apt-get update && \
    apt-get -y install \
        libgtk-3-0 libnotify4 libnss3 libxss1 libxtst6 libatspi2.0-0 libappindicator3-1 libsecret-1-0 libasound2 \
        nodejs npm xdg-utils xvfb wget && \
    apt-get clean
RUN \
    wget https://github.com/jgraph/drawio-desktop/releases/latest/download/latest-linux.yml && \ 
    DRAWIO_VERSION=`grep version latest-linux.yml | cut -f2 -d' '` && \
    DRAWIO_DEB_NAME=draw.io-amd64-${DRAWIO_VERSION}.deb && \ 
    wget https://github.com/jgraph/drawio-desktop/releases/latest/download/${DRAWIO_DEB_NAME} && \ 
    dpkg -i ${DRAWIO_DEB_NAME} && \
    rm -f latest-linux.yml ${DRAWIO_DEB_NAME} && \
    npm install -g xvfb-maybe && \
    export PATH=$PATH:`npm bin -g`
ENTRYPOINT ["/usr/bin/env","xvfb-maybe","drawio","--no-sandbox"]
CMD ["--help"]