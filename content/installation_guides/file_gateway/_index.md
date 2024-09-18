---
title: "File Gateway Installation Guide"
linkTitle: "File Gateway"
description: ""
date: 2024-08-19
draft: false
weight: 50
---

An Amazon S3 File Gateway enables you to share files between your on-premises components and the company's components within your solution deployed in AWS. For example, asset metadata is collected and managed in your on-premises data management system. The asset metadata must be sent to the company's asset processing component for further processing and use by other company components. In this example, the S3 File Gateway provides you with a local network drive location to drop the asset metadata and eliminates a complex integration between your on-premises components and the cloud components in your solution.

The solution consists of:

* an S3 File Gateway: software provided by AWS, which you must install and configure in a virtual machine within your network
* an AWS gateway configuration: a configuration within AWS maintained by the company
* an AWS file share configuration: an SMB/NFS configuration within AWS maintained by the company
* one or more AWS S3 buckets: storage in AWS, configured and maintained by the company

![](../../images/fdps_installation_architecture_overview.png)

