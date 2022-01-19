# Run Book / System Operation Manual

## Service or system overview

**Service or system name:** 

### Alarms associated to this runbook

> What alarms link to this page?

* [Kafka message stream lag time too high](https://www.google.com)
* [Kafka message stream lag time absent](https://www.google.com)

### Dashboards relevant to this runbook

> What dashboards are useful while using this runbook?

* [Service Overview Dashboard](https://www.google.com)
* [Data Throughput Dashboard](https://www.google.com))

### Service owner

> Which team owns and runs this service or system?

["LOGGING" Logging ingestion team](https://www.google.com)

### External dependencies

> What external applications/services/etc does this application have?

* Kafka for log streaming
* EC2 for compute
* S3 for object storage

### Throttling

> How can the system be throttled to avoid flooding other dependent systems? Can specific customer/tenants be throttled individually to eliminate "noisy neighbor" incidents?

#### Throttling - external customers/tenants

* [API Gateway](https://www.google.com) controls overall throttling
* Per-tenant throttling at the service level via the [Feature Service](https://www.google.com)

#### Throttling - internal services

* Service level throttling based off the [Feature Service](https://www.google.com)

### Expected traffic and load

> Details of the expected throughput/traffic: requests/sec, data throughput, "chatty" customer/tenants

* 1000 requests per second per partition
* 5GB/hr per partition

### Tools

> What tools are available to help operate the system?

* [web console](https://www.google.com) to reboot/replace instances
* [deployment UI](https://www.google.com) to update/revert a deployment
* [Grafana](https://www.google.com) to view metrics/dashboards

## Troubleshooting

### Events and error messages

> What significant events, state transitions and error events may be logged?

* Kafka message lag time too high: 
*   Check [kafka dashboard](https://www.google.com) for hot partitions
*   Check [ingestion dashboard](https://www.google.com) for socket count
*     If socket count > 15,000 then restart container...

### Metrics

> What significant metrics will be generated?

* [Kafka lag per partition](https://www.google.com)
* [Data ingestion throughput](https://www.google.com)
* [Host metrics](https://www.google.com)

### Health checks

> How is the health of dependencies (components and systems) assessed? How does the system report its own health?

#### Health of dependencies

* [object storage health](https://www.google.com) 
* [Kubernetes cluster health](https://www.google.com)

#### Health of service

* `/health` HTTP endpoint: 200 --> basic health, 500 --> bad configuration
* `/health/deps` for checking dependencies

## Operational tasks

### Deployment

> How is the software deployed? How does roll-back happen?

* [Deployment Management UI](https://www.google.com) to control infrastructure and application deployment orchestration

### Routine and sanity checks

> What kind of checks need to happen on a regular basis?

* `/health` endpoints should be checked every 60secs
* [Canaries](https://www.google.com) every 5-15 minutes

