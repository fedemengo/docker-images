FROM alpine:3.17

WORKDIR /tmp

# install deps
RUN apk update && \
    apk add curl make gcc libc-dev unzip openssl readline-dev

# install lua
RUN curl -R -O http://www.lua.org/ftp/lua-5.4.4.tar.gz && \
    tar -zxf lua-5.4.4.tar.gz && \
    cd lua-5.4.4/ && make linux test && make install && cd /tmp && rm -rf lua-5.4.4*

# install luarocks
RUN wget https://luarocks.org/releases/luarocks-3.8.0.tar.gz && \
    tar zxpf luarocks-3.8.0.tar.gz && \
    cd luarocks-3.8.0 && ./configure --with-lua-include=/usr/local/include && \
    make && make install && cd /tmp && rm -rf luarocks-3.8.0* && \
    luarocks install readline

WORKDIR /

# install fennel
RUN curl https://fennel-lang.org/downloads/fennel-1.3.0 > /usr/bin/fennel && \
    chmod +x /usr/bin/fennel

ENTRYPOINT ["/usr/bin/fennel"]

