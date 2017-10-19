---
title: Library
position: 3
---

### [Knackpy](https://github.com/cityofaustin/knackpy)

Knackpy is a Python client module for interacting with data stored in [Knack](https://www.knack.com) applications.

#### What does it do?

It provides a developer-friendly interface to the Knack API from a Python client.

#### Why does it exist?

The Transportation Department maintains a suite of low-code business applications built with a web platform called [Knack](http://knack.com).

Knack applications support a growing number of needs within the department, including a visitor sign-in application, an interactive data inventory, and an asset and work management system.

Knackpy makes it easy for developers to integrate Knack applications with other systems by providing a simple interface to extract data from and load data into the application.

A common use case is to publish data from a Knack application to the City's Socrata-powered open data portal. By passing Knackpy a handful of application parameters, data is extracted in a state that is ready for upload to the data portal (via [Sodapy](https://pypi.python.org/pypi/sodapy, for example)).

#### Where is it used?

- Transportation Data Publishing scripts ([GitHub](https://github.com/cityofaustin/transportation-data-publishing))
  - This repository houses a number of scripts which utilize Knackpy to extract data and publish it to the City's Open Data Portal.
  - The repository also contains [utility scripts](https://github.com/cityofaustin/transportation-data-publishing/tree/master/data_tracker) which extend Knack application features and enable integration with other applications, such as the 311 CSR system.

#### How is it used?

Knackpy can be installed in any Python application as a module.
