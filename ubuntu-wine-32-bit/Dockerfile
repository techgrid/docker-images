FROM ubuntu:21.10

LABEL maintainer="contact@arpittyagi.com"

RUN apt update

# Install tzdata noninteractivly
ENV DEBIAN_FRONTEND=noninteractive
RUN ln -fs /usr/share/zoneinfo/America/Chicago /etc/localtime
RUN apt -y install tzdata &&

# 32-bit architecture
RUN dpkg --add-architecture i386
RUN apt install -y wine32 xvfb curl wget
RUN wget -P /mono http://dl.winehq.org/wine/wine-mono/6.2.0/wine-mono-6.2.0-x86.msi -q --show-progress --progress=bar:force
RUN nohup Xvfb :0 -screen 0 1920x1280x24 &
