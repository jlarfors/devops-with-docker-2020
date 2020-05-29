FROM ubuntu:16.04


RUN apt update \
    && apt install -y -qq --no-install-recommends \
    ca-certificates \
    curl \
    && rm -rf /var/lib/apt/lists/*

COPY curler.sh /curler.sh

CMD ["/curler.sh"]
