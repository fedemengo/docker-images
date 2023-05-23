FROM alpine:3.12

RUN apk update && \
    apk upgrade && \
    apk add git sudo make cmake g++

RUN git clone --branch v1.13.0 https://github.com/google/googletest.git && \
    cd googletest && mkdir install && cd install && \
    cmake ../  && make && \
    sudo make install

