FROM ubuntu:22.04 AS builder-image

# To avoid tzdata blocking the build with frontend questions
ENV DEBIAN_FRONTEND=noninteractive 

RUN apt-get update && apt-get install --no-install-recommends -y python3.10 python3.10-dev python3.10-venv python3-pip python3-wheel build-essential && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# create and activate virtual environment
RUN python3.10 -m venv /opt/venv
ENV PATH="/opt/venv/bin:$PATH"

RUN pip3 install --no-cache-dir tiatoolbox

FROM ubuntu:22.04 AS runner-image
RUN apt-get update && apt-get install --no-install-recommends -y python3.10 python3-venv \
    libopenjp2-7-dev libopenjp2-tools \
    openslide-tools \
    libgl1 \                                          
    && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY --from=builder-image /opt/venv /opt/venv

# activate virtual environment
ENV VIRTUAL_ENV=/opt/venv
ENV PATH="/opt/venv/bin:$PATH"

# CMD ["python3"]