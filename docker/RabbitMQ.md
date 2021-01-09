# RabbitMQ

## run
`docker run -it --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3-management`

## run rabbitmq bash
`docker exec -it rabbitmq /bin/bash`

## list vhosts
`rabbitmqctl list_vhosts`
