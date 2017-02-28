# Docker-Kafka

Multi-container Docker Compose configuration for an instance of Apache Kafka, an instance of Apache ZooKeeper, and an instance of an Apache Kafka consumer.

The Dockerfile in the root builds a base image for the other Docker images in the repository. This base image is located in Docker Hub at [jleung51/docker-kafka](https://hub.docker.com/r/jleung51/docker-kafka/).

To execute the Docker Compose multi-container instance, navigate into the `compose/` directory and run:
```
docker-compose up
```

## Credits

Credit goes to Arthur Tse (GitHub: [arthur-tse7](https://github.com/arthur-tse7)) for writing the Dockerfiles and Docker Compose configuration.
