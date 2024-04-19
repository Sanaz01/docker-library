FROM python:3.10-slim

# Adding labels for the GitHub Container Registry
LABEL org.opencontainers.image.title="scvi-tools"
LABEL org.opencontainers.image.description="Container image for the use of scvi-tools library for Single-Cell analysis in Python"
LABEL org.opencontainers.image.version="latest"
LABEL org.opencontainers.image.authors="sanaz.iitd@gmail.com"
LABEL org.opencontainers.image.source=https://github.com/Sanaz01/docker-library

# Installing necessary libraries via pip
RUN pip install pandas==2.2.2
RUN pip install matplotlib==3.8.4
RUN pip install scanpy==1.10.1
RUN pip install leidenalg==0.10.2
RUN pip install torch==2.2.2
RUN pip install torchvision==0.17.2
RUN pip install torchaudio==2.2.2
RUN pip install pytorch-cuda==12.1
RUN pip install jaxlib==0.4.26
RUN pip install jax==0.4.26 
RUN pip install scikit-misc==0.3.1
RUN pip install scvi-tools==1.1.2



# RUN conda install anaconda::pandas=2.0.3
# RUN conda install conda-forge::matplotlib=3.8.4
# RUN conda install conda-forge::scanpy=1.10.1
# RUN conda install conda-forge::leidenalg=0.10.2
# RUN conda install pytorch torchvision torchaudio pytorch-cuda=11.7 -c pytorch -c nvidia
# RUN conda install jax jaxlib -c conda-forge
# RUN pip install scvi-tools==1.1.2
