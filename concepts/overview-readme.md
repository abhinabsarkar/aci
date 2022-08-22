# Azure Container Instances overview
Azure Container Instances is a solution to operate isolated containers, including simple applications, task automation, and build jobs. [Azure Container Instances | Microsoft docs](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-overview)

* Container access - Azure Container Instances enables exposing your [container groups](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-container-groups) directly to the internet with an IP address and a fully qualified domain name (FQDN). When you create a container instance, you can specify a custom DNS name label so your application is reachable at `customlabel.azureregion.azurecontainer.io`.
* Hypervisor-level security - Azure Container Instances guarantees your application is as isolated in a container as it would be in a VM.
* Custom sizes - Containers are typically optimized to run just a single application. Azure Container Instances provides optimum utilization by allowing exact specifications of CPU cores and memory. You pay based on what you need and get `billed by the second`, so you can fine-tune your spending based on actual need.
* Persistent storage - Azure Container Instances are stateless. If the container is restarted, crashes, or stops, all of its state is lost. To persist state beyond the lifetime of the container, Azure Container Instances can mount an Azure file share created with Azure Files. [Mount an Azure file share in Azure Container Instances | Microsoft docs](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-volume-azure-files)
* Linux and Windows containers -  schedule both Windows and Linux containers with the same API . Some features are currently `restricted to Linux containers`. [Features only on Linux containers | Microsoft docs](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-overview#linux-and-windows-containers)
* [Container Groups](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-container-groups) - It shares host machine, local network, storage, and lifecycle. This enables you to combine your main application container with other supporting role containers, such as logging sidecars.
* VNet deployment - enables deployment of container instances into an Azure virtual network

## Not supported
* liveness probes and readiness probes aren't supported in container groups, which make it harder to identify workload downtime

# ACI under the hood
[Azure Container Instances (ACI) under the hood | Azure Friday](https://www.youtube.com/watch?v=giQLmxMKAKE)

![alt txt](/images/aci-control-plane.jpg)

![alt txt](/images/aci-node-plane.jpg)

* [Containerd](https://containerd.io/) is an [OCI (Open Container Initiative)](https://opencontainers.org/) compliant core `container runtime` that provides the minimum set of required functionality to execute containers and manage images on a node.
* [openGCS](https://github.com/microsoft/opengcs) - Linux open source project to further the development of a production quality implementation of Linux Hyper-V containers on Windows (LCOW). It's designed to run inside a custom Linux OS for supporting Linux container payload.
* [runc](https://github.com/opencontainers/runc) is a CLI tool for spawning and running containers on Linux according to the OCI specification.
