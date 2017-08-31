---
title: Reliability
position: 1
---

## Reliability
A reliable service is one that is available when it's needed and that suffers from limited downtime. Keep the following in mind when designing a reliable microservice.

### Monitoring
- How will you know if the service is down? Do you have proactive error logging and reporting or do you rely on consumers of the service to inform you of an outage?

### Performance

- How quickly does your service process requests?
- Do you have timeouts set so your service does not hang indefinitely on a single failed request or response?

### Scalability

- Have you identified extremes of server requests and data transfer?
- Are there other dependncies like 3rd-party API rate limits that might be a bottleneck in your application?
- Read more in the [scalability guide](../scalability)
