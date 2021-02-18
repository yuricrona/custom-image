FROM registry.access.redhat.com/rhel7/rhel:latest
USER root
WORKDIR /opt/app-root/app
RUN curl -fsSL https://rpm.nodesource.com/setup_15.x | bash -
RUN yum -y install make gcc openssl-devel bzip2-devel libffi-devel zlib-devel lzma xz-devel gcc-c++ nodejs
COPY ./Python-3.9.0.tgz .
RUN tar xzf Python-3.9.0.tgz
RUN ./Python-3.9.0/configure --enable-optimization
RUN make install
RUN curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py && python3 get-pip.py
RUN rm -rf /opt/app-root/app/*
