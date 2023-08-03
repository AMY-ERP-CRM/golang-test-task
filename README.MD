<p align="center">
  <img src="https://hsto.org/webt/ih/ds/fu/ihdsfuqni5apj0my18tnukzztw0.png" alt="Logo" width="128" />
</p>

# Test Task for GoLang Developer

![Project language][badge_language]

## Task Description

Need to develop an Application, provided HTTP API to get data about current Forex price for Currencies (EUR/USD, USD/GBP, USD/JPY). DATA provided by [TradingView API][dataset_link]


## Description of required functionality

- Application every 30 seconds, get data from API link and store it in Storage;
- HTTP API should return response in JSON. Maximum timeout is 2ms till first HTTP byte response (TTFB)
- Serving HTTP requests to API-endpoints that implement a search for stored data;
- Servicing HTTP requests to a route that returns metric data (in [prometheus][prometheus_format] format) of the application's operation.
- You choose the method of API development.

App should content next metrics:

- The total number of processed requests to API endpoints;
- The number of errors in processing HTTP requests to API endpoints;
- Data on the processing time of HTTP requests to the API endpoint;
- Additional metrics, at your discretion.

## Implementation Requirements

- Redis must be used as a data storage;
- All functions _(exported and non-exported)_ must be accompanied by a clear comment (in English);
- Do not unnecessarily shorten the names of variables and constants - the code is written for people, and it should be as simple and understandable as possible;
- You can use any third party packages, but don't use any framework;
- All key functionality should be captured by unit tests;
- After completing the work on the task, it is necessary to write the accompanying documentation for working with the application in the `README.md` file in the repository root;
- The datastore connection settings configuration must be able to be controlled by both startup flags and environment variables. Configuration options should be described in the `README.md` file of your repository.

## The advantages will be

- Setting up CI _(by GitHub actions, TravisCI, etc)_ that runs tests and builds for each commit;
- Automatic assembly of the Docker image with the application;
- Intuitive breakdown of commits - one specific task - one commit or PR (its edits - a separate commit or PR);
- Writing of all texts of commits - in English.


## Execution result

The link to the repository with your implementation must be sent to our HR or TeamLead, from whom you received the link to this repository.

The application should launch successfully after executing:

```bash
$ git clone ...
$ make build
$ docker-compose up -d
$ docker-compose run --rm app ./app
```

> If a different set of commands is required to run the application, be sure to reflect this in the `README.md` file of your repository.

Unit tests should also be performed using the command:

```bash
$ make test
# and optionally:
$ make cover
```


[badge_language]:https://img.shields.io/badge/language-go_1.20.7-blue.svg?longCache=true
[dataset_link]:https://www.tradingview.com/rest-api-spec/
[prometheus_format]:https://github.com/prometheus/docs/blob/master/content/docs/instrumenting/exposition_formats.md
