# Fianl Project Report
Video link : [CST8915FinalProject](https://youtu.be/lgCiNUyO4-o)  

## Architecture Diagram
![Architecture Diagram](./images/Best%20Buy%20application.png)

## Brief application explanation
This application is an e-commerce platform consisting of multiple services that work together to provide a seamless shopping experience. The main components of the application include:
- **Store Front**: The user interface where customers can browse products and place orders.
- **Store Admin**: An administrative interface for managing products, orders, and other backend operations.
- **Product Service**: A backend service that manages product information and inventory.
- **Order Service**: A backend service that handles order processing and management.
- **MakeLine Service**: A service responsible for preparing orders for shipment.
- **MongoDB**: A NoSQL database used for storing product and order data.
- **RabbitMQ**: A message broker used for communication between services.


## Deployment instructions
To deploy the application, please follow these steps:
1. Make sure you have a Kubernetes cluster set up and `kubectl` configured to interact with it.
2. Clone the repository containing the Kubernetes YAML files for the application.
```bash
    git clone https://github.com/boud0217/CST8915-final.git
```
3. Navigate to the directory containing the YAML files.
4. Apply the YAML files using the following command:
   ```bash
   kubectl apply -f config-maps.yaml
   kubectl apply -f secrets.yaml
   kubectl apply -f aps-all-in-one.yaml
   ```
5. Monitor the deployment status using:
   ```bash
    kubectl get pods
    kubectl get pods
    ```
6. Once all pods are in the `Running` state, access the application services using the appropriate service URLs or load balancer IPs.



## Links Table
| Services | Repositories links | Docker hub images links |
| :--- | :--- | :--- |
| store-front | [store-front-l8](https://github.com/boud0217/store-front-l8) | [store-front](https://hub.docker.com/repository/docker/dolsom/store-front-l8/general) |
| store-admin | [store-admin-l8](https://github.com/boud0217/store-admin-l8) | [store-front](https://hub.docker.com/repository/docker/dolsom/store-admin-l8/general) |
| makeline-service | [makeline-service-l8](https://github.com/boud0217/makeline-service-l8) | [makeline-service](https://hub.docker.com/repository/docker/dolsom/makeline-service-l8/general) |
| Product-service | [product-service-l8](https://github.com/boud0217/product-service-rust-l8) | [product-service](https://hub.docker.com/repository/docker/dolsom/product-service-rust-l8/general) |
| order-service |  [order-service-l8](https://github.com/boud0217/order-service-l8) | [order-service](https://hub.docker.com/repository/docker/dolsom/order-service-l8/general) |