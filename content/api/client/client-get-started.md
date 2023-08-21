---
title: "Getting started"
linkTitle: "Getting started"
description: "Simple tutorial to get started with the client account API"
date: 2023-08-19
draft: false
weight: 10
---

{{< alert title="Prerequisites" >}}
Before you get started with the client account API, you must have the following information ready:

- your `platform_id` to build the base URL
- the login details for your service user
{{< /alert >}}

## Build the base URL

Use your `platform_id` to build up the base URL for all available REST API endpoints. See [Base URL]({{< relref "base-url-service-user#base-url" >}}) for more information.

For example, if your `platform_id` is `my_company_platform_id`, then the base URL for the REST API endpoints in your staging environment is `https://api.staging.my_company_platform_id.platform.io`.

## Fetch API token

Before calling the client account API endpoints, fetch an API token with your service user using the [Authentication API]({{< relref "authentication#post-/v1/login/password" >}}) endpoint.

For example, if your service user for your staging environment has the following login details:

- `username`: service_user
- `password`: xxxyyy

, then the call looks as follows:

```sh
curl POST https://api.staging.my_company_platform_id.platform.io/v1/login/password \
--data '{
    "username": "service_user",
    "password": "xxxyyy"
}'
```

, with a success response as follows:

```json
{
    "api_token": "your_api_token"
}
```

## Create a client account

Use the newly created API token as a bearer token in the header for each call to the client account API endpoints. For example, when you create a new client account. See [Create client account]({{< relref "client-api-ref#post-/v1/client/signup" >}}) for more information.

Example call:

```sh
curl POST https://api.staging.my_company_platform_id.platform.io/v1/client/signup \
--header 'Authorization: Bearer your_api_token' \
--data '{
    "user_id": "80491f93-1eb1-42c2-b5e1-d2e94dac5ab9",
    "email": "new_client@client.com",
    "name": {
        "first_name": "new",
        "last_name": "client"
    },
    "password": "new_client"
}'
```

Response:

```json
{
    "client_token": "client_token"
}
```
