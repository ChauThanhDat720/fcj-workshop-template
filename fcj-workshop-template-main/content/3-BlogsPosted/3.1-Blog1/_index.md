---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Scaling telco automation to millions of devices with Managed Red Hat Ansible Automation Platform (AAP) on AWS and Red Hat OpenShift Service on AWS (ROSA)

Hello AWS Study Group VN community.

If you are working in the telecommunications industry or operating systems with a massive number of endpoints—up to millions of nodes like home routers, modems, or broadband gateways—updating configurations or performing simultaneous firmware upgrades without bottlenecking the system is always an extremely daunting challenge.

Today, I would like to share a brilliant architecture translated and detailed from the AWS Architecture Blog. It solves this ultra-large-scale problem by combining the duo of [**Managed Red Hat Ansible Automation Platform (AAP) on AWS**](https://aws.amazon.com/blogs/ibm-redhat/scaling-telco-automation-to-millions-of-devices-with-managed-red-hat-ansible-automation-platform-aap-on-aws-and-red-hat-openshift-service-on-aws-rosa/) and [**Red Hat OpenShift Service on AWS (ROSA)**](https://aws.amazon.com/blogs/ibm-redhat/scaling-telco-automation-to-millions-of-devices-with-managed-red-hat-ansible-automation-platform-aap-on-aws-and-red-hat-openshift-service-on-aws-rosa/).

**The Key Point: Completely Decoupling the Control Plane and Execution Plane**

Traditional management systems often bundle the control unit (UI, APIs) and the execution unit (running commands) into the same server infrastructure. When you send commands to hundreds of thousands of devices simultaneously, the sudden spike in processes exhausts all resources, often causing the management interface for engineers to hang.

With this modern architecture:

* **Control Plane:** AAP on AWS serves as the central hub (handling only the UI, APIs, and orchestration). This control cluster dynamically synchronizes the device list (Inventory) from external sources like CMDB systems or Cloud Providers, while also syncing automation scripts (Playbooks) from centralized source code repositories like **GitHub**.
* **Execution Plane:** The heavy lifting of executing Ansible Playbooks is offloaded entirely to container Pods (called Container Groups in Kubernetes) running on the ROSA cluster.

During peak times, the execution plane can comfortably scale out via IPv4/IPv6 protocols to device gateways, while your control plane remains smoothly responsive.

**Top-Tier Infrastructure: Multi-Region & Stateless Design with Amazon S3**

To handle the scale of millions of endpoints nationwide, the system cannot run in just one place. This architecture deploys [**Red Hat OpenShift Service on AWS (ROSA)**](https://aws.amazon.com/blogs/ibm-redhat/scaling-telco-automation-to-millions-of-devices-with-managed-red-hat-ansible-automation-platform-aap-on-aws-and-red-hat-openshift-service-on-aws-rosa/) across **multiple AWS Regions (Multi-Region)** such as *us-east-1, us-west-1, us-west-2*. In each region, the Worker Nodes responsible for execution are further distributed evenly across **3 Independent Availability Zones (AZ-A, AZ-B, and AZ-C)** to ensure High Availability. A severed cable or a failed zone will not take down the system.

Most importantly, to keep the AAP cluster lightweight and stateless, all heavy management data is completely offloaded to [**Amazon Simple Storage Service (S3) Buckets**](https://aws.amazon.com/blogs/ibm-redhat/scaling-telco-automation-to-millions-of-devices-with-managed-red-hat-ansible-automation-platform-aap-on-aws-and-red-hat-openshift-service-on-aws-rosa/). S3 acts as the storage and distribution layer for *Ansible Content Collections* as well as the Container Images of the *Automation Execution Environments*.

**Real-Time Autoscaling and Cost Optimization**

This is the most valuable aspect of the solution. Instead of maintaining a massive fleet of servers to prepare for upgrade days—only to leave them idle on normal days—the combination of ROSA and AWS optimizes costs perfectly using a pay-as-you-go model.

Let's look at a realistic timeline for a scheduled upgrade:

* **09:00 AM (Normal state):** The system runs exactly 3 EC2 instances (Worker Nodes) for lightweight monitoring, keeping costs to an absolute minimum.
* **09:01 AM (Entering peak hour):** The "Firmware Tuesday" upgrade schedule is triggered simultaneously for **1,000 home router devices**.
* **09:02 AM (Process explosion):** To handle a massive amount of parallel connections (based on fork configuration), AAP requests the immediate creation of **200 execution Pods** on Kubernetes.
* **09:05 AM (Silent autoscaling):** Because the initial 3 servers are fully utilized, the new Pods enter a *Pending* state. Instantly, the *ROSA Cluster Autoscaler* feature detects this and calls AWS to spin up new EC2 instances in the background to handle the load. The work is processed smoothly without bottlenecks.
* **09:30 AM (Mission accomplished):** The firmware upgrade campaign is successful, and the 200 execution Pods are automatically terminated.
* **09:45 AM (Automatic scale-in):** The system notices that the newly spun-up EC2 instances are now empty. The ROSA Metrics Server automatically scales down and terminates them, returning the infrastructure to its original 3-server state.

As a result, the business only pays for the additional servers during those few tens of minutes of peak traffic, without needing to feed a system running at full capacity 24/7.

**The Secret Weapon: Pushing Logs to an OLAP System to Train AI / Operations LLMs**

Running millions of devices generates a colossal amount of logs. This architecture does not store logs in the traditional way, which easily causes I/O bottlenecks. All execution data, logs, and metrics from AAP are continuously pushed to a distributed **OLAP (Online Analytical Processing)** database, specialized for real-time analytics and log aggregation like **Grafana / Grafana Loki**.

Besides providing engineers with clear Dashboards for debugging, the most "valuable" point here is that this massive and clean log data source will be used as input material to **train specialized AI/LLM models for operations (Operations LLM Mode)**. In the future, AI itself will learn from these logs to automatically detect anomalies and provide self-healing solutions for telecommunication networks.

**Other Outstanding Advantages Compared to Legacy Methods**

In addition to elastic scalability, this architecture completely solves the library dependency conflict problem between different device generations. Each automation script is neatly packaged into its own isolated Container Image (Execution Environment). Once finished, it cleans up after itself without leaving junk or affecting other processes.

Simultaneously, because both AAP and ROSA are Fully Managed Services coordinated by Red Hat and AWS, the entire burden of patching operating systems, configuring network layers, or maintaining infrastructure is significantly reduced for the operations team. Engineers can simply focus on writing Playbooks to configure devices.

To protect the business's budget, you can fully establish control guardrails (Fences) such as:

1. **Kubernetes Resource Quotas:** A hard limit on the maximum number of CPUs that AAP is allowed to consume in a namespace.
2. **AWS Service Quotas:** A ceiling on the number of EC2 instances (e.g., the m5.xlarge family) allowed to be spun up in a Region, preventing scenarios where a recursive bug in an automation script unexpectedly balloons the bill.

Source: <https://aws.amazon.com/blogs/ibm-redhat/scaling-telco-automation-to-millions-of-devices-with-managed-red-hat-ansible-automation-platform-aap-on-aws-and-red-hat-openshift-service-on-aws-rosa/>

![](/images/blog1/img_01.png)

![](/images/blog1/img_02.png)