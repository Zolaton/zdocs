# Cloud Infrastructure Technologies
## Virtualization
#### Type-1 hypervisor
* native or bare-metal
  * runs directly on top of a physical host machine's hardware, without the need for a host OS
* examples
  * IBM z/VM
  * Microsoft Hyper-V
  * VMware ESXi
  * AWS Nitro
  * Xen
#### Type-2 hypervisor
* runs on top of the host's OS
* typically for end-users, but they may be found in enterprise settings as well
* examples:
  * VirtualBox
  * VMware Player
  * VMware Workstation
  * Parallels Desktop for Mac
#### Mix Type-1 & Type-2  hypervisor
* KVM
* bhyve

## Infrasctructure as a Service (IaaS)
### AWS
#### Amazon Elastic Compute (EC2)
* Amazon Machine Images (AMI) = preconfigured images
* Instance Types = Hardware profile
  * General purpose instances
  * Optimized instances for:
    * Compute (for CPU intensive applications)
    * GPU
    * Memory (RAM)
    * Machine Learning (ML)
    * Storage (SSD)

#### Other AWS services & tools
    * Security Groups for network access rules
    * Amazon Elastic Block Store (EBS) for persistent storage attachment
    * Dedicated hosts to provision instances on a physical machine reserved for our use
    * Elastic IP to remap a Static IP address automatically
    * Virtual Private Cloud (VPC) for network isolation
    * CloudWatch for monitoring resources and applications
    * Auto Scaling to dynamically resize resources

### Azure
#### Azzure Virtual Machines
* Use Azure Hypervisor, a customized version of Microsoft Hyper-V type-1
* Features and Tools
  * VM Types (compute, memory, storage and network resources...)
    * General purpose
    * Optimized VMs for
      * Compute (for CPU intensive applications)
      * GPU
      * Memory (RAM)
      * High Performance Compute (HPC)
      * Storage
* Create VM
  * On the web UI
  * With Scale Sets

#### Other Azure services & tools
* Network security groups to manage network traffic
* SSD or HDD for persistent storage attachment, with optional encryption
* Dedicated hosts to provision VMs on a physical machine reserved for our use
* Accelerated networking for low latency and high throughput
* Virtual network for network isolation
* Monitoring resources and applications
* Resource Manager templates for VM deployment
* Seamless hybrid connections
* Automated backups

### DigitalOcean
#### Droplets
to manage
  * resource profile
  * guest Operating System
  * application server
  * ecurity
  * backup
  * monitoring
  * etc.
#### Resource profiles
* associated with cost plans
  * Shared CPU
    * Standard Droplets
      * burstable vCPU and memory to support web servers, forums, and blogs
  * Dedicated CPU
    * General Purpose
    * CPU-Optimized
    * Memory-Optimized
#### Other Digital Ocean services & tools
* Monitoring
* Cloud Firewalls
* Backups
* Snapshots
* Team Management
* Block Storage
* Spaces for scalable and secure storage
* Load Balancers
* Floating IPs
* APIs
* Networking

### Google Compute Engine
#### Features and Tools
* GCE Machine Types
  * General-purpose
  * Memory-optimized
  * Compute-optimized
  * Shared-core
* Other
  * Storage
  * Networking VPC and Firewalls
  * Snapshots
  * Cloud Security Scanner
  * Health Checks
  * Sole-tenant Nodes
  * Network Endpoint Group

### IBM Cloud components and services

### Oracle Cloud

### OpenStack

## Platform as a Service (PaaS)
* Cloud Foundry
* OpenShift
* The Heroku Platform

## Containers
* Containers
* Project Moby

## Containers: Micro OSes for Containers
* Alpine Linux
* Atomic Host
* Fedora CoreOS
* RancherOS
* Ubuntu Core
* VMware Photon

## Containers: Container Orchestration
### Docker Swarm
### Kubernetes
#### Kubernetes Architecture - Key Components
  * __Cluster__ group of hosts and  other infrastructure resources
  * __Master Node__
    * Schedule pods
    * Manage worker nodes
    * Main components
      * kube-apiserver
      * etcd
      * kube-scheduler
      * kube-controller-manager
    * High Availability possible with multiple Master Nodes
  * __Worker Node__
    * Host to run pods
    * Runs a daemon called __kubelet__ to communicate with the master node
    * Runs __kube-proxy__, a network proxy for communication to the external world
  * __ Namespace__
    * partitions logically the cluster into sub-clusters
    * provides isolation for
      * projects
      * applications
      * users
      * teams
#### Kubernetes Architecture - Key API Ressources
* Pod
* ReplicaSet
* Deployment
* Service
* Label
* Selector
* Volume
#### Kubernetes Hosted Solutions
* Amazon Elastic Kubernetes Service
* Azure Kubernetes Service
* Google Kubernetes Engine
* IBM Cloud Kubernetes Service
* NetApp Project Astra
* Oracle Container Engine for Kubernetes
* Red Hat OpenShift
* VMware Tanzu Kubernetes Grid
* Mirantis Kubernetes Engine

