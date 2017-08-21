---
title: Security
position: 3
---

## Security

### Consumer whitelist

- If your microservice is not a publicly-accessible endpoint have you defined an explicit list of whitelisted IPs that it will respond to?
- Should you issue token-based credentials to indidivual consumers of the microservice in order to monitor request rates?

### SSL

- Does your service take advantage of the city's SSL certificates to support end-to-end encryption and inhibit domain spoofing?

### Intentional abuse

- Could your service be targeted by a bad actor to disrupt a critical digital service offered by the city?
- If your service includes file upload, are there restrictions on the size and volume of uploads to prevent someone from using it as their own free data store?

### Hardware and software updates

- Do you have a plan to make sure your software, firmware, and hardware is up-to-date to take advantage of security enhancements and patches?

### Logging

- Does your logging or monitoring make it easy to quickly identify potential abuses?
