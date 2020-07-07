# SDM Proto API

This repository is the master of all proto files.

All services can include it as submodule or just copy paste.

## Init the submodule in a service repository

Be sure to remove any old proto folder before doing this (you will also need to commit).

In this example we checkout in the folder `src/main/proto`.

```shell script
git submodule add git@github.com:spoud/sdm-proto-api.git src/main/proto
```

## Update the submodule

```shell script
git submodule update --force --init --recursive --remote
```
