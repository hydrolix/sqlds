
# sqlds for Hydrolix

Hydrolix-specific fork of [grafana/sqlds](https://github.com/grafana/sqlds) v5.1.1.

## Fork Changes

Forked on 2026-04-16. Summary of changes from upstream:

### Added

- `interpolator.go` — SQL interpolation and macro handling using Hydrolix's `clickhouse-sql-parser`
- `metadata.go` — Metadata provider for ClickHouse metadata queries (primary keys, ad-hoc filters) with TTL caching
- `models/settings.go` — Hydrolix-specific plugin settings and configuration models
- `driver_round_time_test.go` — Round time functionality tests
- Comprehensive test coverage for interpolator, macros, metadata, and settings

### Changed

- Renamed Go module to `github.com/hydrolix/sqlds/v5`
- Rewrote `macros.go` with Hydrolix-specific macro implementations
- Modified `connector.go`, `datasource.go`, `driver.go`, and `health.go` for Hydrolix integration

### Removed

- `.github/` CI/CD workflows, codeowners, and issue automation (Grafana-specific)
- `completion.go` — generic completion logic
- `driver-mock.go` — generic driver mock
- Generic integration and middleware tests

### Dependencies

- Added `github.com/hydrolix/clickhouse-sql-parser v0.3.0`
- Added `github.com/jellydator/ttlcache/v3 v3.4.0`
- Added `github.com/mithrandie/csvq-driver v1.7.0`
- Added `github.com/grafana/dataplane/sdata v0.0.9`