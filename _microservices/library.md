---
title: Library
position: 3
---

### [Form Dispatcher](https://github.com/cityofaustin/forms-api-dispatch)

The form dispatcher consumes web form submissions and dispatches them to auxiliary microservices,

#### What does it do?

The dispatcher allows web forms to be submitted to a single endpoint and sent to auxiliary microservices to do things like send an email or create a GitHub issue using the submitted data. It makes web forms more consistent, flexible, and reliable for developers, form authors, and customers.

#### Why does it exist?

#### Where is it used?

#### How is it used?

See the README for instructions

### [GitHub Issue Creator]()

The Issue Creator receives a request from the Form Dispatcher and uses the GitHub API to create an Issue on the repository specified in the form parameters.

Submit a form to the Form Dispatcher with the `destination` parameter set to `githubIssue`

### [Email Dispatcher](https://github.com/cityofaustin/form-email)

The Email dispatcher receives a request from the Form Dispatcher and delivers the submitted data to the `@austintexas.gov` email address specified in the form parameters.

#### What does it do?

It uses AWS SES to deliver email.

#### Why does it exist?

#### Where is it used?

#### How is it used?

Submit a form to the Form Dispatcher with the `destination` parameter set to `email`

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
