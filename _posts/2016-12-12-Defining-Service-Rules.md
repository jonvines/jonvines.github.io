---
layout: post
title:  "Defining service rules"
date:   2016-12-12 15:30:00 +0100
categories: services rules
excerpt: Defining service rules in a world where (lots of) services rule
published: true
---

One cannot develop services these days without mentioning Microservices. The premise being that our services are independently deployable pieces of Software and are small enough to allow some flexibility in where the services are deployed. 

> Microservices is a specialisation of an implementation approach for service-oriented architectures (SOA) used to build flexible, independently deployable software systems. Source [Wikipedia](https://en.wikipedia.org/wiki/Microservices)

A number of questions can arise very quickly when considering moving towards deploying very small services:
- How small is small enough?
- What technologies should we use?
- How much granularity should our service have?
- How should clients communicate with our service?
- etc...

In an effort to define service rules within our team, I became inspired by a story relating to [Jeff Bezos rules at Amazon](https://apievangelist.com/2012/01/12/the-secret-to-amazons-success-internal-apis/). We see laid out a very specific set of rules around what a service is and what its purpose should be. Whilst these rules apply at a very high level organisation wide, by distilling them a little further we had a nice set of rules for defining our own services. 

## Service rules ##
1. A service should have one responsibility
2. A service owns its integration points
3. A service is responsible for ensuring a clients use of its endpoints does not break the client
4. A service should only interact with other services via their published integration points
5. A service must be deployed independently

### A service should have one responsibility ###

Here we are referring to the context of the service being developed, harking back to [Single Responsibility](https://en.wikipedia.org/wiki/Single_responsibility_principle) at a higher abstraction or more specifically the [Bounded Context](http://dddcommunity.org/resources/ddd_terms/) of the service. This can also be seen discussed in the Thoughtworks blog post [Domain Driven Design for Services Architecture](https://www.thoughtworks.com/insights/blog/domain-driven-design-services-architecture).

### A service owns its integration points ###

This means any APIs, commands invoking action or events signalling action are owned and exposed appropriately by the service. As a .Net development team, all web apis are documented using [Swagger](http://swagger.io/) ensuring up to date docmentation of the services. Commands and events are built exposed as nuget packages as part of the CI delivery pipeline.

### A service is responsible for ensuring a clients use of its endpoints does not break the client ###

We aim to achieve this rule by using [Consumer Driven Contract Tests](https://docs.pact.io/) as part of our CI build pipeline, failure of the tests means the build is stopped and failed prompting the developer to resolve the failing test (usually a revert of the commit).

### A service should only interact with other services via their published integration points ###

Looking back on rule number two, a service should only be able to communicate via published integration points. This means no direct database access, no back doors, no referencing dlls inappropriately.

### A service must be deployed independently ###

If it comes to deployment, and we're deploying three services at the same time as they'd fail without each other then we're violating this rule.

## Conclusion ##
These rules are applicable to our team now, and have helped to distill our design principles whilst building new services. It has also helped us to better define context boundaries when defining new services. We'll revisit this list of rules as we learn more.
