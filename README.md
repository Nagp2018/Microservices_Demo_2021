# Mircoservices_Demo_2021

1. Eureka Server is Netflix Eureka which requires self registration from client.
2. Api Gateway if netflix zuul gateway for routing to various services and it will register itself to eureka client as well.
3. Product service is going to register itself at eurka server and will make use of eurekaclient for client side load balancing
	and make call to price service to fetch price of product.
	Circuit Breaker pattern (Hystrix) is also implemented at api level if price service is down, for providing default output to user of api.
4. Price Service is going to be register at eureka server and have exposed endpoint for getting price of products.
5. Both of Product and price service route calls are also defined in api-gateway for routing purpose.
6. SpringBootRabbitMQHelloWorld service and spring-boot-rabbitmq-listener service are for async communication demonstration purpose.(Example from javainuse)
7. SpringBootRabbitMQHelloWorld service act as producer of message at rabbitmq.
8. spring-boot-rabbitmq-listener service act as consumer of message from rabbitmq.

Tech Stack:-
Java
Spring boot
Spring cloud

Api calls for testing:-
1. http://localhost:9999/products/001
2. http://localhost:9999/products/price/001