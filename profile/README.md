# OpenPhase Labs

OpenPhase Labs builds open infrastructure for the public agencies that operate
physical systems - starting with traffic signals.

Our work is published as **open contracts first, implementations second**. A
contract here is a schema, not an application - it does nothing by itself, and
that is the point: anyone can build against it without building with us.

## Traffic Ops

Our transportation line: software for the agencies that operate traffic signals.

### Contracts

Two of them, and they are not the same thing. Both are Protobuf; they sit on
different boundaries.

**[OpenPhase](https://github.com/OpenPhase-Labs-Org/openphase-protocol)** - the
messages Traffic Ops products speak to *each other*, over NATS JetStream, MQTT
and other transports. Publish/subscribe, product to product. Protobuf schemas
plus a spec doc per subject.

**[TSIGMA plugin contract](https://github.com/OpenPhase-Labs-Org/tsigma-contract)** -
the boundary between a TSIGMA host and the plugins it loads: decoders, ingestion
methods, reports, notifications, auth and storage. gRPC over a subprocess plugin
protocol, with a host-served callback plane. Host to plugin, not product to
product.

If you are integrating two systems, you want OPENPHASE. If you are writing a
plugin for TSIGMA, you want the plugin contract.

### Implementations

**TSIGMA** *(not yet published)* - automated traffic signal performance
measures. Ingests controller event logs, decodes them, validates them, and
reports on them. Extended through plugins rather than forks, against the
contract above.

## Licensing

Contracts are published under **MPL-2.0**: modifications to the contract files
stay open, so a divergent copy cannot be closed, while anything built against
them is yours.

## Elsewhere

<!-- Add the website here once it is live, and set it in the profile's Website
     field too (Settings -> Public profile) - that field appears in search
     results where this README does not. -->
