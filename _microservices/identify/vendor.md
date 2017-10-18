---
title: Vendors
position: 1
---
# Vendor considerations

:construction: This is a work in progress

There are a number of ways to work with 3rd-party vendors to enjoy the benefits of a microservice approach.

## Integrating with existing solutions

A microservice can be used to connect city-built software with vendor solutions that are already in use, whether those solutions are off-the-shelf or custom-built. In this case, it is important to promote close collaboration between the microservice author(s) and the engineering team that's responsible for iterations to and maintenance on the existing solution to ensure that and update doesn't break the microservice.

## Full-stack solutions

If you're considering an all-in-one solution or platform, these questions can help determine whether it offers the flexibility to either be used _as_ a microservice or can effectively use an existing one:

- Does the service have an API that will allow developers to _read_ from and _write_ to the database?
- Can the service tap into external APIs that allow it to interact with separate, independent systems?

If possible, have a web developer from your department or from CTM participate in the vetting process so they can provide valuable insights into the practical application of a vendor's data & service portability features.

Additionally, a requirements-gathering process can help provide more focus to a vendor assessment. If you work with users of the solution to understand and articulate specific needs you can more accurately gauge the viability of one solution over another. For example, a requirement to "provide geocoding support" is less help ful than one to "determine whether a provided set of latitude/longitude coordinates are included in one or several pre-defined geographic polygons".

## Custom builds

If you're engaging with an outside vendor to build a custom solution you can refer them to these guides as a suggestion for how to make critical architectural decisions.

## Examples

### Socrata + Austin Convention Center Department

The events calendar is one of the cornerstones of the Austin Convention Center's web presence. When they embarked on a full website re-build one of the first challenges they had to tackle was how to keep their calendar up-to-date without requiring too much employee overhead.

As part of their open data initiative, ACCD was already publishing event information to [the official Open Data Portal](https://data.austintexas.gov/Business/ACCD-Event-Listings/p9ma-z6y9) using the Socrata platform. Since the platform makes data accessible to other applications via an API endpoint, ACCD was able to add a nightly rake task to their website architecture that pings the Socrata API each night and updates the calendar data with any new entries.