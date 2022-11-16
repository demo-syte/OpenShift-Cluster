# OpenShift-Cluster
OpenShift  multi-node Cluster (OCP) Deployment

**Install & Configure Multi-Node OpenShift (OCP) Cluster Using User Provisioned Infrastructure:** 

An OpenShift Cluster is a group of nodes or machines running together. At the highest level of Kubernetes, there exist two kinds of servers, a Master and a Worker node. These servers can be Virtual Machines (VM) or physical servers (Bare metal). Together, these servers form an OpenShift cluster and are controlled by the services that make up the Control Plane.
In this post, we have covered, installation & configuration steps of setting up of Multi-Node OpenShift (OCP) Cluster Using User Provisioned Infrastructure on AWS.
There are three ways of installing OpenShift cluster:

a) Community Edition  Origin Kubernetes Distribution (OKD):
An OKD stands for Origin Key Distribution, which is the open-source upstream community edition of Red Hat’s OpenShift container platform. OKD is a container management and orchestration platform based on Docker and Kubernetes.

b) **Red Hat OpenShift Service on AWS (ROSA):**
Red Hat OpenShift Service on AWS (ROSA) is a fully managed OpenShift service, jointly managed and supported by both Red Hat and Amazon Web Services (AWS). Having your clusters maintained by this service gives you the freedom to focus on deploying applications.

c) **Enterprise Edition - OpenShift Container Platform (OCP)**

Enterprise Edition  OpenShift Container Platform (OCP)  is a consistent hybrid cloud foundation for building and scaling containerized applications. Benefit from streamlined platform installation and upgrades from one of the enterprise Kubernetes leaders.
OCP is an on-premises platform as a service built around Docker containers orchestrated and managed by Kubernetes on a foundation of Red Hat Enterprise Linux. The family’s other products provide this platform through different environments: OKD serves as the community-driven upstream, OpenShift Online is the platform offered as software as a service, and OpenShift Dedicated is the platform offered as a managed service.
The OpenShift Console has developer and administrator-oriented views. Administrator views allow one to monitor container resources and container health, manage users, work with operators, etc. Developer views are oriented around working with application resources within a namespace. OpenShift also provides a CLI that supports a superset of the actions that the Kubernetes CLI provides.

With the release of Red Hat OpenShift 4, the concept of User Provisioned Infrastructure (UPI) has emerged to encompass the environments where the infrastructure (compute, network and storage resources) that hosts the OpenShift Container Platform is deployed by the user. In this type of installation, you as a user deploy underlying infrastructures like Operating System whereas the installer will install Openshift Cluster and openshift related resources.
This allows for more creative deployments while leaving the management of the infrastructure to the user. This allows us to deploy OpenShift Container Platform 4.1 on a mix of virtual and bare-metal machines.

![image](https://user-images.githubusercontent.com/78690371/158143069-42dfe5c2-a8c4-434d-b240-4dc1194d8ef2.png)

 
**Prerequisites For Cluster Setup**
Deploying Openshift clusters can be hard and painful, so an alternate way of doing this can be using a Cloud Platform for deploying them. You can use any Cloud Platform; here, we are using AWS Cloud. Before getting on with creating a cluster, make sure you have the following setup ready:

I)  AWS Account, launch a ec2 instance
II) Register for entries for the nameserver to configure Amazon Route53. 
III) Launching a Linux Instance Using EC2.
•	AMI: select 64-bit (x86) architecture.
•	Instance type: t2.micro

IV) Connect to EC2 instance  using Putty
Setup Openshift Cluster Using User Provisioned Infrastructure

 
**Install & Configure Multi-Node OpenShift (OCP) Cluster Using User Provisioned Infrastructure: **

An OpenShift Cluster is a group of nodes or machines running together. At the highest level of Kubernetes, there exist two kinds of servers, a Master and a Worker node. These servers can be Virtual Machines (VM) or physical servers (Bare metal). Together, these servers form an OpenShift cluster and are controlled by the services that make up the Control Plane.

steps of setting up of Multi-Node Openshift (OCP) Cluster Using User Provisioned Infrastructure on AWS.

There are three ways of installing OpenShift cluster:

a) Community Edition Origin Kubernetes Distribution (OKD):
An OKD stands for Origin Key Distribution, which is the open-source upstream community edition of Red Hat’s OpenShift container platform. OKD is a container management and orchestration platform based on Docker and Kubernetes.

b) Red Hat OpenShift Service on AWS (ROSA):
Red Hat OpenShift Service on AWS (ROSA) is a fully managed OpenShift service, jointly managed and supported by both Red Hat and Amazon Web Services (AWS). Having your clusters maintained by this service gives you the freedom to focus on deploying applications.

c) Enterprise Edition  OpenShift Container Platform (OCP)

we will be installing OCP.

**What is OCP in OpenShift?**

Enterprise Edition OpenShift Container Platform (OCP)  is a consistent hybrid cloud foundation for building and scaling containerized applications. Benefit from streamlined platform installation and upgrades from one of the enterprise Kubernetes leaders.
OCP is an on-premises platform as a service built around Docker containers orchestrated and managed by Kubernetes on a foundation of Red Hat Enterprise Linux. The family’s other products provide this platform through different environments: OKD serves as the community-driven upstream, OpenShift Online is the platform offered as software as a service, and OpenShift Dedicated is the platform offered as a managed service.
The OpenShift Console has developer and administrator-oriented views. Administrator views allow one to monitor container resources and container health, manage users, work with operators, etc. Developer views are oriented around working with application resources within a namespace. OpenShift also provides a CLI that supports a superset of the actions that the Kubernetes CLI provides.

**What is User Provisioned Infrastructure (UPI)?**

