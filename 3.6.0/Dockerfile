FROM rocker/tidyverse:3.6.0
MAINTAINER "Rainer Krug" Rainer.Krug@uzh.ch Rainer@krugs.de

# 1. Install java (see https://tecadmin.net/install-oracle-java-11-on-debian-9-stretch/)
RUN apt-get update \
  && apt-get install -y default-jdk \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/

# 2. Download and install imageJ.
# RUN wget http://wsr.imagej.net/distros/linux/ij152-linux64-java8.zip \
COPY ij152-linux64-java8.zip .
RUN unzip ij152-linux64-java8.zip \
  && rm ij152-linux64-java8.zip

# 3. Download the LOCI Bio-formats plug-in and place the jar file in the plug-ins folder of ImageJ.
# RUN wget https://downloads.openmicroscopy.org/bio-formats/5.1.10/artifacts/loci_tools.jar -P ij152-linux64-java8/plugins
COPY ParticleLinker.jar ImageJ/plugins

# 4. Download the ParticleLinker.
#RUN wget NEED TO GET THE URL

# 5. Download and install the R - The statistical computing environment, and potentially Rstudio.
# Already in the source image

# Install bemovi from github / master
RUN installGithub.r pennekampster/bemovi@master \
  && rm -rf /tmp/downloaded_packages/
