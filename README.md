# UPenn CyberSecurity Capstone

![](cloud_network_Idrees.png)


###   Automated ELK Stack Deployment
---
The files in this repository were used to configure the network depicted above.

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions used to install only certain pieces of it, such as Filebeat or Metricbeat.

- **[install-filebeat.yml](Scripts/install-filebeat.yml)**
- **[install-metricbeat.yml](Scripts/install-metricbeat.yml)**
- **[install-elk.yml](Scripts/install-elk.yml)**

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology
---
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA (D*mn Vulnerable Web Application)

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.

> **Load balancing** is the process of distributing incoming reequests/tasks over a set of resources in order to prevent disproportionate skew of requests load towards one specific server. For example, this can be particularly useful in maintaining availability of services to customers in the setting of a DoS attack on one of the server, rendering it unavailable. If the same services are available on an alternate server, the load balancer can distribute the web traffic to the alternate server when the primary server is 'overloaded' - this way the services (such as sales) continue to remain operational even in the mist of the attack. In addition it can also be configured to limit access to particular servers to prevent penetration by hackers. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files, logs and system metrics.

> **Filebeat** collects data about the file system. It is helpful in detecting changes to certain important files stampd by time like for example if a hacker attemps to change etc/passwd and this information is then sent to Elasticsearch on the ELK Server

> **Metricbeat** Collects metrics to help with the assessment regarding the operational state of computer machines on the network (VMs in this case) and then sends it to Elasticsearch on ELK Server. For example it can be helpful in determining CPU usage, memory disk I/O, Network I/O and Uptime information. 

The configuration details of each machine may be found below.


| Name     | Function     | IP Address | Operating System |
|----------|--------------|------------|------------------|
| Jump-Box | Gateway      | 10.0.0.4   |    Linux         |
| Web-1    | Server       | 10.0.0.5   |    Linux         |
| Web-2    | Server       | 10.0.0.6   |    Linux         |                  
| Web-3    | Server       | 10.0.0.7   |    Linux         |                  
| ELK      | Monitoring   | 10.1.0.4   |    Linux         |
