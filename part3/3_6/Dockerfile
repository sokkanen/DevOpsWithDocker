FROM ubuntu:16.04 as build-stage

WORKDIR /build 
RUN apt-get update && apt-get install -y wget tar && \
    wget https://files.pythonhosted.org/packages/41/ee/93f3dee2155209e46fe68a3f3adfb1fb66df86ad1c3a828ea892635eae4c/yle-dl-20190614.tar.gz && \
    tar -zxvf yle-dl-20190614.tar.gz

FROM python:3.8-rc-alpine

RUN apk add --no-cache bash ffmpeg gcc libxml2-dev libxslt-dev make musl-dev php7 php7-bcmath \
    php7-curl php7-simplexml wget 
COPY --from=build-stage /build /build
ENV LC_ALL=C.UTF-8
WORKDIR /build
RUN pip install -U pip setuptools youtube_dl yle-dl && adduser -D -u 666 nonroot
WORKDIR /saved
RUN chown nonroot /saved /build
ENTRYPOINT ["yle-dl"]
USER nonroot
