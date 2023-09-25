FROM --platform=linux/amd64 ubuntu:22.04

RUN apt update
RUN apt install -y \
    curl git wget ca-certificates curl gnupg \
    lldb python3-lldb-14
RUN ln -s /usr/lib/llvm-14/lib/python3.10/dist-packages/lldb/* /usr/lib/python3/dist-packages/lldb/
# swift
RUN mkdir temp && cd temp && \
    wget https://download.swift.org/swift-5.8.1-release/ubuntu2204/swift-5.8.1-RELEASE/swift-5.8.1-RELEASE-ubuntu22.04.tar.gz && \
    tar xvfz swift-5.8.1-RELEASE-ubuntu22.04.tar.gz && \
    cp -R swift-5.8.1-RELEASE-ubuntu22.04/* / && cd .. 
RUN rm -rf ./temp
# other packages
RUN apt install -y clang curl git libfontconfig-dev libgl-dev libxext-dev make nfs-client ninja-build cmake
# final symlink for python
RUN ln -s /usr/bin/python3 /usr/bin/python
# install xvfb and vscode dependencies for testing
RUN apt install -y xvfb libnss3 libatk1.0-0 libatk-bridge2.0-0 libgtk-3-0 libgbm-dev libasound2
