# Installation with Helm

Quick start instructions for the setup and configuration of azuredisk CSI driver using Helm.

Choose one of the following two mutually exclusive options described below.

## Option#1: Install with Helm via `helm template`

```shell
$ helm template charts/azuredisk-csi-driver --name azuredisk-csi-driver --namespace kube-system > $HOME/azuredisk-csi-driver.yaml
$ kubectl apply -f $HOME/azuredisk-csi-driver.yaml
```

## Option#2: Install with Helm and Tiller via `helm install`

This option need to install [Tiller](https://github.com/kubernetes/helm/blob/master/docs/architecture.md#components), please see [Using Helm](https://helm.sh/docs/using_helm/#example-service-account-with-cluster-admin-role) for more information.

```shell
$ helm install charts/azuredisk-csi-driver --name azuredisk-csi-driver --namespace kube-system
```

## Uninstall

- For option#1, uninstall using `kubectl`:

```shell
$ kubectl delete -f $HOME/azuredisk-csi-driver.yaml
```

- For option#2, uninstall using `helm`:

```shell
$ helm delete --purge azuredisk-csi-driver
```
