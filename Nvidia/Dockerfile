FROM nvidia/cuda:11.7.1-cudnn8-runtime-ubuntu22.04

# To avoid tzdata blocking the build with frontend questions
ENV DEBIAN_FRONTEND=noninteractive 

RUN apt-get -y update && apt-get -y install --no-install-recommends \
    libopenjp2-7-dev libopenjp2-tools \
    openslide-tools \
    libgl1 \
    && pip3 --no-cache-dir install tiatoolbox \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

CMD ["python3"]