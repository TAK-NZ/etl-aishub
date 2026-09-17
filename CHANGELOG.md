# CHANGELOG

## Emoji Cheatsheet
- :pencil2: doc updates
- :bug: when fixing a bug
- :rocket: when making general improvements
- :white_check_mark: when adding tests
- :arrow_up: when upgrading dependencies
- :tada: when adding new features

## Version History

### v1.1.0

:tada: **Added**
- `capabilities.json` manifest describing task permissions and invocation modes, validated against `@tak-ps/etl`'s `StaticCapabilitiesSchema`
- Basic test suite using Node's built-in `node:test` via `tsx`

:rocket: **Changed**
- CI now builds and pushes the Docker image with `docker buildx build`, embedding `capabilities.json` as the `com.cloudtak.capabilities` OCI annotation so CloudTAK can read it directly from ECR
- Switched to `Task.init()` in the local-dev and Lambda handler entry points
- Bumped Node.js to 24 in CI (`lint.yml`, `etl-deploy.yml`) and added `engines.node >= 24` to `package.json`, matching the Dockerfile's `nodejs:24` base image

:arrow_up: **Dependencies**
- Updated dependencies via `npm update`, resolving all `npm audit` findings (8 vulnerabilities to 0)

### v1.0.0

:tada: **Added**
- Initial implementation of AISHub ETL
- Support for AISHub.net REST API
- Ship type classification and CoT mapping
- Configurable bounding box filtering
- Speed filtering capabilities
- Comprehensive vessel information display