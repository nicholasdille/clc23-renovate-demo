#syntax=docker/dockerfile:1.7.0@sha256:dbbd5e059e8a07ff7ea6233b213b36aa516b4c53c645f1817a4dd18b83cbea56

FROM ubuntu:22.04@sha256:f9d633ff6640178c2d0525017174a688e2c1aef28f0a0130b26bd5554491f0da AS base

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