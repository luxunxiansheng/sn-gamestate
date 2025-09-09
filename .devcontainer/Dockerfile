FROM rayproject/ray:latest-py39-gpu

# Switch to ro# Install Python dependencies
# Moved to postCreateCommand in devcontainer.jsonser for installation and setup
USER root

# Install required system dependencies for matplotlib, OpenCV, and H.264 codec support
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    pkg-config \
    libfreetype6-dev \
    libpng-dev \
    libqhull-dev \
    libagg-dev \
    libcairo2-dev \
    libffi-dev \
    python3-dev \
    # H.264 codec and video processing dependencies
    libx264-dev \
    libx265-dev \
    libvpx-dev \
    libfdk-aac-dev \
    libmp3lame-dev \
    libopus-dev \
    # FFmpeg with H.264 support
    ffmpeg \
    libavcodec-dev \
    libavformat-dev \
    libavutil-dev \
    libswscale-dev \
    libswresample-dev \
    # Additional video processing libraries
    libgstreamer1.0-dev \
    libgstreamer-plugins-base1.0-dev \
    libgtk-3-dev \
    libjpeg-dev \
    libpng-dev \
    libtiff-dev \
    libdc1394-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    # Install uv
    && curl -LsSf https://astral.sh/uv/install.sh | sh

ENV PATH="/root/.local/bin:/root/.cargo/bin:$PATH"

# Set working directory
WORKDIR /workspaces/sn-gamestate

# Copy project files
COPY . .




