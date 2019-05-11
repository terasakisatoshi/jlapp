FROM arm32v7/julia:1.0.3-stretch
#FROM terasakisatoshi/jlcross:rpi3-1.1.0
MAINTAINER SATOSHI TERASAKI

RUN apt-get update && apt-get install -y \
    build-essential \
    bzip2 \
    git \
    fbi \
    imagemagick \
    libgtk-3-dev \
    libpango1.0-0 \
    libglib2.0-0 \
    libcairo2 \
    libpng-dev \
    wget
# install GR dep
RUN apt-get update && apt-get install -y \
    libx11-dev libxft-dev libxt-dev \
    libgl1-mesa-dev python-opengl \
    qt4-dev-tools pyqt4-dev-tools \
    texlive-latex3 dvipng \
    libgs-dev \
    libmupdf-dev \
    libgtk2.0-dev \
    libwxgtk3.0-dev \
    libglfw3-dev \
    libzmq3-dev
#RUN apt-get install qt4-default
RUN cd /tmp && \
    git clone https://github.com/jheinen/gr && \
    cd gr && \
    make GRDIR=/opt/gr && make install && \
    cd ../ && rm -r gr

ENV PATH=/root/berryconda3/bin:$PATH
RUN wget --quiet https://github.com/jjhelmus/berryconda/releases/download/v2.0.0/Berryconda3-2.0.0-Linux-armv7l.sh && \
    /bin/bash Berryconda3-2.0.0-Linux-armv7l.sh -bf && \
    rm Berryconda3-2.0.0-Linux-armv7l.sh

