FROM alpine:3.12

RUN apk update && \
    apk upgrade && \
    apk add git sudo make cmake g++

RUN git clone --branch v1.13.0 https://github.com/google/googletest.git && \
    cd googletest && mkdir install && cd install && \
    cmake ../  && make && \
    sudo make install

RUN git clone --branch v1.8.0 https://github.com/google/benchmark.git && \
    cd benchmark && \
    cmake -E make_directory "build" && \
    cmake -E chdir "build" cmake -DBENCHMARK_DOWNLOAD_DEPENDENCIES=on -DCMAKE_BUILD_TYPE=Release .. && \
    sudo cmake --build "build" --config Release --target install

