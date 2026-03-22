# Benchmark Dockerfile — used to measure Docker layer cache performance.
# Intentionally installs heavy dependencies to create meaningful cache layers.
# Uncached: ~30-60s. Cached with ECR layer cache: <5s.

FROM ubuntu:22.04

RUN apt-get update && apt-get install -y \
    build-essential \
    python3 python3-pip python3-venv \
    curl wget git jq \
    && rm -rf /var/lib/apt/lists/*

RUN python3 -m venv /opt/venv && \
    /opt/venv/bin/pip install --no-cache-dir \
    numpy pandas requests flask boto3

COPY benchmarks/ /app/benchmarks/
WORKDIR /app

CMD ["echo", "Benchmark build complete"]
