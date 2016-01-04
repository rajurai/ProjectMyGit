# Overview

Alliance is a Software Defined Gateway for inter-cloud integration, which stitches together multiple distinct clouds to support many  hybrid cloud delivery profiles. In other worlds, Alliance gateway is a de-centralized application (DApp) component which enables peer-to-peer (P2P) inter-cloud integration to support many hybrid cloud profiles, e.g. enterprise private cloud to provider cloud bursting, virtual private cloud (VPC) and Intercloud provider collaboration. 

**Table of Contents**

- [Overview](#overview)
    - [Hybrid cloud models](#hybrid-cloud-models)
    - [Gateway Features](#gateway-features)
    - [Gateway Architecture](#gateway-architecture)
    - [Gateway Components](#gateway-components)
        - [API Server](#api-server)
        - [Agent Server](#agent-server)
    - [Getting Started](#getting-started)
        - [Software Requirements](#software-requirements)
        - [Deployment Procedure](#deployment-procedure)
            - [Deploying using Debian Package](#deploying-using-debian-package)
    - [Documentation](#documentation)
    - [Roadmap](#roadmap)
        - [Core Components and Features](#core-components-and-features)
        - [Security](#security)
        - [Operations](#operations)
        - [Platform Support](#platform-support)
    - [Development](#development)
    - [License](#license)

## Hybrid cloud models

Alliance framework support following hybrid cloud delivery models.

![Hybrid Cloud Models](docs/_static/HybridCloudModels.png)

### Model 1

In this model, a private cloud or VPC consumes resources from shared pool from provider cloud. There is no resource isolation and capacity guarantee. 

### Model 2

In this model, a private cloud or VPC consumes resources from dedicated resource pool (physical resources) from provider cloud. It provide resource isolation and capacity guarantee. In some cases a provider offers "Cloud As A Service" to back on-premise private cloud or VPC.   

## Gateway Features

The main design goals of Alliance is to integrate infrastructure (IaaS) and platform (PaaS) cloud capabilities to provide a uniform inter-operable platform. Alliance currently supports OpenStack cloud platform but it follows platform agnostic plugable modular design, that means underpinning cloud platform can be different. Following are the specific features 

* Single pane of glass for Intercloud.
    * Single endpoint and uniform set of APIs to manage resources across many distinct clouds.   
    * Resource management lookup/provisioning/de-provisioning (IaaS) across clouds.
    * Orchestration. (Integration with HOT)
    * Intercloud OSS and BSS support.
* Modular and Plugable framework.
    * Platform agnostic integration.
* PKI Trust based integration.
    * Cryptographic (ACS 256) secured communication.
    * Full mesh federation.
    * Anonymization
* Namespaces and Project Federation
    * Keep project name same everywhere.  
* Native Federation
    * Seamless token operations (SSO).
    * Intercloud Authentication
    * Intercloud meter synchronization and aggregation.
* Distributed Quota enforcement.

## Gateway Architecture 

The architecture is based on decentralized peer-to-peer gateway interactions. As per the diagram below all gateways are peer managed by different organization and can be a client/service based on transaction flow. Gateway exposes high performance Thrift RPC API and communication between gateways will happens on RPC. RPC APIs are required to support single endpoint, inter-gateway trust and performance.

Communication between gateway and underpinning cloud happens on platform native protocol; as mentioned gateway follows plugable design paradigm to communicate with underpinning cloud. 

The gateway also exposes REST APIs which is needed to support uniform REST API requirements, which makes it platform agnostic. 

![Architecture](docs/_static/Architecture.png)

## Gateway Components

![Alliance Component Diagram](docs/_static/AllianceBlockDiagram.png)

The Gateway majorly have three components as below:

### API Server

API server exposes uniform REST APIs and abstracts the complexity of many platform APIs. It introduces a new construct called cloud Namespace which is used for addressing of requests.

#### Admin API

Admin API are used to setup partners, metadata and PKI trust, these APIs are mostly used by cloud Admins. 

#### Management API

Management APIs are used for inter-cloud resource management which includes lookup, provisioning and de-provisioning of resources.  

[API Docs](https://github.com/CiscoCloud/alliance/tree/devel/apis)

### RPC Server

RPC server exposes Thrift APIs for inter-gateway communication and provide trust based inter-cloud integration. Trust validation is happens with PKI and symmetric cryptography.   

### Asynchronous worker

TBD - Not implemented

## Roadmap

Below are the list of features partially or fully implemented in P2P gateway, unchecked items are roadmap. 

### Platform plug-in

- [x] OpenStack Kilo
- [ ] OpenStack Liberty
- [ ] Cloud Foundry

### User Interface
- [x] Single pane of glass
- [x] Uniform OSS and BSS
- [x] Single endpoint and uniform API.

### Administrator 

- [x] Administration API to manage partners and metadata.
- [x] On-demand API driven partner (Ent. private, VPC, Intercloud partner …. ) pairing. 
- [x] Namespace aware APIs and resource grouping.
- [x] Project Federation to keep same project name.

### Security
- [x] Secured PKI Trust
- [x] Peer authentication through trust validation.
- [x] Ephemeral cryptographic session keys.
- [x] Cryptographic (ACS) secured RPC. 
- [x] Anonymization (At projects)
- [ ] Cloud Native federation.

### Infrastructure (IaaS)

#### Horizon

- [x] Andrew

#### Compute

- [x] Raju
 
#### Network

- [x] Aravind

#### Object Storage

- [ ] Not Implemented 

#### Image Management

- [x] Raju
 
#### Volume

- [x] Andrew
 
#### Orchestration

- [ ] Heat

### Plateform (PaaS)

- [x] Not Implemented

## Getting Started

###### (Aravind) Write steps for working with git.Git's commands which can be used and its description.

Note:

* Note1
* Note2
* Note3



### Software Requirements
-----------------------------------------------------------------------------------------------------------------------------

###### (Aravind) Write about the software requirements to run the project in this section.


### Deployment Procedure
-----------------------------------------------------------------------------------------------------------------------------
(Aravind and Andrew)
###### Please refer to the [Getting Started Guide](#getting-started),which covers deployments.

#### Deploying Using Debian Package
`````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````
     Write about the deployment procedure using the debian package
`````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````

## Documentation

###### All documents are located [here](https://github.com/CiscoCloud/alliance/tree/devel/apis)

## Development
###### Write about the details of how anyone can contribute to the project.

## Getting Support
###### Write about the support details of the project.In case of any issue how anyone can get the support.

## License
###### Write about the license details of the project.
