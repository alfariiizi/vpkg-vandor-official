# VPkg Vandor Official

This directory contains the registry entries for official Vandor VPkg packages. Each package is stored in a separate GitHub repository and referenced by remote URL.

## Package Structure

Each package is defined by a YAML file containing metadata and remote URL information:

- `redis-cache.yaml` - Redis caching module with go-redis/v9
- `audit-logger.yaml` - Structured audit logging with context tracking

## Repository Structure

The actual package templates are stored in the separate repository: [vpkg-vandor-official](https://github.com/alfariiizi/vpkg-vandor-official)

Each package follows this structure:
```
package-name/
├── meta.yaml              # Package metadata
├── templates/             # Go template files
│   ├── *.go.tmpl         # Go source templates
│   └── README.md.tmpl    # Documentation template
└── README.md             # Package documentation
```

## Available Packages

### vandor/redis-cache
Simple Redis adapter using go-redis/v9 with Uber FX integration.
- **Type**: fx-module
- **Dependencies**: github.com/redis/go-redis/v9, go.uber.org/fx
- **Tags**: full-backend, eda, minimal, cache

### vandor/audit-logger
Structured audit logging with context tracking for compliance and debugging.
- **Type**: fx-module
- **Dependencies**: go.uber.org/zap, go.uber.org/fx
- **Tags**: full-backend, eda, minimal, logging

## Remote URL Format

All packages use remote URLs pointing to the raw GitHub content:
```
https://raw.githubusercontent.com/alfariiizi/vpkg-vandor-official/main/{package-name}
```

This allows for:
- Independent versioning of packages
- Easier maintenance and updates
- Community contributions via separate repositories
- Better organization and discoverability