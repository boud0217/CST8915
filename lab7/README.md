# Lab 7
Video link : [Demo Video](https://youtu.be/olPyIvY_674)

## Analysis
### RabbitMQ 
RabbitMQ is a stateless application in this configuration because it will not remember anything after restarts or deletes. If you restart the pod, all of that will disappears.
Without persistence storage, every RabbitMQ pod restart wipes all the data (users, permissions, queues, exchanges, bindings, and messages). It reinitializes with fresh defaults and services using these credentials may suddenly fail authenticating.
To solve this problem, we can add a persistent storage by adding the following code to our .yaml file : 
```yaml
      volumeClaimTemplates:
        - metadata:
            name: rabbitmq-data
            spec:
            accessModes: ["ReadWriteOnce"]
            resources:
                requests:
                storage: 1Gi
```
We can also use Kubernetes Secrets to store the credentials.
There is another solution which is switching from "Deployment" to "StatefulSet". StatefulSets give each pod a stable identity and are designed for stateful apps like RabbitMQ.