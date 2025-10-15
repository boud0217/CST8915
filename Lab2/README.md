# Lab 2
Video link : [Demo Video](https://youtu.be/MDEO_6qn4Yo)


## What changes did you make to the order-service and product-service to comply with the Configurations and Backing Services factors of the 12-Factor App methodology?
For the Order Service:
- Uses dotenv to load environment variables from a .env file
- Configures the server port via process.env.PORT with a default value of 3000
- Configures RabbitMQ connection via process.env.RABBITMQ_CONNECTION_STRING with a default value of 'amqp://localhost'
- Treats RabbitMQ as an attached backing service via a configurable connection URL
- RabbitMQ connection is established robustly with error handling
- Uses a configurable connection string via environment variable

For the Product Service:
- Uses the dotenv library to load environment variables
- Configures the server port via the PORT environment variable with a default value of 3030


## Why is it important to use environment variables instead of hard-coding configurations in your application?
- Sensitive information like credentials, API keys, and connection strings are secured
- The same code can run in different environments (development, staging, production) with different configurations
- Configuration changes don't require code changes or redeployments.

## Why is it important to have separate repositories for each microservice? How does this help maintain independence and scalability of each service?
- Each microservice can be developed, deployed, and scaled independently
- Different teams can work on different services without interfering with each other
- Each service can use different technologies and frameworks best suited for its functionality
- Easier to manage and maintain smaller codebases
- Independent versioning and deployment cycles for each service
- Fault isolation: issues in one service do not directly impact others
- Scalability: services can be scaled independently based on demand


### Order service repository : [order-service](https://github.com/boud0217/order-service)
### Product service repository : [product-service](https://github.com/boud0217/product-service)
### Store-front repository : [store-front](https://github.com/boud0217/store-front)