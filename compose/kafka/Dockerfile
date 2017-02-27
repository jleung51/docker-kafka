FROM jleung51/docker-kafka

RUN mkdir /kafka-logs /scripts
ADD ./wait-for-it.sh /scripts/

RUN sed -i "s|#advertised.host.name=<hostname routable by clients>|advertised.host.name=192.168.99.100|g" /opt/${KAFKA}/config/server.properties
RUN sed -i "s|log.dirs=/tmp/kafka-logs|log.dirs=/kafka-logs|g" /opt/${KAFKA}/config/server.properties
RUN sed -i "s|zookeeper.connect=localhost:2181|zookeeper.connect=zookeeper:2181|g" /opt/${KAFKA}/config/server.properties

CMD ./scripts/wait-for-it.sh zookeeper:2181 -s -- /opt/${KAFKA}/bin/kafka-server-start.sh /opt/${KAFKA}/config/server.properties
