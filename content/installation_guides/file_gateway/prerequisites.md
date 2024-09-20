---
title: "Prerequisites"
linkTitle: "Prerequisites"
description: ""
date: 2024-09-18
draft: false
weight: 10
---

Before you install the S3 File Gateway, make sure that the following prerequisites are met:

* Microsoft Active Directory service account with the correct permissions. For more information, see [Active Directory service account permission requirements - AWS Storage Gateway](https://docs.aws.amazon.com/filegateway/latest/files3/ad-serviceaccount-permissions.html)
* One of the following hypervisors to deploy the virtual machine appliance:
  * VMware ESXi Hypervisor
  * Microsoft Hyper-V Hypervisor
  * Linux Kernel-based Virtual Machine

    For supported versions, see [Supported hypervisors and host requirements](https://docs.aws.amazon.com/filegateway/latest/files3/Requirements.html#requirements-host)
* Sufficient bandwidth between your network and AWS \(at least 100 Mbps\)
* Hardware:
  * Four virtual processors assigned to the VM
  * 16 GB of reserved RAM for File Gateways
  * 80 GB of disk space for installation of VM image and system data
  * 150 GB for an additional cache disk for your VM
  
    For more information, see [Hardware and storage requirements](https://docs.aws.amazon.com/filegateway/latest/files3/Requirements.html#requirements-hardware-storage)


For more information on prerequisites, see [File Gateway setup requirements - AWS Storage Gateway](https://docs.aws.amazon.com/filegateway/latest/files3/Requirements.html).

