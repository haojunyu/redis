# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.195.0/containers/cpp/.devcontainer/base.Dockerfile
# [Choice] Debian / Ubuntu version (use Debian 11/9, Ubuntu 18.04/21.04 on local arm64/Apple Silicon): debian-11, debian-10, debian-9, ubuntu-21.04, ubuntu-20.04, ubuntu-18.04
ARG VARIANT=ubuntu-20.04
FROM mcr.microsoft.com/vscode/devcontainers/cpp:0-${VARIANT}

# [Optional] Uncomment this section to install additional packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>
# 20.04 LTS换源
RUN sed -i "s/archive.ubuntu.com/mirrors.aliyun.com/g" /etc/apt/sources.list && apt update &&\
    # C/C++ 基础软件
    apt install -y --no-install-recommends build-essential clang-8 \
        doxygen wget &&\
    # cmake 安装最新版本3.19.3
    apt install -y --no-install-recommends libssl-dev &&\
    # faiss所需软件swig4.0.1 python3
    apt install -y --no-install-recommends libopenblas-dev swig python3-dev python3-pip &&\
    rm -rf /var/lib/apt/lists/*
    
