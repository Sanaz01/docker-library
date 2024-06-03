# Using Python base image
FROM python:3.10-slim

# Adding labels for the GitHub Container Registry
LABEL org.opencontainers.image.title="scanpy"
LABEL org.opencontainers.image.description="Container image for the use of Scanpy library for Single-Cell analysis in Python"
LABEL org.opencontainers.image.version="latest"
LABEL org.opencontainers.image.authors="sanaz.iitd@gmail.com"
LABEL org.opencontainers.image.source=https://github.com/Sanaz01/docker-library

# Installing packages via pip
RUN pip install scanpy==1.10.1 leiden-clustering==0.1.0
