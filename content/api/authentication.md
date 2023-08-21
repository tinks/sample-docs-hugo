---
title: "Authentication API"
linkTitle: "Authentication API"
description: "How to authenticate to use the REST APIs"
date: 2023-08-19
draft: false
weight: 30
---

## Bearer token

An API token is used to authenticate with all endpoints, except the Authentication API, where the API token is fetched from. Use your [service account]({{< relref "base-url-service-user#service-user" >}}) details to fetch the API token.

This API token is used as a Bearer token in the header of each API call.

```tsx
Headers:
  Authorization: Bearer <api-token>
```

## API token payload and expiry

{{% alert %}}Cache the API token and only request a new one when the old one has either expired or is near expiry.{{% /alert %}}

The API token returned from this API endpoint is a JSON Web Token (JWT) and contains an expiry time. This means that you are required to fetch a new API token when the previous one has expired before making calls to other endpoints which require an API token for authentication.

The expiry time can be read from the token’s payload part, in the `exp` property.

Example payload of a token:

```json
{
  "r": [
    "service"
  ],
  "exp": 1642159394,
  "sub": "f76ec415-1811-4935-a659-63dc2483c852",
  "reg": "za"
}
```

For more information on JWT and decoding the token, refer to [jwt.io](https://jwt.io/).

## API reference

Try out fetching an API token for your staging environment.

{{< rapi-doc src="../api/v1/auth/openapi.yaml" no-auth="true" >}}