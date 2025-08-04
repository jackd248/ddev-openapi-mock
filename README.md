<div align="center">

# DDEV Openapi Mock

[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/jackd248/ddev-openapi-mock/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/jackd248/ddev-openapi-mock/actions/workflows/tests.yml?query=branch%3Amain)
[![last commit](https://img.shields.io/github/last-commit/jackd248/ddev-openapi-mock)](https://github.com/jackd248/ddev-openapi-mock/commits)
[![release](https://img.shields.io/github/v/release/jackd248/ddev-openapi-mock)](https://github.com/jackd248/ddev-openapi-mock/releases/latest)
</div>

## Overview

This add-on integrates [Openapi Mock](https://github.com/muonsoft/openapi-mock) into your [DDEV](https://ddev.com/) project to easily test and interact with a fake OpenAPI interface.

## Installation

```bash
ddev add-on get jackd248/ddev-openapi-mock
ddev restart
```

After installation, make sure to commit the `.ddev` directory to version control.

## Configuration

By default, the OpenAPI [petstore specification](https://github.com/readmeio/oas-examples/blob/main/3.0/json/petstore.json) is used for demo purpose. 
You can change the OpenAPI specification by setting the `OPENAPI_MOCK_SPECIFICATION` environment variable in your `.ddev/.env.openapi-mock` file to use an absolute URL or to a local specification file within `.ddev/openapi/`, e.g. `file:/data/openapi.json`.

## Usage

Regarding your used open api specification, you can use the following commands to interact with the Openapi Mock service:

```bash
ddev launch :8080/pet/findByStatus
```

## Advanced Customization

To change the Docker image:

```bash
ddev dotenv set .ddev/.env.openapi-mock --openapi-mock-docker-image="muonsoft/openapi-mock:latest"
ddev add-on get jackd248/ddev-openapi-mock
ddev restart
```

Make sure to commit the `.ddev/.env.openapi-mock` file to version control.

All customization options (use with caution):

| Variable | Flag | Default                                                                                            |
| -------- | ---- |----------------------------------------------------------------------------------------------------|
| `OPENAPI_MOCK_DOCKER_IMAGE` | `--openapi-mock-docker-image` | `muonsoft/openapi-mock:latest`                                                                     |
| `OPENAPI_MOCK_PORT` | `--openapi-mock-port` | `8080`                                                                                             |
| `OPENAPI_MOCK_SPECIFICATION` | `--openapi-mock-specification` | `https://raw.githubusercontent.com/muonsoft/openapi-mock/refs/heads/master/examples/petstore.yaml` |
| `OPENAPI_MOCK_USE_EXAMPLES` | `--openapi-mock-use-examples` | `if_present`                                                                                       |
| `OPENAPI_MOCK_CORS_ENABLED` | `--openapi-mock-cors-enabled` | `true`                                                                                             |

## Credits

**Contributed and maintained by [@jackd248](https://github.com/jackd248)**
