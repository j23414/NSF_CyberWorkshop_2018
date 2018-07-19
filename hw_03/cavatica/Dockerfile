#FROM alpine:3.5
#FROM ubuntu
FROM r-base
LABEL maintainer="Jennifer Chang <jennifer.chang.chang@gmail.com>"
#RUN apk update
RUN apt-get update
#RUN apk add bash \
RUN apt-get install -y bash \
            git \
	    curl \
	    perl \
	    r-base-dev

RUN git clone https://github.com/incertae-sedis/cavatica.git

