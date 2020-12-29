# RabbitMQ
c# version
## concepts

### CreateModel
- channel
- session
- model

### QueueDeclare
- durable
- exclusive
- autoDelete

### BasicPublish
- exchange
- routingKey
- basicProperties
- body
```c#
string message = "Hello World!";
var body = Encoding.UTF8.GetBytes(message);
```

### BasicQos
`channel.BasicQos(prefetchSize: 0, prefetchCount: 1, global: false);`

not to give more than one message to a worker at a time.

## types

1 just a queue

![new](images/python-one.webp)

identify

## exchange types
- direct
- topic
- headers
- fanout