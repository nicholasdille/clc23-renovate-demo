#syntax=docker/dockerfile:1.8.1@sha256:e87caa74dcb7d46cd820352bfea12591f3dba3ddc4285e19c7dcd13359f7cefd

FROM ubuntu:22.04@sha256:19478ce7fc2ffbce89df29fea5725a8d12e57de52eb9ea570890dc5852aac1ac AS base

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