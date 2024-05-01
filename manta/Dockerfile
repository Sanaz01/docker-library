FROM ubuntu:20.04

# Adding labels for the GitHub Container Registry
LABEL org.opencontainers.image.title="manta"
LABEL org.opencontainers.image.description="Container image for the use of Manta: Structural Variant and indel Caller"
LABEL org.opencontainers.image.version="latest"
LABEL org.opencontainers.image.authors="sanaz.iitd@gmail.com"
LABEL org.opencontainers.image.source=https://github.com/Sanaz01/docker-library
ENV manta_version 1.6.0

RUN apt-get update \
    && apt-get install -y wget bzip2 python3.7 \
    && rm -rf /var/lib/apt/lists/*

RUN wget https://github.com/Illumina/manta/releases/download/v${manta_version}/manta-${manta_version}.centos6_x86_64.tar.bz2 && \
    tar -jxvf manta-${manta_version}.centos6_x86_64.tar.bz2 && \
    rm manta-${manta_version}.centos6_x86_64.tar.bz2 && \
    mv manta-${manta_version}.centos6_x86_64 manta
