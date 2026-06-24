# SDM Proto API

Single source of truth for all SDM gRPC service definitions.

Published as versioned packages for Java (Maven) and TypeScript (npm), so consumers can depend on specific versions and get automated updates via Dependabot.

## Packages

### Maven (Java + gRPC + Mutiny stubs)

```xml
<dependency>
  <groupId>io.spoud.sdm</groupId>
  <artifactId>sdm-proto-api</artifactId>
  <version>1.0.0</version>
</dependency>
```

Requires the GitHub Packages Maven repository:
```xml
<repository>
  <id>github</id>
  <url>https://maven.pkg.github.com/spoud/sdm-proto-api</url>
</repository>
```

### npm (Connect-RPC TypeScript types)

```bash
npm install @spoud/sdm-proto-api
```

Requires `.npmrc` with GitHub Packages registry:
```
@spoud:registry=https://npm.pkg.github.com
```

## Development

### Prerequisites

- Java 21
- Node.js 22
- [Buf CLI](https://buf.build/docs/installation)

### Building locally

```bash
# Lint proto files
buf lint

# Build Java package
mvn -B package

# Build TypeScript package
cd ts && npm ci && npm run build
```

### Proto structure

```
activities/    blob/          collaboration/  global/
hooks/         logistics/     looker/         permission/
profiler/      schema/        search/         topology/
```

Each domain module contains `domain/`, `service/`, `selection/`, and/or `mutation/` subdirectories with versioned proto files (v1, v1alpha, v1alpha1).
