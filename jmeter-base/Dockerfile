FROM openjdk:8-jre-slim
ARG JMETER_VERSION

ENV JMETER_VERSION ${JMETER_VERSION:-5.2.1}
LABEL Description="This image is used to start the Apache JMeter Master Executable" Vendor="Collabnix" Version="1.0"
# Installig Pre-requisite Packages like wget & JRE
RUN apt-get clean && \
        apt-get update && \
        apt-get -qy install \
                        wget \
                        telnet \
                        iputils-ping \
                        unzip
# Installing jmeter
RUN   mkdir /jmeter
RUN   cd /jmeter
RUN   wget https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-$JMETER_VERSION.tgz
RUN   tar -xzf apache-jmeter-$JMETER_VERSION.tgz
RUN   rm apache-jmeter-$JMETER_VERSION.tgz
# Settingt Jmeter Home
ENV JMETER_HOME /apache-jmeter-$JMETER_VERSION
# Finally Adding Jmeter to the Path
ENV PATH $JMETER_HOME/bin:$PATH
COPY config/user.properties $JMETER_HOME/bin/user.properties
