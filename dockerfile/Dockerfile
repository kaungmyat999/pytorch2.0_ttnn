FROM ghcr.io/tenstorrent/tt-metal/tt-metalium/ubuntu-22.04-dev-amd64:latest AS release

# Install system-level dependencies (using apt-get)
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        sudo \
        libgl1-mesa-glx \
        git-lfs \
        libsndfile1 \
        docker.io && \
    rm -rf /var/lib/apt/lists/*  # Clean up apt cache

# Initialize git lfs (must be done before any git operations)
RUN git lfs install
CMD ["pytest", "./tests/autogen_op/GPT-2/test_GPT-2_aten__softmax_default.py"]
