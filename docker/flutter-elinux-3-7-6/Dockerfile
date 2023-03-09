FROM ubuntu:20.04

# Set timezone
ENV TZ=Asia/Tokyo
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Update apt
RUN apt-get update

# Install dependencies
RUN apt-get install -y curl unzip git clang cmake pkg-config
RUN apt-get install -y libegl1-mesa libgles2-mesa libxkbcommon-dev
RUN apt-get install -y libgtk-3-dev ninja-build
RUN apt-get install -y libwayland-dev
RUN apt-get install -y libdrm-dev libgbm-dev libinput-dev libudev-dev libsystemd-dev

# Install Flutter eLinux
RUN git clone -b 3.7.6 https://github.com/sony/flutter-elinux.git
RUN mv flutter-elinux /opt/

ENV PATH=$PATH:/opt/flutter-elinux/bin
ENV PATH=$PATH:/opt/flutter-elinux/flutter/bin

# Check Flutter eLinux
RUN flutter-elinux doctor
RUN flutter-elinux devices