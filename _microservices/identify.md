---
title: Identifying a microservice opportunity
position: 1
---

## Why a microservice architecture might be appropriate

If some or all of these conditions apply then a microservice approach might make sense. Not all microservices need to be used by many different applications, however, so even if you think it would only apply to a single application or service there still might be reason to break out as an independent application. The other information in this section can help you determine why you may or may not want to create a single-use microservice.

### High leverage

One benefit of a microservice is its applicability to a range of use cases or its use by a number of different applications. It’s important to identify the appropriate level of abstraction for the microservice so that it can be used as widely as possible. A solution doesn't _have_ to be highly-leveraged to justify its implementation as a microservice, but widely-leveraged solutions are likely to be strong candidates for a microservice architecture.

### Risk mitigation

Sometimes a particular feature or dependency can represent a single point of failure for an application. Microservices can help hedge that risk by isoltaing the failure to themselves.

### Increased flexibility

When single features or components of a larger application become too intertwined with the application's core business logic it can present a problem to developers who are trying to introduce changes to either the feature or the application as a whole. Implementing features as microservices allow developers to iterate without as much risk of unintended consequences.
