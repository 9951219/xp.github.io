# RabbitMQ简介

RabbitMQ是一个开源的消息代理和队列服务器，用来通过普通协议在不同的应用之间共享数据(跨平台跨语言)。RabbitMQ是使用Erlang语言编写，并且基于AMQP协议实现。

#### RabbitMQ的优势：

- **`可靠性(Reliablity)：`**使用了一些机制来保证可靠性，比如持久化、传输确认、发布确认。
- **`灵活的路由(Flexible Routing)：`**在消息进入队列之前，通过Exchange来路由消息。对于典型的路由功能，Rabbit已经提供了一些内置的Exchange来实现。针对更复杂的路由功能，可以将多个Exchange绑定在一起，也通过插件机制实现自己的Exchange。
- **`消息集群(Clustering)：`**多个RabbitMQ服务器可以组成一个集群，形成一个逻辑Broker。
- **`高可用(Highly Avaliable Queues)：`**队列可以在集群中的机器上进行镜像，使得在部分节点出问题的情况下队列仍然可用。
- **`多种协议(Multi-protocol)：`**支持多种消息队列协议，如STOMP、MQTT等。
- **`多种语言客户端(Many Clients)：`**几乎支持所有常用语言，比如Java、.NET、Ruby等。
- **`管理界面(Management UI)：`**提供了易用的用户界面，使得用户可以监控和管理消息Broker的许多方面。
- **`跟踪机制(Tracing)：`**如果消息异常，RabbitMQ提供了消息的跟踪机制，使用者可以找出发生了什么。
- **`插件机制(Plugin System)：`**提供了许多插件，来从多方面进行扩展，也可以编辑自己的插件。

#### RabbitMQ的整体架构

![img](https:////upload-images.jianshu.io/upload_images/17039633-b0adf1dfade2f122.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200/format/webp)

整体架构.png

#### RabbitMQ的消息流转

![img](https:////upload-images.jianshu.io/upload_images/17039633-6fe89a2074201de7.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200/format/webp)

消息流转