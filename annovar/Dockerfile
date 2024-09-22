
# Using the Ubuntu base image
FROM ubuntu:noble-20240114

# Adding labels for the GitHub Container Registry
LABEL org.opencontainers.image.title="Annovar"
LABEL org.opencontainers.image.description="Container image for the use of Annovar"
LABEL org.opencontainers.image.version="latest"
LABEL org.opencontainers.image.authors="sanaz.iitd@gmail.com"
LABEL org.opencontainers.image.source=https://github.com/Sanaz01/docker-library
LABEL org.opencontainers.image.version="hg38"


# Installing prerequisites
RUN apt-get update \
  && apt-get install -y --no-install-recommends build-essential=12.10ubuntu1 wget=1.21.4-1ubuntu4 perl=5.38.2-3.2build2 \
  && rm -rf /var/lib/apt/lists/*

# Pulling and extracting Annovar source code
RUN wget -q --no-check-certificate http://www.openbioinformatics.org/annovar/download/0wgxR2rIVP/annovar.latest.tar.gz && tar -xvf annovar.latest.tar.gz
ENV PATH="${PATH}:/annovar"

# Downloading GRCh38 resources
RUN annotate_variation.pl -buildver hg38 -downdb -webfrom annovar refGene /annovar/humandb/
RUN annotate_variation.pl -buildver hg38 -downdb -webfrom annovar knownGene /annovar/humandb/
RUN annotate_variation.pl -buildver hg38 -downdb -webfrom annovar cosmic70 /annovar/humandb/
RUN annotate_variation.pl -buildver hg38 -downdb -webfrom annovar esp6500siv2_all /annovar/humandb/
RUN annotate_variation.pl -buildver hg38 -downdb -webfrom annovar clinvar_20240611 /annovar/humandb/
RUN annotate_variation.pl -buildver hg38 -downdb -webfrom annovar dbnsfp47a_interpro /annovar/humandb/
RUN annotate_variation.pl -buildver hg38 -downdb -webfrom annovar gnomad41_exome /annovar/humandb/
RUN annotate_variation.pl -buildver hg38 -downdb -webfrom annovar gnomad41_genome /annovar/humandb/

# Cleanup
RUN rm -rf annovar.latest.tar.gz /annovar/humandb/hg19_*

