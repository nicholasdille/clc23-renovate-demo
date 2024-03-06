#syntax=docker/dockerfile:1.6.0@sha256:ac85f380a63b13dfcefa89046420e1781752bab202122f8f50032edf31be0021

FROM ubuntu:22.04@sha256:77906da86b60585ce12215807090eb327e7386c8fafb5402369e421f44eff17e AS base

SHELL [ "bash", "-o", "errexit", "-c"]
ARG DEBIAN_FRONTEND=noninteractive

COPY <<no-recommends <<no-suggests /etc/apt/apt.conf.d/
APT::Install-Recommends "false";
no-recommends
APT::Install-Suggests "false";
no-suggests

RUN <<EOF
grep security /etc/apt/sources.list >/etc/apt/sources.list.d/security.list
apt-get update -o Dir::Etc::SourceList=/etc/apt/false -o Dir::Etc::SourceParts=/etc/apt/sources.list.d
apt-get upgrade -y
rm -f /etc/apt/sources.list.d/security.list
EOF

ARG ref=main
LABEL org.opencontainers.image.source="https://github.com/nicholasdille/clc23-renovate-demo" \
      org.opencontainers.image.title="Ubuntu" \
      org.opencontainers.image.description="Base image for Ubuntu"