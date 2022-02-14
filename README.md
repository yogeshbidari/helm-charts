# Helm Chart for HDFS installation

## Introduction

This Helm chart installs HDFS on kubernetes cluster

## Prerequisites

- Kubernetes cluster 1.10+
- Helm 3.0.0+

## Installation

## Install the chart

Install the hdfs helm chart with a release name my-release:

> helm install my-release hdfs/

## Install with custom values.yaml

> helm install my-release hdfs/ -f values.yaml


## Uninstallation

To uninstall/delete the my-release deployment:

> helm uninstall my-release
