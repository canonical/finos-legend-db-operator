[![FINOS - Incubating](https://cdn.jsdelivr.net/gh/finos/contrib-toolbox@master/images/badge-incubating.svg)](https://finosfoundation.atlassian.net/wiki/display/FINOS/Incubating)

# FINOS Legend Database Manager Operator

## Description

The Legend Operators package the core [FINOS Legend](https://legend.finos.org)
components for quick and easy deployment of a Legend stack.

This repository contains a [Juju](https://juju.is/) Charm for
deploying a service which exposes a MongoDB database to other Legend Charms.

The full Legend solution can be installed with the dedicated
[Legend bundle](https://charmhub.io/finos-legend-bundle).


## Usage

The Legend Database Operator can be deployed by running:

```sh
$ juju deploy finos-legend-db-k8s --channel=edge
```


## Relations

The standalone DBM will initially be blocked, and will require being
related to the [MongoDB Operator](https://github.com/canonical/mongodb-operator).

```sh
$ juju deploy mongodb-k8s --channel=edge
$ juju relate finos-legend-db-k8s mongodb-k8s
# Relate to the legend services:
$ juju relate finos-legend-db-k8s finos-legend-sdlc-k8s
$ juju relate finos-legend-db-k8s finos-legend-engine-k8s
$ juju relate finos-legend-db-k8s finos-legend-studio-k8s
```

## Contributing

Visit Legend [Contribution Guide](https://github.com/finos/legend/blob/master/CONTRIBUTING.md) to learn how to contribute to Legend.

## License

Copyright (c) 2021-present, Canonical

Distributed under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0).

SPDX-License-Identifier: [Apache-2.0](https://spdx.org/licenses/Apache-2.0)

