#
# Apache Synapse 2.1.0
#
FROM azul/zulu-openjdk:7
MAINTAINER Totto (totto@totto.org)

RUN apt-get -qq update \
    && apt-get -yqq install ca-certificates ssl-cert wget



# copy zip from local folder to container
RUN wget -P /opt http://apache.mirrors.lucidnetworks.net//synapse/2.1.0/synapse-2.1.0-bin.tar.gz && \
    apt-get update && \
    apt-get install -y zip && \
    apt-get clean && \
    gz -d synapse-2.1.0-bin.tar.gz \
    tar xvf synapse-2.1.0-bin.tar.gz 
#    rm /opt/synapse-2.1.0-bin.tar.gz

ADD synapse.xml  /opt/synapse-2..1.0/repository/conf/synapse-config/synapse.xml  

ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64
EXPOSE 9443
CMD ["/opt/synapse-2.1.0/bin/synapse.sh"]
