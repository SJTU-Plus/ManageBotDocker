FROM ubuntu:latest
LABEL maintainer="iskyzh@gmail.com"

WORKDIR /app
RUN apt-get update -y -qq && apt-get install wget -qq
RUN wget https://github.com/Mrs4s/go-cqhttp/releases/download/v0.9.18/go-cqhttp-v0.9.18-linux-amd64.tar.gz && tar -xvf go-cqhttp-v0.9.18-linux-amd64.tar.gz && rm go-cqhttp-v0.9.18-linux-amd64.tar.gz
COPY run.sh /app
CMD /app/run.sh
