FROM ubuntu as singularityimg
LABEL maintainer="Jennifer Chang <jennifer.chang.chang@gmail.com>"

RUN apt-get update
RUN apt-get install -y \
    bash \
    git \
    python \
    dh-autoreconf \
    build-essential \
    libarchive-dev

RUN git clone https://github.com/singularityware/singularity.git
RUN cd singularity; ./autogen.sh
RUN cd singularity; ./configure --prefix=/usr/local --sysconfdir=/etc
RUN cd singularity; make
RUN cd singularity; make install

ENV PATH=/:$PATH