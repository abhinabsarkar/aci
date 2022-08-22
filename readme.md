# Azure Container Instance
Azure Container Instances is a solution to operate isolated containers, including simple applications, task automation, and build jobs. For scenarios where you need full container orchestration, including service discovery across multiple containers, automatic scaling, and coordinated application upgrades, we recommend Azure Kubernetes Service (AKS).
* [Overview & ACI under the hood](/concepts/overview-readme.md)
    * [Azure Container Instances (ACI) under the hood | Azure Friday](https://www.youtube.com/watch?v=giQLmxMKAKE)
* [Container groups](/concepts/aci-cg-readme.md)
* [Reference Architecture / Automate infrastructure reconfiguration | Microsoft docs](https://docs.microsoft.com/en-us/azure/architecture/example-scenario/serverless/automation-application-gateway)
    * [Deploy the Reference Architecture on Azure](https://github.com/mspnp/aci-auto-healing) - The deployment failed during VNet creation with the error message `Another operation on this or dependent resource is in progress`. Didn't debug it.