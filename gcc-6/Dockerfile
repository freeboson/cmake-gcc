FROM gcc:6

ENV CMAKE_MINOR_VERSION 3.7
ENV CMAKE_VERSION 3.7.2


ADD https://cmake.org/files/v3.7/cmake-3.7.2-Linux-x86_64.sh /tmp
ADD https://cmake.org/files/v3.7/cmake-3.7.2-SHA256.txt /tmp
ADD https://cmake.org/files/v3.7/cmake-3.7.2-SHA256.txt.asc" /tmp

RUN gpg --keyserver pgp.mit.edu --recv-keys 4b9e84567bfb4eda

RUN pushd /tmp \
    && gpg --batch --verbose --verify cmake-${CMAKE_VERSION}-SHA-256.txt.asc cmake-${CMAKE_VERSION}-SHA-256.txt \
    && sha256sum -c --ignore-missing cmake-${CMAKE_VERSION}-SHA-256.txt \
    && mkdir -p /opt/cmake \
    && sh cmake-${CMAKE_VERSION}-Linux-x86_64.sh --prefix=/opt/cmake --skip-license --exclude-subdir \
    && popd