## Unikernels
* Unikernels

## Microservices
* Microservices

## Software-Defined Networking (SDN) and Networking for Containers
* Decouples the network control layer from the traffic forwarding layer
### SDN Architecture
* __Data Plane__
  * also called the Forwarding Plane
  * handles data packets and apply actions to them based on rules which we program into lookup-tables
* __Control Plane__
* Control Plane
  * calculates and programms the actions for the Data Plane.
  * make the forwarding decisions
  * implements services like:
    * Quality of Service (QoS)
    * VLANs
    * ...
* __Management Plane_ where we can
  * configure
  * monitor
  * and manage the network devices

### Activities Performed by a Network Device
* Network device perform following activities
  * __Ingress and egress packets__
    * performed at the lowest layer
    * decides what to do with ingress packets
      * which packets to forward, based on forwarding tables
    * activities are mapped as Data Plane activities
      * All routers, switches, modem, etc. are part of this plane
  * __Collect, process, and manage the network information__
    * collect, process, and manage the network information
    * network device makes the forwarding decisions
    * which the Data Plane follows
    * activities are mapped by the Control Plane activities
      * some of the protocols which run on the Control Plane are routing and adjacent device discovery
  * __Monitor and manage the network__
    * with tools available in the Management Plane, interact with the network device to
    * configure it
    * and monitor it with tools like SNMP (Simple Network Management Protocol)

### SDN Framework
![SND Framework](https://courses.edx.org/assets/courseware/v1/75cf2c883adc3d24bb86f506c1c49474/asset-v1:LinuxFoundationX+LFS151.x+2T2020+type@asset+block/LFS151-SDN-Framework.png)

### Networking for Containers
* Two standards for container networking
  * Container Network Model (CNM)
    * Mostly [developped by Docker](https://github.com/moby/libnetwork/blob/master/docs/design.md)
  * Container Networking Interface (CNI)
    * [Cloud Native Computing Foundation (CNCF) project](https://www.cncf.io/)
* Service Discovery
  * mechanism for processes and services to 
    * find each other automatically 
    * talk to each other
  * Two steps
    * Registration
      * with etc, Consul..
    * Lookup
      * usually supported with DNS

### Software-Defined Storage
* __Ceph__
  * designed for performance, reliability and scalability
  * object, block, and file system storage
  * flexible, highly reliable, and easy to manage
* __GlusterFS__
  * media streaming
  * data analysis
  * data- and bandwidth-intensive tasks
* __FreeNAS__ File, Block, and Object Sharing
* __LINBIT__ Block Storage
* __MinIO__
  * Object Storage
  * S3 Compatible
* Nexenta
* OpenEBS
* OpenSDS
* Soda Dock
* VMware vSAN+
#### [Volume Management in Kubernetes](https://kubernetes.io/docs/concepts/storage/volumes)
* Ephemeral Volume
  * Same lifecycle as Pod
  * Deleted when Pod is deleted
  * Preserved between restarts
* Persistent Volumes
  * Lifecycle independant of Pod
  * Preserved when Pod is deleted
  * Can be shared between Pods
##### [Types of Volumes](https://kubernetes.io/docs/concepts/storage/volumes/#volume-types)



* Container Storage Interface (CSI)
* Cloud Foundry Volume Service

## DevOps and CI/CD
* CI/CD: Jenkins
* CI/CD: Travis CI
* CI/CD: Shippable
* CI/CD: Concourse
* Cloud Native CI/CD

## Tools for Cloud Infrastructure I (Configuration Management)
* Ansible
* Puppet
* Chef
* Salt Open

## Tools for Cloud Infrastructure II (Build & Release)
* Terraform
* CloudFormation
* BOSH

## Tools for Cloud Infrastructure III (Key-Value Pair Store)
* etcd
* Consul
* ZooKeeper

## Tools for Cloud Infrastructure IV (Image Building)
* Building Docker Images
* Packer

##  Tools for Cloud Infrastructure V (Debugging, Logging, and Monitoring for Containerized Applications)
* Sysdig
* cAdvisor
* Elasticsearch
* Fluentd
* Datadog
* Prometheus
* Splunk

## Service Mesh
* Features and Implementation of Service Mesh
* Consul
* Envoy
* Istio
* Kuma
* Linkerd
* Maesh
* Tanzu Service Mesh

## Internet of Things (IoT)
* Internet of Things

## Serverless Computing
* Serverless Computing
* AWS Lambda
* Google Cloud Functions
* Azure Functions
* Serverless and Containers

## Distributed Tracing
* OpenTracing
* Jaeger
