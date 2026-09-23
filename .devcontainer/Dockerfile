FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

# ------------------------------------------------------------
# GROMACS + basic scientific tools
# ------------------------------------------------------------
RUN apt-get update && \
    export DEBIAN_FRONTEND=noninteractive && \
    apt-get install -y --no-install-recommends \
        gromacs \
        python3 \
        python3-pip \
        python3-venv \
        git \
        wget \
        curl \
	emacs \
        nano \
        vim \
        && rm -rf /var/lib/apt/lists/*

# ------------------------------------------------------------
# Python environment for analysis
# ------------------------------------------------------------
RUN python3 -m venv /opt/md-python && \
    /opt/md-python/bin/pip install --upgrade pip && \
    /opt/md-python/bin/pip install \
        numpy \
        scipy \
        pandas \
        matplotlib \
        jupyterlab \
        MDAnalysis \
        nglview

ENV PATH="/opt/md-python/bin:${PATH}"