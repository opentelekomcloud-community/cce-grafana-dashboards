# Basic Grafana + Prometheus Deployment

This folder contains the necessary configuration files for deploying a basic Grafana and Prometheus monitoring stack. For a more fine tuned deployment I would recommend visiting the IITS [chart](https://github.com/iits-consulting/charts/tree/main/charts/prometheus-stack).

## Overview

This setup provides a foundational monitoring solution with Grafana for visualization and Prometheus for metrics collection. It is suitable for monitoring Kubernetes clusters and other systems.

## Requirements

- CCE Cluster [docs](https://docs.otc.t-systems.com/cloud-container-engine/umn/clusters/creating_a_cluster/creating_a_cce_standard_turbo_cluster.html)
- helm3 [install](https://helm.sh/docs/intro/install/)
- helmfile [install](https://github.com/helmfile/helmfile)

## Deployment Steps

### Modify default configuration

- Default k8s namespace is `sre`. You can modify this in the `helmfile.yaml`
- By default 20Gi PVC (SAS EVS) will be allocated for Grafana and Prometheus. You can modify this in the `values.yaml`

```sh
helmfile sync
```

## Accessing Grafana

- Getting the `admin` password
```sh
kubectl get secret --namespace sre prometheus-stack-grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo
```
- Create port-forward pointing to Grafana ( note: this will use the kube-api bandwidth(EIP) )
```sh
kubectl port-forward svc/prometheus-stack-grafana 8080:80 -nsre
```
- From your browser you should be able to access Grafana via http://localhost:8080

## Uninstall

```sh
helmfile destroy
kubectl delete pvc --all -n ${namespace}
```
