---
title: "Installation process"
linkTitle: "Installation process"
description: ""
date: 2024-09-18
draft: false
weight: 20
---

As a customer, you do not have access to the AWS console where the company deploys the components needed for your solution. As a result, certain steps in setting up the S3 File Gateway are executed by a company representative. The following diagram illustrates the stages in the process and who executes them:

```mermaid
flowchart
    subgraph Customer
        direction TB
        st0((START)) --> st1
        st1(Request link to S3 File Gateway virtual machine image)
        st3(Install and configure S3 File Gateway virtual machine image) --> st4(Test S3 File Gateway connectivity)
        st4 --> st5{Success?}
        st5 -- no --> st6a(Configure firewall and router to access service endpoints)
        st6a --> st4
        st5 -- yes --> st6b{Provide the company with access to VM?}
        st6b -- no --> st7b(Set up second machine with AWS CLI and cURL)
        st7b --> st8(Request AWS credentials)
        st11(Set up credentials on secondary machine) --> st12(Run commands on secondary machine to configure and activate S3 File Gateway)
        st12 --> st13(Notify the company of successful setup)
    end
    subgraph The company
        direction TB
        st2(Provide URL to customer)
        st7a(Configure and activate S3 File Gateway) --> st15((END))
        st9(Set up temporary AWS user) --> st10(Send credentials and information to customer)
        st14(Remove temporary AWS user) --> st15
    end
    st1 --> st2
    st2 --> st3
    st6b -- yes --> st7a
    st8 --> st9
    st10 --> st11
    st13 --> st14
```
