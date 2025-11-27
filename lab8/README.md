# Lab 8
Video link : [Demo Video](https://youtu.be/lEXd1jMdfO8)
Task 1 YAML file : [aps-all-in-one-Task1.yaml](https://github.com/boud0217/CST8915/blob/main/lab8/aps-all-in-one-Task1.yaml)
Task 2 YAML file : [aps-all-in-one-Task-2.yaml](https://github.com/boud0217/CST8915/blob/main/lab8/aps-all-in-one-Task-2.yaml)

Explanation of solution in task 2 :  
In the task 1 "MongoDB" and "RabbitMQ" has their data ephemeral. If they get restarted or they fail, all the data will be lost. We need to make them persistent.  
In task 2 I have added "PersistentVolume" and "PersistentVolumeClaim" for both "MongoDB" and "RabbitMQ" to make their data persistent. Now if they get restarted or they fail, all the data will be saved in the persistent volume.  
For MongoDB, I added 2 more replicas. One is primary and the others are secondaries. The primary handles writes and the secondaries replicate data. I also added persistent storage by setting a PersistentVolumeClaim (PVC) via "volumeClaimTemplates". This is a request for storage by a pod in the local storage. The PVC makes sure that the data are persistent. For high availability, I setted the "ClusterIP" to "none" so it provides DNS names like "mongodb-0", "mongodb-1".  
For RabbitMQ, I have mounted a PVC on "/var/lib/rabbitmq", the directory that stores queues and messages.