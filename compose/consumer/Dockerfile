FROM jleung51/docker-kafka

ARG topic_name=test
ENV TOPIC_NAME=$topic_name

RUN mkdir /scripts
ADD ./wait-for-it.sh /scripts/

CMD ./scripts/wait-for-it.sh zookeeper:2181 -s -- ./scripts/wait-for-it.sh kafka:9092 -s -- /opt/${KAFKA}/bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic ${TOPIC_NAME} && /opt/${KAFKA}/bin/kafka-console-consumer.sh --zookeeper zookeeper:2181 --topic ${TOPIC_NAME}
