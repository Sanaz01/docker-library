# Using the Miniconda base image
FROM continuumio/miniconda3:24.1.2-0

# Adding labels for the GitHub Container Registry
LABEL org.opencontainers.image.title="scanpy"
LABEL org.opencontainers.image.description="Container image for the use of Scanpy library for Single-Cell analysis in Python"
LABEL org.opencontainers.image.version="0.1"
LABEL org.opencontainers.image.authors="sanaz.iitd@gmail.com"
LABEL org.opencontainers.image.source=https://github.com/Sanaz01/docker-library

# Switching from hard-links to copies
RUN conda config --set always_copy true

# Installing necessary libraries via conda
RUN conda install anaconda::pandas=2.0.3
RUN conda install conda-forge::matplotlib=3.8.4
RUN conda install conda-forge::scanpy=1.10.1
RUN conda install conda-forge::leidenalg=0.10.2
