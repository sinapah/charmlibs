# Changelog

All notable changes to the charmlibs.interfaces.otlp library will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.0]

### Added
- Initial release of charmlibs.interfaces.otlp
- `OtlpRequirer` for consuming OTLP endpoints from a provider relation
- `OtlpProvider` for publishing OTLP endpoints to requirer relations
- `OtlpEndpoint` pydantic model representing a single OTLP endpoint (protocol, URL, telemetries); used to communicate the required information for a server offering an OTLP API endpoint
- `OtlpRequirerAppData` and `OtlpProviderAppData` pydantic models for relation databag validation
- Support for filtering endpoints by protocol (`http`, `grpc`) and telemetry type (`logs`, `metrics`, `traces`)
- `grpc` is favoured over `http` when multiple endpoints are available
- Rule publishing support for LogQL and PromQL alert rules via `OtlpRequirer.publish()`
- LZMA+base64 compression of rules in the requirer databag to avoid Juju databag size limits
- `OtlpProvider.rules()` for fetching and validating injected rules from all requirer relations
- Generic aggregator rules automatically included in every requirer's published rule set
- Python 3.10+ compatibility


