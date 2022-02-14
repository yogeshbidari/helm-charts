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

## Configuration

Configuration

| Parameter                                                                   | Description                                                                                                        | Default                         |
| --------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------| ------------------------------- |
| **ReplicaCount**                                                            |
| `replicaCount`                                                              | Replica of each pod to be deployed                                                                                               | `1`                             |
| **Namespace**                                                            |
| `namespace`                                                              | Namespace where application to be deployed                                                                                              | `nil`                             |
| **Environment**                                                            |
| `env`                                                              | Environment Label where application to be deployed                                                                                              | `nil`                             |
| **Image**                                                                   |
| `image.repository`                                                          |  Image repository name                                                                                                    | `nil`                   |
| `image.tag`                                                                   |  Image tag                                                                                                     | `nil`                        |
| `image.pullPolicy`                                                          |  Image pull policy                                                                                             | `nil`                  |
| `image.pullSecretName`                                                          |  Image pull secret name                                                                                          | `nil`                           |
| **Master Details**                                                            |
| `master.name`                                                              |  Name of master-hdfs to be deployed                                                                                             | `worker-hdfs`                             |
| **SecurityContext**                                                         |
| `master.securityContext.runAsUser`                                                 |  User ID for containerized process User                                                                                                   | `nil`                          |
| `master.securityContext.fsGroup`                                                   |   Group ID for containerized process Group                                                                                                  | `nil`                          |
| `master.securityContext.runAsGroup`                                                   |  Group ID for containerized process                               | `nil`                          |
| **Environment Variables**
| `master.env`                                                   | Environment variables for the master hdfs pods                               | `nil`                          |
| **probes**
| `master.probes`                                                                | Readiness and Liveliness probes need to be configured if required            | `nil`                           |
| **probes**
| `master.ports`                                                                | Ports for accessing the services            | `nil`                           |
| **Resources**
| `master.resources`                            | Pod resource requests and limits            | `nil`                           |
| **volumemounts**
| `master.volumemounts.mount`                            | volumemounts is a list accepts volume mounts with properities name and mountpath           | `nil`                     |
| **volumeClaimTemplates**
| `master.volumeClaimTemplates.claim`                            | volumeClaimTemplates is a list accepts pvc claims with properities of name and size         | `[]`                 
| **Service**                                                                     |
| `master.service.annotations`                                                            | ADD Annotation If LoadBalancer InternalIP set to true                                                                                 | `nil`                         |
| `master.service.type`    | service type |  `ClusterIP`  |
| `master.service.loadbalancerInternal_IP`       | Set to true when need to use Internal LoadBalancer IP | `nil` |
| `master.service.loadBalancerSourceRanges`                                                   | Set when need to use LoadBalancer Source IP Ranges                                                                                      | `[]`                      |
| `master.service.ports    `                                                       | service ports to be opened                        | `[]`                            |
| **Worker Details**                                                            |
| `workers.name`                                                              |  Name of master-hdfs to be deployed                                                                                             | `master-hdfs`                             |
| **SecurityContext**                                                         |
| `workers.securityContext.runAsUser`                                                 |  User ID for containerized process User                                                                                                   | `nil`                          |
| `workers.securityContext.fsGroup`                                                   |   Group ID for containerized process Group                                                                                                  | `nil`                          |
| `workers.securityContext.runAsGroup`                                                   |  Group ID for containerized process                               | `nil`                          |
| **Environment Variables**
| `workers.env`                                                   | Environment variables for worker hdfs pod                               | `nil`                          |
| **probes**
| `workers.probes`                                                                | Readiness and Liveliness probes need to be configured if required            | `nil`                           |
| **probes**
| `workers.ports`                                                                | Ports for accessing the services            | `nil`                           |
| **Resources**
| `workers.resources`                            | Pod resource requests and limits            | `nil`                           |
| **volumemounts**
| `workers.volumemounts.mount`                            | volumemounts is a list accepts volume mounts with properities name and mountpath           | `nil`                     |
| **volumeClaimTemplates**
| `workers.volumeClaimTemplates.claim`                            | volumeClaimTemplates is a list accepts pvc claims with properities of name and size         | `[]`                 
| **Service**                                                                     |
| `workers.service.annotations`                                                            | ADD Annotation If LoadBalancer InternalIP set to true                                                                                 | `nil`                         |
| `workers.service.type`    | service type |  `ClusterIP`  |
| `workers.service.loadbalancerInternal_IP`       | Set to true when need to use Internal LoadBalancer IP | `nil` |
| `workers.service.loadBalancerSourceRanges`                                                   | Set when need to use LoadBalancer Source IP Ranges                                                                                      | `[]`                      |
| `workers.service.ports    `                                                       | service ports to be opened                        | `[]`                            |
