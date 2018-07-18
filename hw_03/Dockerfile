FROM alpine:3.5
LABEL maintainer="Jennifer Chang <jennifer.chang.chang@gmail.com>"
RUN apk update
RUN apk add git \
    	    bash \
	    perl \
	    R \
	    curl

RUN git clone https://github.com/j23414/cavatica.git

CMD ls; ls cavatica/
