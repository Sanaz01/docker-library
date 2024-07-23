FROM ubuntu:xenial

## bedtools ##

WORKDIR /usr/local
RUN git clone https://github.com/arq5x/bedtools2.git && \
    cd /usr/local/bedtools2 && \
    git checkout v2.27.0 && \
    make && \
    ln -s /usr/local/bedtools2/bin/* /usr/local/bin/

