[![add-on registry](https://img.shields.io/badge/DDEV-Add--on_Registry-blue)](https://addons.ddev.com)
[![tests](https://github.com/jackd248/ddev-openapi-mock/actions/workflows/tests.yml/badge.svg?branch=main)](https://github.com/jackd248/ddev-openapi-mock/actions/workflows/tests.yml?query=branch%3Amain)
[![last commit](https://img.shields.io/github/last-commit/jackd248/ddev-openapi-mock)](https://github.com/jackd248/ddev-openapi-mock/commits)
[![release](https://img.shields.io/github/v/release/jackd248/ddev-openapi-mock)](https://github.com/jackd248/ddev-openapi-mock/releases/latest)

# DDEV Openapi Mock

## Overview

This add-on integrates Openapi Mock into your [DDEV](https://ddev.com/) project.

## Installation

```bash
ddev add-on get jackd248/ddev-openapi-mock
ddev restart
```

After installation, make sure to commit the `.ddev` directory to version control.

## Usage

| Command | Description |
| ------- | ----------- |
| `ddev describe` | View service status and used ports for Openapi Mock |
| `ddev logs -s openapi-mock` | Check Openapi Mock logs |

## Advanced Customization

To change the Docker image:

```bash
ddev dotenv set .ddev/.env.openapi-mock --openapi-mock-docker-image="busybox:stable"
ddev add-on get jackd248/ddev-openapi-mock
ddev restart
```

Make sure to commit the `.ddev/.env.openapi-mock` file to version control.

All customization options (use with caution):

| Variable | Flag | Default |
| -------- | ---- | ------- |
| `OPENAPI_MOCK_DOCKER_IMAGE` | `--openapi-mock-docker-image` | `busybox:stable` |

## Credits

**Contributed and maintained by [@jackd248](https://github.com/jackd248)**
