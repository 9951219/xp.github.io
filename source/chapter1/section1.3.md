# RabbitMQ的多种Exchange类型

Exchange分发消息时，根据类型的不同分发策略有区别。目前共四种类型：direct、fanout、topic、headers(headers匹配AMQP消息的header而不是路由键(Routing-key)，此外headers交换器和direct交换器完全一致，但是性能差了很多，目前几乎用不到了。所以直接看另外三种类型。)。

> direct

![img](https:////upload-images.jianshu.io/upload_images/5015984-13db639d2c22f2aa.png?imageMogr2/auto-orient/strip|imageView2/2/w/385/format/webp)

MacDown Screenshot



消息中的路由键(routing key)如果和Binding中的binding key一致，交换器就将消息发到对应的队列中。路由键与队列名完全匹配。

> fanout

![img](https:////upload-images.jianshu.io/upload_images/5015984-2f509b7f34c47170.png?imageMogr2/auto-orient/strip|imageView2/2/w/463/format/webp)

MacDown Screenshot



每个发到fanout类型交换器的消息都会分到所有绑定的队列上去。fanout交换器不处理该路由键，只是简单的将队列绑定到交换器上，每个发送到交换器的消息都会被转发到与该交换器绑定的所有队列上。很像子网广播，每台子网内的主机都获得了一份复制的消息。fanout类型转发消息是最快的。

> topic

![img](https:////upload-images.jianshu.io/upload_images/5015984-275ea009bdf806a0.png?imageMogr2/auto-orient/strip|imageView2/2/w/558/format/webp)

MacDown Screenshot



topic交换器通过模式匹配分配消息的路由键属性，将路由键和某个模式进行匹配，此时队列需要绑定到一个模式上。它将路由键(routing-key)和绑定键(bingding-key)的字符串切分成单词，这些单词之间用点隔开。它同样也会识别两个通配符："#"和"*"。#匹配0个或多个单词，匹配不多不少一个单词。

