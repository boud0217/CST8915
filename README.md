# LAB 1
Video link : [CST8915Lab1](https://youtu.be/AudO7oLcBAk)

## Brief Technical Explanation
### Order Service
This service coded using NodeJS.js framework receive orders from the strore-front and publish them on RabbitMQ streams. The framework used is Express.js.
It receive the orders by HTTP POST on port 3000 and send the streams on the port 15672. 

### Product Service
This code sets up a web server in Rust, which exposes a single endpoint and returns a list of products in JSON format. Only the Store-front is communicating with it. The only route is "/products" and only receive GET HTTP calls. Wrap is the framework used. 
The server listen to the port 3030 and return products coded locally. 

### Store Front
This is the front end to get access to the service describe above. It listen to the user products selection and send it to the order service. It is coded in Javascript using VueJS framework.
It is fetching products from Product service via 3030 port and sending the orders to Order Service via 3000 port.