With the release of Red Hat OpenShift 4, the concept of User Provisioned Infrastructure (UPI) has emerged to encompass the environments where the infrastructure (compute, network and storage resources) that hosts the OpenShift Container Platform is deployed by the user. In this type of installation, you as a user deploy underlying infrastructures like Operating System whereas the installer will install Openshift Cluster and openshift related resources.
This allows for more creative deployments while leaving the management of the infrastructure to the user. This allows us to deploy OpenShift Container Platform 4.1 on a mix of virtual and bare-metal machines.
 
**Prerequisites For Cluster Setup**
Deploying Openshift clusters can be hard and painful, so an alternate way of doing this can be using a Cloud Platform for deploying them. You can use any Cloud Platform; here, we are using AWS Cloud. Before getting on with creating a cluster, make sure you have the following setup ready:

I)  We will follow the guide here to Install & Configure Multi-Node Openshift Cluster using Run It Yourself User Provisioned Infrastructure On AWS .

II) Create an AWS Free Account, as we will use AWS Cloud for setting up an Openshift Cluster. 

III) Subscribe to Redhat Developer and create and update Redhat account, access the Active subscription. We need to have you will reach the subscription page, where you should see one Active Subscription.
 
IV) Registering a domain name for free from any hosting service provider. I have used Amazon Route53 for getting public DNS Name

V) Register for entries for the nameserver to configure Amazon Route53. 

VI) Launching a Linux Instance Using EC2.

The EC2  is a computing service that provides scalable computing capacity and eliminates the equipment investment up-front, so the applications can be developed and deployed faster. Virtual machines on AWS EC2 are called instances. In this guide, we are going to use t2. Medium EC2 Instance, which is not part of the free trial period, pleases (shutdown) to delete the instance once you are done with the practice. This Setup is done on an AWS EC2 instance with the following configurations.
Read more about How to create an AWS EC2 instance.



•	AMI: select 64-bit (x86) architecture.
•	Instance type: t2.micro

VII) Connect to EC2 instance  using Putty
![image](https://user-images.githubusercontent.com/78690371/158145449-fa6eb973-1981-4fde-b2e6-6155e4a43967.png)

 
Install & Configure AWS CLI On Linux (EC2)

One of the AWS tools is known as AWS CLI (Command-line interface). It is used to manage AWS services through commands. AWS Command Line Interface (CLI) is a unified configuration to administer AWS public cloud services. With only one tool, we can download, configure and monitor multiple AWS services using commands and automate them via scripts.
 
Setup Openshift Cluster Using User Provisioned Infrastructure

1. **Generating Key Pair for Cluster Node SSH Access:**
2. 
a) Create key pair:
$ sudo -i
$ ssh-keygen -t ed25519 -N '' -f ~/.ssh/id_rsa
![image](https://user-images.githubusercontent.com/78690371/158148349-4c2352f3-6ae9-4619-b15b-28e92a9eeb74.png)

 
2. **Obtaining the Installation Program:**

Access the Infrastructure Provider page on the Red Hat OpenShift Cluster Manager site. If you have a Red Hat account, log in with your credentials. If you do not, create an account. To create an account follow the Pre-requisite section Subscription to Redhat.
Click on this link to open Infrastructure Provider: https://console.redhat.com/openshift/install


a) Login into your cluster and scroll down till Run it yourself and click on AWS
 ![image](https://user-images.githubusercontent.com/78690371/158148795-758c1ee7-c5ce-4e17-b333-46a4d00facc4.png)

https://mirror.openshift.com/pub/openshift-v4/x86_64/clients/ocp/stable/openshift-install-linux.tar.gz


 

**Install OpenShift CLI on Linux:**

a) Download Now OpenShift v4.8 Linux Client entry and save the file. https://mirror.openshift.com/pub/openshift-v4/x86_64/clients/ocp/stable/openshift-client-linux.tar.gz
b) Verify the client binary installed

![image](https://user-images.githubusercontent.com/78690371/158149787-390934d1-334f-4974-b129-029f03524f87.png)

 

**OPEN SHIFT CLUSTER INSTALLATION**

a)	**Customize your Cluster nodes (optional)**

**$ ./openshift-install create install-config --dir=/root/openshift**

This will generate the ‘install-config’ yaml file then you edit it with desired Number of replicas needed for Worker & Master node.

Save & exit.

Note: Do not change the ‘install-config’ yaml name otherwise cluster will not consume it.


b) **Start Openshift Cluster Installation**

$ **./openshift-install create cluster --dir=/root/openshift --log-level=info**

(This Cluster creation process will take 30-45 minutes)

**LOGGING INTO CLUSTER**

1. Logging in to the cluster using the Command Line (CLI):

a) Export the kubeadmin credentials from the root user

$ export KUBECONFIG=<installation_directory>/auth/kubeconfig
$ echo 'export KUBECONFIG=/root/openshift/auth/kubeconfig' >> $HOME/.bashrc

![image](https://user-images.githubusercontent.com/78690371/158149840-0c6b4bc6-22fd-4ff3-9f3d-619d4a607f16.png)


 

a) **List the OpenShift Container Platform web console route:**
$ oc get routes -n openshift-console | grep console
![image](https://user-images.githubusercontent.com/78690371/158150007-febe19ee-6729-4404-b9a8-d958f0d1bdb2.png)


 

**Check Cluster Logs**
You can review a summary of an installation in the OpenShift Container Platform installation log. If an installation succeeds, the information required to access the cluster is included in the log.
a) Review the .openshift_install.log log file in the installation directory on your installation host:
$ cat <install_dir>/.openshift_install.log
$ cat /root/openshift/.openshift_install.log


** To delete the cluster please use the below commands:**
$ sudo su –
$ cd /root/openshift
$ ./openshift-install destroy cluster --dir=/root/openshift --log-level=info



