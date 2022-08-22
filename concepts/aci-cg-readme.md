# Container groups in Azure Container Instances
A container group is a collection of containers that get scheduled on the same host machine. The containers in a container group share a lifecycle, resources, local network, and storage volumes. It's similar in concept to a pod in Kubernetes. [Container groups | Microsoft docs](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-container-groups)

![alt txt](/images/container-groups-example.png)

[Scenarios for using container groups](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-container-groups#common-scenarios)