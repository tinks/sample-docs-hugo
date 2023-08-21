---
title: "REST APIs"
linkTitle: "REST APIs"
description: "Integrate with your platform instance"
date: 2023-08-19
draft: false
menu:
  main:
    weight: 10
    pre: <i class='fas fa-file-code'></i>
cascade:
  - type: rapidoc
---

The REST APIs are used to create an integration between your web application and your platform instance. This documentation contains the necessary information to get started:

- how to construct the base URL for all endpoints
- information about the service user used to fetch authentication tokens
- information about rate limiting
- tutorials on how to get started with each set of endpoints
- descriptions of each endpoint, their request body and their response bodies

The functionality to try out the endpoints directly from the documentation is only available when you open the documentation from the staging environment URL. This guarantees that you can only make test calls to your staging environment and avoids running into CORS issues, because we do not allow you to make cross domain calls from the production environment to the staging environment or the other way around.
