FROM debian:10

ENV PATH="/usr/local/mipsel-unknown-elf/bin:${PATH}"
ENV PSN00BSDK_TC="/usr/local/mipsel-unknown-elf/"
RUN mkdir "/usr/local/PSN00BSDK_LIBS"
ENV PSN00BSDK_LIBS="/usr/local/PSN00BSDK_LIBS/"

RUN echo "deb http://ftp.de.debian.org/debian stretch main" | tee -a /etc/apt/sources.list

RUN apt update -y && apt install -y git wget xz-utils locales build-essential texinfo libtinyxml2-dev libmpc* libmpfr4 && rm -rf /var/lib/apt/lists/* \
    && localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8 

RUN wget -q http://lameguy64.net/download/psn00bsdk/toolchain/gcc-7.4.0-mipsel-unknown-elf_linux-amd64.tar.xz -O /tmp/gcc-7.4.0-mipsel-unknown-elf_linux-amd64.tar.xz && tar -xf /tmp/gcc-7.4.0-mipsel-unknown-elf_linux-amd64.tar.xz -C /

RUN git clone https://github.com/Lameguy64/PSn00bSDK.git /tmp/psdk && cd /tmp/psdk && cd /tmp/psdk/tools && make && make install && mv /tmp/psdk/tools/bin/* /usr/bin && cd /tmp/psdk/libpsn00b && make && make install

