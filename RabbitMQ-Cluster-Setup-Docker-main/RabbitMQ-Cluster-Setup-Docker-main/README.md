# RabbitMQ-Cluster-Setup-Docker
```
# Clone Code 
git clone https://github.com/MithunTechnologiesDevOps/RabbitMQ-Cluster-Setup-Docker.git
# Cd to the folder
cd RabbitMQ-Cluster-Setup-Docker
# Create Docker Bridge Network
docker network create rabbits
# Create rabbit mq node1 container
docker run -d --network rabbits -v ${PWD}/config/rabbit-1/:/config/ -e RABBITMQ_CONFIG_FILE=/config/rabbitmq -e RABBITMQ_ERLANG_COOKIE=WIWVHCDTCIUAWANLMQAW -e RABBITMQ_DEFAULT_USER=admin -e RABBITMQ_DEFAULT_PASS=admin --hostname rabbit-1 --name rabbit-1 -p 8081:15672 rabbitmq:3.8-management

# Create rabbit mq node2 container
docker run -d --network rabbits -v ${PWD}/config/rabbit-2/:/config/ -e RABBITMQ_CONFIG_FILE=/config/rabbitmq -e RABBITMQ_ERLANG_COOKIE=WIWVHCDTCIUAWANLMQAW --hostname rabbit-2 --name rabbit-2 rabbitmq:3.8-management

#Access rabbit my managemnt console using your doker server ip on port 8081 . 
Default Rabbit mq console username: admin and password: admin
```
