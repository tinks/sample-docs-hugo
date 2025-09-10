---
title: "Part II: Problem solving"
linkTitle: "Part II: Problem solving"
description: ""
date: 2025-09-09
draft: true
weight: 30
---

I think all three initiatives are important and if time allows it, I would execute these in the order below. If there is more pressure to provide improvements, I would start with the customer support feedback loop first. However, I would set up a documentation structure that enables the documentation team to also do the other parts without the need to rework a bunch of documentation.

## Entity relationship diagram, improved descriptions, and realistic examples

The main issue I see is how the partner maps the fields used in their application to the fields in the Nmbrs API. This is what I would do to improve the partner's understanding and make it easier for them to create the mapping.

1. Create an entity relationship diagram to clearly visualise how companies, debtors, employees, contracts, and so on relate to each other.
1. Improve the descriptions of the different entities and include real-life examples.
1. Improve the descriptions of the endpoints, fields, and enumerations. At the same time, I would improve the code snippets to show real-life examples.

## Getting started scenarios

It looks like certain entities need to be set up in the Nmbrs application before you can even start using the API. For example, the partner cannot implement and test the authentication flow without having at least one debtor and one user set up.

The Getting Started Guide would explain: 
- all prerequisites to get started
- the logical scenarios and prerequisites for different applications connecting to the Nmbrs platform

This will help partners to get started quickly, and have immediate guidance for their application integration.

## Customer support feedback loop

I would set up an initiative to work with customer support (or whoever deals with the customers’ questions) to find what the main pain points are creating an integration, improve the documentation in those areas, and follow up with customer support on what the impact is of the additional documentation.
