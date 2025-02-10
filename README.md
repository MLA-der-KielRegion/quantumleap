# quantumleap

QuantumLeap is a REST service for storing, querying and retrieving NGSI v2 and NGSI-LD (experimental support) spatial-temporal data.

## Voraussetzungen

* Kubernetes 1.23+
* Helm 3.8.0+

## Installation

```bash
$ cd quantumleap
$ helm install <my-release> helm --values <values file> -n <namespace>
```

alternativ:

```bash
$ helm upgrade --install <my-release> helm --values <values file> -n <namespace>
```

Beispiel:

```bash
$ helm upgrade --install my-release helm -n my-namespace --create-namespace --values <values file>
```

## Parameter
Die wichtigen Parameter werden im values.yaml konfiguriert.

| Name                    | Description                                     | Value  |
|:------------------------|:------------------------------------------------|:-------|
| quantumleap.loglevel    | loglevel of the service                         | WARNING |
| quantumleap.workers     | number of workers                               | 2      |
| quantumleap.defaultdb   |                                                 | timescale |
| quantumleap.useFlask    |                                                 | false  |
| quantumleap.geocoding   |                                                 | false   |
| quantumleap.threads     |                                                 | 1      |
| quantumleap.redisHost   |                                                 |        |
| quantumleap.redisPort   |                                                 | 6379   |
| quantumleap.defaultLimit |                                                | 10000  |
| quantumleap.keepRawEntity |                                               | false  |
| quantumleap.insertMaxSize |                                               |        |
| quantumleap.defaultCacheTtl |                                             | 60     |
| database.timescale.host |                                                 | quantumleap |
| database.timesclae.port |                                                 | 5432   |
| database.timescale.dbname |                                               | quantumleap |
| database.timescale.dbuser |                                               | quantumleap |
| database.timescale.dbpass |                                               |        |
| database.timesclae.sslenabled |                                           | false  |
| wq.offloadwork          |                                                 | false  |
| wq.recoveryFromEnqueingFailure |                                          | false  |
| wq.maxRetries           |                                                 | 0      |
| wq.failureTtl           |                                                 | 604800 |
| wq.successTtl           |                                                 | 86400  |
| wq.workers              |                                                 | 2      |
| cache.geocoding         |                                                 | true   |
| cache.queries           |                                                 | true   |
| cache.defaultTtl        |                                                 | 60     |


## Upgrading the chart

```bash
$ helm upgrade <my-release> helm --values <values file> -n <namespace>
```

## Links

https://quantumleap.readthedocs.io/en/latest/
https://github.com/orchestracities/ngsi-timeseries-api

## License
Copyright © 2024 ADDIX GmbH