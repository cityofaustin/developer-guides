---
title: Reliability
position: 1
---

## Reliability
A reliable service is one that is available when it's needed and that suffers from limited downtime. Keep the following in mind when designing a reliable microservice.

### Scalability
- Have you calculated the extremes of request rates, and can you service tolerate them? A good example is ATXFloods, a service which experiences massive peaks at precisely the time it is most critical to its users. Its architecture must be able to accommodate an increased response rate several orders of magnitude higher than the traffic it experiences 99% of the year.

### Monitoring
- How will you know if the service is down? Do you have proactive error logging and reporting or do you rely on consumers of the service to inform you of an outage?

### Performance

- How quickly does your service process requests?
- Do you have timeouts set so your service does not hang indefinitely on a single failed request or response?
