FROM ubuntu:latest

WORKDIR /usr/local/sml

RUN apt-get clean && apt-get update

# Install wget and build tools
RUN apt-get install -y wget build-essential

# Install `multilib` for 32-bit support that SML/NJ requires.
RUN apt-get install -y gcc-multilib g++-multilib

# Install vim
RUN apt-get install -y vim

# Get the source
RUN wget http://smlnj.cs.uchicago.edu/dist/working/110.78/config.tgz

# Extract the source
RUN gunzip <config.tgz | tar xf -

# Modify the configured targets, in order to build the heap2adm program
RUN sed -i /usr/local/sml/config/targets -e "s/\#request heap2asm/request heap2asm/g"

# Compile
RUN /usr/local/sml/config/install.sh

# Modify heap2exec to build 32 bit binaries, as it needs to link against the
# supplied 32 bit SML runtime
RUN sed -i /usr/local/sml/bin/heap2exec -e "s/CC=cc/CC=\"cc -m32\"/g"

# Add SML binaries to path
ENV PATH /usr/local/sml/bin:$PATH

WORKDIR /usr/local/

# Install Tutch 0.53
RUN wget http://www.cse.chalmers.se/~abela/tutch/tutch-0.53-for-sml-110.45.tar.gz && tar xzf tutch-0.53-for-sml-110.45.tar.gz
RUN cd tutch-0.53 && make
ENV PATH="/usr/local/tutch-0.53/bin:${PATH}"

WORKDIR /root/
