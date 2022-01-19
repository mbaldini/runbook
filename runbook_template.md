# Run Book / System Operation Manual

## Service or system overview

**Service or system name:** 

### Alarms associated to this runbook

> What alarms link to this page?

_(e.g. Kafka message stream lag time too high)_

### Dashboards relevant to this runbook

> What dashboards are useful while using this runbook?

_(e.g. [Service Overview Dashboard](https://www.google.com), [Data Throughput Dashboard](https://www.google.com))_

### Service owner

> Which team owns and runs this service or system?

_(e.g. ["LOGGING" Logging ingestion team](https://www.google.com))_

### External dependencies

> What external applications/services/etc does this application have?

_(e.g. Kafka for log streaming, EC2 for compute, S3 for object storage)_

### Throttling

> How can the system be throttled to avoid flooding other dependent systems? Can specific customer/tenants be throttled individually to eliminate "noisy neighbor" incidents?

#### Throttling - external customers/tenants

_(e.g. [API Gateway](https://www.google.com) controls overall throttling, with per-tenant throttling at the service level via the [Feature Service](https://www.google.com))_

#### Throttling - internal services

_(Service level throttling based off the [Feature Service](https://www.google.com))_

### Expected traffic and load

> Details of the expected throughput/traffic: requests/sec, data throughput, "chatty" customer/tenants

_(e.g. Max: 1000 requests per second @ 5GB/hr per partition)_

### Tools

> What tools are available to help operate the system?

_(e.g. Use the [web console](https://www.google.com) to reboot/replace instances, [deployment UI](https://www.google.com) to revert a deployment, [Grafana](https://www.google.com) to view metrics/dashboards)_

## Troubleshooting

### Events and error messages

> What significant events, state transitions and error events may be logged?

_(e.g. Kafka message lag time too high: Check [kafka dashboard](https://www.google.com) for hot partitions. Check [ingestion dashboard](https://www.google.com) for socket count. If socket count > 15,000 then restart container...)_

### Metrics

> What significant metrics will be generated?

_(e.g. [Kafka lag per partition](https://www.google.com), [Data ingestion throughput](https://www.google.com), [Host metrics](https://www.google.com))_

### Health checks

> How is the health of dependencies (components and systems) assessed? How does the system report its own health?

#### Health of dependencies

_(e.g. Use [object storage health](https://www.google.com) and [Kubernetes cluster health](https://www.google.com))_

#### Health of service

_(e.g. Provide `/health` HTTP endpoint: 200 --> basic health, 500 --> bad configuration + `/health/deps` for checking dependencies)_

## Operational tasks

### Deployment

> How is the software deployed? How does roll-back happen?

_(e.g. Use [Deployment Management UI](https://www.google.com) to control infrastructure and application deployment orchestration)_

### Routine and sanity checks

> What kind of checks need to happen on a regular basis?

_(e.g. All `/health` endpoints should be checked every 60secs, [Canaries](https://www.google.com) every 5-15 minutes)_

