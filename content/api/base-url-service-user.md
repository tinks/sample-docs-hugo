---
title: "Base URL & service user"
linkTitle: "Base URL & service user"
description: "Basic information for accessing the REST APIs"
date: 2023-08-19
draft: false
weight: 10
---

To get started with the integration, you need the following information:

* **Base URL**: the URL where all API endpoints are located for your platform instance
* **Service user**: the account set up for your platform instance to fetch the authentication token for the API endpoints

## Base URL

As a customer, you have a staging and production environment:

* **Staging base URL**: `https://api.staging.<platform_id>.platform.io`
* **Production base URL**: `https://api.<platform_id>.platform.io`

Your `platform_id` is provided to you during your onboarding.

## Service user

{{% alert %}}The service users for production and staging environments are different.{{% /alert %}}

The service user consists of a user name and password, which is provided to you by your account manager.