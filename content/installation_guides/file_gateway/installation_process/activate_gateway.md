---
title: "Configure and activate gateway"
linkTitle: "Configure and activate gateway"
description: ""
date: 2024-09-18
draft: true
weight: 40
---

In this stage, the S3 File Gateway is configured and activated. How this happens depends on whether or not the company is granted access to the virtual machine where you installed the S3 File Gateway.

## The company can have access to VM

If you allow the company, even temporary, access to the virtual machine where you installed the S3 File Gateway, then the company can configure and activate the S3 File Gateway.

Inform your designated company representative that you have successfully installed and tested the S3 File Gateway virtual machine. Provide the following information:

*   How to connect to the virtual machine \(IP address\).
*   How to access your network, in case the virtual machine is within a restricted network.
*   The credentials to log into the virtual machine.

If the S3 File Gateway virtual machine is in a restricted network, then provide and request the information needed to allow the company access to the restricted network. For example, you may have to open your network to specific IP addresses from the company, which the company needs to provide to you.

## The company cannot have access to VM

If you cannot provide access to the virtual machine to the company, then you must execute the following steps to configure and activate the S3 File Gateway in AWS:

1. Request AWS credentials and S3 File Gateway information from your designated company representative. You receive the following information:
   * `aws_access_key_id`: the access key ID of the AWS user
   * `aws_secret_access_key`: the access key of the AWS user
   * `region`: the region where the File Gateway will be activated \(the region is the same as the region you tested against in the previous stage\)
   * `gateway-name`: the name of the File Gateway in AWS
   * `activation-key`: the activation key of the File Gateway in AWS
1. Create a new virtual machine within the same network as the File Gateway virtual machine with the following tools installed:
   * AWS CLI: see [Install or update to the latest version of the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) for installation instructions.
   * cURL: see [curl/Download](https://curl.se/) to retrieve the executable
1. Log into your new virtual machine
1. Set up the AWS CLI credentials file with the following information:

   ```
   [gwinstall]
   aws_access_key_id = <aws_access_key_id provided by INVIDI>
   aws_secret_access_key = <aws_secret_access_key provided by INVIDI>
   ```
1. Set up the AWS CLI configuration file with the following information:

   ``` {#codeblock_rhl_hmk_n1c}
   [profile gwinstall]
   region = <region provided by INVIDI>
   ```
1. Run the following AWS CLI command to activate the gateway:

   ```
   aws activate-gateway \
   --activation-key <activation-key provided by INVIDI>\
   --gateway-name <gateway-name provided by INVIDI>\
   --gateway-timezone <timezone of the File Gateway VM>\
   --gateway-region <region provided by INVIDI>\
   --profile gwinstall
   ```

   This command outputs the AWS File Gateway ARN, which is needed in the following command:

   ```
   {
       "GatewayARN": "arn:aws:storagegateway:<region>:<account#>:gateway/sgw-<gateway-id>"
   }
   ```
1. Run the following AWS CLI command to list the disks in your File Gateway VM:

   ```
   aws --profile gwinstall storagegateway list-local-disks --gateway-arn <GatewayARN>
   ```

   The command outputs the list of disks in your File Gateway VM:

   ```
   {
       "GatewayARN": "<GatewayARN>",
       "Disks": [
           {
               "DiskId": "92e81768-7ac1-4523-9c59-1043a27121cb",
               "DiskPath": "/dev/sdb",
               "DiskNode": "SCSI (0:1)",
               "DiskStatus": "present",
               "DiskSizeInBytes": 161061273600,
               "DiskAllocationType": "AVAILABLE",
               "DiskAttributeList": []
           }
       ]
   }
   ```
1. Run the following AWS CLI command, using the `DiskId` from the output from the previous command, to identify the cache disk of the File Gateway to the setup in AWS:

   ```
   aws --profile gwinstall storagegateway
                 add-cache --gateway-arn <GatewayARN> --disk-ids
           "<DiskId>"
   ```
1. Notify your designated company representative that you have finalized AWS File Gateway configuration and activation, and request to verify the File Gateway in AWS. When you receive confirmation, you can continue with the next steps to request the AWS File shares necessary for your solution.
