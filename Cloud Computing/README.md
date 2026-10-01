# Cloud Computing

## Overview

Cloud computing provides computing resources over the internet instead of requiring applications to run entirely on a single physical computer.

It allows applications to become more accessible, scalable, reliable, and easier to manage as the number of users changes.

## How Servers Evolved to the Cloud

Cloud computing evolved through several stages as organizations looked for better resource utilization, lower costs, and easier scalability.

The progression went from physical servers to increasingly flexible virtualized environments and eventually to modern cloud platforms.

The cloud allows organizations to provision computing resources when needed instead of purchasing and maintaining all physical hardware themselves.

## Cloud Benefits and Characteristics

The main characteristics of cloud computing are:

* Scalability: Resources can be increased or decreased as application demand changes.
* On-demand self-service: Resources such as servers and storage can be created or removed when needed.
* Pay only for what you use: Costs are based on resource usage rather than large upfront hardware purchases.
* Security: Cloud providers provide infrastructure-level security controls and services.
* High availability: Applications can continue operating even when part of the infrastructure fails.
* Global access: Applications and resources can be accessed from different locations around the world.

## Cloud Deployment Models

### Public Cloud

A public cloud provides computing resources over the internet using infrastructure shared by multiple customers.

It is commonly used because resources can be provisioned quickly and scaled without managing physical infrastructure.

### Private Cloud

A private cloud is dedicated to a single organization.

It provides greater control and customization and can be useful when organizations have specific security, compliance, or infrastructure requirements.

### Hybrid Cloud

A hybrid cloud combines public and private cloud environments.

Organizations can keep certain resources in a private environment while using public cloud resources when additional scalability is required.

## Cloud Service Models

### Infrastructure as a Service (IaaS)

IaaS provides basic computing infrastructure such as:

* Virtual machines
* Storage
* Networking

The cloud provider manages the physical infrastructure while the customer manages the operating system, applications, and configuration.

### Platform as a Service (PaaS)

PaaS provides a managed environment for developing and running applications.

The provider manages the underlying infrastructure and operating system, allowing developers to focus primarily on the application itself.

### Software as a Service (SaaS)

SaaS provides complete software applications over the internet.

The provider manages the infrastructure, operating system, application, and maintenance.

Examples include services such as Gmail and Zoom.

## Major Cloud Providers

Some major cloud providers include:

* Amazon Web Services (AWS)
* Microsoft Azure
* Google Cloud Platform (GCP)
* Alibaba Cloud
* IBM Cloud
* Oracle Cloud

AWS is one of the largest cloud providers and offers a wide range of infrastructure and cloud services.

## EC2

Amazon EC2 (Elastic Compute Cloud) provides virtual computers in the cloud.

An EC2 instance has resources such as CPU and memory and can run applications similarly to a physical computer.

### Instance Types

Instance types determine the resources available to a virtual machine.

In general:

* Larger instances provide more computing resources.
* Smaller instances provide fewer resources and generally cost less.

## Cloud Console Lab

In the practical part of the room, I created and managed virtual machines in a simulated cloud console.

The environment included:

* application-interface
* study-machine-1
* study-machine-2

The application interface used a t3.micro instance, while the study machines used m5.large instances.

The study machines could be stopped when they were not being used. Stopped instances did not contribute to the running cost in the simulated environment.

This demonstrated how cloud environments allow resources to be started and stopped depending on current requirements.

## Cost Management

One important advantage of cloud computing is the ability to manage resources according to demand.

For example, keeping unused virtual machines running increases resource consumption and cost. Stopping machines that are not currently required can reduce the running cost.

This is an example of the cloud principle:

> Pay only for what you use.

## Key Terminology

| Term          | Meaning                                                                  |
| ------------- | ------------------------------------------------------------------------ |
| Public Cloud  | Cloud services shared by multiple customers over the internet            |
| Private Cloud | Cloud infrastructure dedicated to one organization                       |
| Hybrid Cloud  | Combination of public and private cloud environments                     |
| IaaS          | Renting infrastructure such as virtual machines, storage, and networking |
| PaaS          | Managed environment for building and running applications                |
| SaaS          | Complete software delivered over the internet                            |
| EC2           | AWS virtual computing service                                            |

## Key Takeaways

The main concepts learned in this room were:

* Cloud computing provides computing resources over the internet.
* Cloud environments can scale according to demand.
* Public, private, and hybrid clouds provide different deployment approaches.
* IaaS, PaaS, and SaaS provide different levels of responsibility.
* EC2 provides virtual machines in AWS.
* Cloud resources can be created and managed on demand.
* Stopping unused resources can reduce costs.
* Cloud computing provides scalability, flexibility, availability, and global access.

## Next Topic

The next module covers Operating Systems.

Understanding operating systems is important for cybersecurity because operating systems manage hardware, processes, memory, users, permissions, and other security-related components.
