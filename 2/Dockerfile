FROM spgc/duckiebot-base-image:amd

SHELL ["/bin/bash", "-c"]

WORKDIR /workspace

COPY requirements-apt.txt .
COPY requirements-python.txt .

RUN set -e; \
    if [ -s requirements-apt.txt ]; then \
        apt update; \
        xargs -a requirements-apt.txt apt install -y; \
    fi

RUN set -e; \
    if [ -s requirements-python.txt ]; then \
        pip install -r requirements-python.txt; \
    fi

