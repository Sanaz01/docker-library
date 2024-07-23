# FROM rstudio/r-base:4.3-jammy
FROM rocker/r-base:4.3.3

# Adding labels for the GitHub Container Registry
LABEL org.opencontainers.image.title="seurat"
LABEL org.opencontainers.image.description="Container image for the use of seurat package for Single-Cell analysis in R"
LABEL org.opencontainers.image.version="latest"
LABEL org.opencontainers.image.authors="sanaz.iitd@gmail.com"
LABEL org.opencontainers.image.source=https://github.com/Sanaz01/docker-library

RUN apt-get update
RUN apt-get -y install curl libxml2 libxml2-dev libcurl4-openssl-dev libssl-dev r-cran-openssl


# install packages
RUN Rscript -e "install.packages('dplyr', version = '1.1.4',  repos='http://cran.us.r-project.org')"
RUN Rscript -e "install.packages('hdf5r', repos='http://cran.us.r-project.org')"
RUN Rscript -e "install.packages('Seurat',  version = '5.0.3', repos='http://cran.us.r-project.org')"
RUN Rscript -e "install.packages('sctransform', version = '0.4.1',  repos='http://cran.us.r-project.org')"
RUN Rscript -e "install.packages('tidyverse', version = '2.0.0',  repos='http://cran.us.r-project.org')"
RUN Rscript -e "install.packages('ggplot2', version = '3.5.0', repos='http://cran.us.r-project.org')"
RUN Rscript -e "install.packages('gridExtra', version = '2.3', repos='http://cran.us.r-project.org')"
RUN Rscript -e "install.packages('devtools', version = '2.4.5', repos='http://cran.us.r-project.org')"
# RUN Rscript -e "devtools::install_github('immunogenomics/presto')"
RUN Rscript -e "install.packages('presto', repos='http://cran.us.r-project.org')"



