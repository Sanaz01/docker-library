# Using the Ubuntu base image
FROM ubuntu:noble-20240114

# Adding labels for the GitHub Container Registry
LABEL org.opencontainers.image.title="varscan2"
LABEL org.opencontainers.image.description="Container image for the use of Varscan2: Identify variants, indels and CNAs in NGS data"
LABEL org.opencontainers.image.version="latest"
LABEL org.opencontainers.image.authors="sanaz.iitd@gmail.com"
LABEL org.opencontainers.image.source=https://github.com/Sanaz01/docker-library


RUN apt-get update && apt-get install -y \
	gcc \
    git \
	default-jre \
	# r-base \
	bc

# Installing prerequisites
RUN apt-get install -y --no-install-recommends build-essential=12.10ubuntu1 wget=1.21.4-1ubuntu4 \
    zlib1g-dev=1:1.3.dfsg-3.1ubuntu2 autoconf=2.71-3 automake=1:1.16.5-1.3ubuntu1 \
    libncurses-dev=6.4+20240113-1ubuntu2 libbz2-dev=1.0.8-5.1 liblzma-dev=5.6.1+really5.4.5-1 \
    libssl-dev=3.0.13-0ubuntu3 libcurl4-gnutls-dev=8.5.0-2ubuntu10.1 bedtools=2.31.1+dfsg-2

# Pulling and extracting Samtools source code
RUN wget -q --no-check-certificate https://github.com/samtools/samtools/releases/download/1.11/samtools-1.11.tar.bz2 && tar -jxf samtools-1.11.tar.bz2

# Installing Samtools
WORKDIR /samtools-1.11
RUN ./configure && make && make install
WORKDIR /


## Installing Varscan2
ENV VARSCAN_INSTALL_DIR=/opt/varscan

WORKDIR $VARSCAN_INSTALL_DIR

RUN wget https://github.com/dkoboldt/varscan/releases/download/v2.4.6/VarScan.v2.4.6.jar && \
    ln -s VarScan.v2.4.6.jar VarScan.jar

WORKDIR /

# Clean up
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/install samtools-1.11 samtools-1.11.tar.bz2
