FROM ubuntu:latest
ARG jarPath=henge-service.jar

RUN apt-get update

RUN apt-get -y install wget
RUN apt-get -y install python-setuptools python-dev build-essential
RUN easy_install pip
RUN pip install cqlsh

COPY java.sh /tmp/java.sh
RUN sh /tmp/java.sh
COPY $jarPath /tmp/henge.jar
COPY start_property_server.sh /tmp/start_property_server.sh
COPY load.cql /tmp/load.cql
ENTRYPOINT ["sh", "/tmp/start_property_server.sh"]
