FROM ubuntu
ENV ZIG_VERSION=0.14.0-dev.1951+857383689
RUN apt-get update \
    && apt-get install -y curl git xz-utils \
    && apt-get upgrade -y
RUN curl -fsL https://ziglang.org/builds/zig-linux-x86_64-${ZIG_VERSION}.tar.xz \
    | tar -Jx -C /opt \
    && ln -s /opt/zig-linux-x86_64-${ZIG_VERSION}/zig /usr/local/bin/zig
RUN git clone https://github.com/zigtools/zls \
    && cd zls \
    && zig build -Doptimize=ReleaseSafe \
    && ln -s /zls/zig-out/bin/zls /usr/local/bin/zls
WORKDIR /ziglings