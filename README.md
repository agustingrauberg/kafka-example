# kafka-test
Testing simple kafka implementation

## Initial Setup
Download kafka from https://kafka.apache.org/quickstart
Then extract it, cd into folder and run the following commands, on separated terminals to start the Zookeeper service and Kafka broker service.

## Kafka with ZooKeeper
Run the following commands in order to start all services in the correct order:
### Start the ZooKeeper service
$ bin/zookeeper-server-start.sh config/zookeeper.properties

Open another terminal session and run:
### Start the Kafka broker service
$ bin/kafka-server-start.sh config/server.properties

NOTE: by default server listener will start on the cannonical name of the host, use "listeners=PLAINTEXT://localhost:9092" to run under "localhost"

## Using docker image
### Get the docker image
$ docker pull apache/kafka:3.7.0

### Start the kafka docker container
$ docker run -p 9092:9092 apache/kafka:3.7.0

Once the Kafka server has successfully launched, you will have a basic Kafka environment running and ready to use.

## Read the events
Set "--topic" to the configured name in the code and also the "--bootstrap-server" to the one on the "config/server.properties" file

$ bin/kafka-console-consumer.sh --topic grauberg --from-beginning --bootstrap-server localhost:9092
