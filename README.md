# Helm Chart for OpenStack Exporter

## Description

This is a forked version of the [official Helm Chart](https://github.com/openstack-exporter/helm-charts) for [OpenStack Exporter](https://github.com/openstack-exporter/openstack-exporter), a tool to export Prometheus metrics from a running OpenStack Cloud.
The fork has been created due to the inactivity of the official Helm Chart, see [#21](https://github.com/openstack-exporter/helm-charts/issues/21).

## Configuration

The chart configuration is done in the `values.yaml` file.

## Usage

### Installation from helm registry
The most recent versions of Helm chart packages are published in the [SCS registry](https://registry.scs.community/harbor/projects/31/repositories/prometheus-openstack-exporter/artifacts-tab?publicAndNotLogged=yes).
Explore the available versions and install the Helm chart package as follows:
```bash
helm upgrade --install prometheus-openstack-exporter oci://registry.scs.community/openstack-exporter/prometheus-openstack-exporter --version <version> 
```

### Installation from source
```bash
# Get a local copy
git clone https://github.com/openstack-exporter/helm-charts.git

# Package the chart
cd helm-charts/charts/prometheus-openstack-exporter/
helm package . 

# Get chart version & install
version="$(awk '/^version:/{ print $NF }' Chart.yaml)"
helm install prometheus-openstack-exporter prometheus-openstack-exporter-${version}.tgz
```

## Contributing

Please fill pull requests or issues under Github.
