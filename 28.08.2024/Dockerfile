#No correct
FROM ubuntu:latest

RUN apt-get update 
RUN apt-get install -y curl

ADD httpd.conf /etc/httpd/conf/httpd.conf

WORKDIR /root

ENTRYPOINT ["ping"]

CMD ["google.com"]


#After hadolint check
FROM ubuntu:22.04

RUN apt-get update COPY&& apt-get install -y curl=7.58.0 \
    --no-install-recommends \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

COPY httpd.conf /etc/httpd/conf/httpd.conf

WORKDIR /root

ENTRYPOINT ["ping"]

CMD ["google.com"]