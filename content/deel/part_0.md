---
title: "Part 0: Document your thought process"
linkTitle: "Part 0: Document your thought process"
description: ""
date: 2025-09-09
draft: true
weight: 10
---

## Knowledge gaps

- **Why integrate with the Nmbrs API**
    
    I could not find information about why a partner would make an integration with Nmbrs. What purpose does Nmbrs fulfil for an HRIS? Why is it important to sync employee data?

    This is the sort of information I'd like to put in the introduction.
- **Pagination is unclear**

    The pagination documentation and examples do not match up in the Nmbrs API documentation. I am unsure if the pagination parts in my payload examples are correct.

- **How should the integration work**

    I do not know what the integration should look like. I would ask the product owner and developers.

## Assumptions

- **Storing data**

    The application that integrates with the Nmbrs API must also store some information from the entities stored in the Nmbrs application. For example, the application must store the `employeeId` sent from the Nmbrs application in its own employee record.
- **Implications of PUT operation**

    I assume that developers know that when using `PUT` operations that they must keep the original payload, and only update or add the fields that have changed in the original payload.

    This is also assuming that the Nmbrs API follows the conventions of REST API operations.
- **Application operation**

    I assume that an _existing_ application integrates with the Nmbrs application. The users keep using the application they are used to, and, in the background, the application syncs the data to the Nmbrs application. I assume that the entities in the Nmbrs application cannot be updated, and the original application serves as the source of truth.

## Solution choices

- **Scenarios**

    Scenarios and how to implement them shows the relationship between entities and use cases of the API.
- **Sequence diagrams**

    Like scenarios, sequence diagrams show the relationship between entities, and visualise the order of actions.

    I believe diagrams are really helpful, especially for more visual learners.

## Real-life situation

This is what I would do in a real-life situation when asked to created this documentation:

- Ask the product owner and developers what an integration should look like for the partner.
- Verify with the developers that my code snippets are correct.
- Send docs for peer review and product owner review.

If time allows, I would also like to develop a solution where the code snippets are pulled from the code. This allows the snippets to stay in sync with future API development.