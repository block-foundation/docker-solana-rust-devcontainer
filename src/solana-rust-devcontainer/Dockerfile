# syntax=docker/dockerfile:1.4


# Base Image
# =============================================================================
FROM rust:latest

RUN \
    apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y \
        curl \
        pkg-config \
        libssl-dev \
        build-essential \
        python3-dev \
        python3-pip

RUN \
    curl -sSf https://sh.rustup.rs | sh -s -- -y && \
    rustup update && \
    rustup install nightly && \
    rustup default nightly && \
    rustup component add rustfmt-preview --toolchain=nightly && \
    cargo install --git https://github.com/solana-labs/solana.git solana-cli

WORKDIR /workspace
