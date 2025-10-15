# LAB 3
Video link : [Demo Video](https://youtu.be/5guHAJy7VX4)

## What challenges did you encounter when configuring environment variables in the GitHub Actions workflow?

1. **Sensitive Secrets Management**: Configuring sensitive connection strings (like RABBITMQ_CONNECTION_STRING) required using GitHub secrets to avoid exposing this sensitive information in workflow files.

2. **Environment Consistency**: Ensuring environment variables remained consistent between the local development environment (using .env) and the production environment on Azure Web App Service was challenging.

3. **Dynamic Port Configuration**: Managing PORT variables for different services (3000 for order-service, 3030 for product-service) required careful attention to avoid conflicts and ensure proper functioning on Azure.

4. **Azure-specific Variables**: Integration with Azure Web App Service required configuring additional Azure-specific variables, such as authentication information and deployment settings.


## How does deploying microservices on Azure Web App Service differ from running them locally?
1. **Scalability**: Azure Web App Service allows for automatic scaling based on demand, whereas local environments are limited by the host machine's resources.
2. **Environment Management**: Azure provides a managed environment with built-in features for monitoring, logging, and security, while local setups require manual configuration and maintenance.
3. **Deployment Process**: Deploying to Azure involves using CI/CD pipelines (like GitHub Actions) for automated deployments, while local deployments are typically manual.
4. **Networking and Accessibility**: Services deployed on Azure are accessible over the internet with proper domain configurations, while local services are typically restricted to the local network.


## Why is it important to use environment variables for configurations in a cloud environment?
Using environment variables for configurations in a cloud environment is important for several reasons:
1. **Security**: Environment variables help keep sensitive information (like API keys, database credentials) out of the codebase, reducing the risk of exposure.
2. **Flexibility**: They allow for easy modification of configurations without changing the code, enabling different settings for development, testing, and production environments.
3. **Portability**: Environment variables facilitate the deployment of applications across different environments (local, staging, production) without code changes.


- Order-service repo : [Order-service repo](https://github.com/boud0217/order-service)
- Product-service repo : [Product-service repo](https://github.com/boud0217/product-service)
- Store-front repo : [Store-front repo](https://github.com/boud0217/store-front)