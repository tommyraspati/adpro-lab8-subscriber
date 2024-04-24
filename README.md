# Reflection 1
## AMQP and Connection Details Explained

### What is AMQP?

AMQP (Advanced Message Queuing Protocol) is an open standard application layer protocol for message-oriented middleware, with a focus on queuing, routing (point-to-point and publish-and-subscribe), reliability and security. It is designed to facilitate the interoperability among different systems and languages by defining a common protocol that can be implemented across a wide variety of platforms.

### What does "guest:guest@localhost:5672" mean?

This string is a connection URI used to connect to a message broker that supports AMQP, in this case, RabbitMQ by default:

- **guest:guest** - These are the default username and password for RabbitMQ when accessing the broker installed on a local machine. It is highly recommended to change these in production environments to ensure security.

- **localhost** - This refers to the local computer where the RabbitMQ server is running. 'localhost' is used to connect to services running on the same machine as the client.

- **5672** - This is the default port used by RabbitMQ for clients connecting using the AMQP protocol. It's important that this port is open and accessible on the machine running the RabbitMQ server.

These components together form the URI needed to establish a connection to the AMQP server, allowing the application to send and receive messages.

![gambar](https://github.com/tommyraspati/adpro-lab8-publisher/assets/89284213/daadb8de-5c8c-4a07-bd68-601646dab9d5)
The graph above indicates that there were 10 messages in the queue at one point. This occurred because the subscriber's speed in consuming data from the queue was slower than the speed at which messages were incoming. As a result, messages remained in the queue until the subscriber consumed them.

![gambar](https://github.com/tommyraspati/adpro-lab8-publisher/assets/89284213/e1c43d5b-2ca6-41b8-b2d1-587f019cabb4)
![gambar](https://github.com/tommyraspati/adpro-lab8-publisher/assets/89284213/5bc901e6-5984-409b-b00c-a273e9466069)
In this scenario, I ran the publisher command with the same amount as before but with 3 subscribers consuming these messages. As shown in the graph, the number of messages in the queue decreased more rapidly than in the previous case. This is because there are more subscribers consuming the messages sent by the publisher, resulting in the number of messages in the queue waiting to be consumed decreasing more quickly.
