ansible-role-rke_rancher_clusters
==================

Create a new Kubernetes Cluster with RKE and deploys Rancher on it

Requirements
------------

Only uses python and ansible.


Role Variables
--------------

```
---
rke_binary_version: v1.0.4
rke_binary_download_url: "https://github.com/rancher/rke/releases/download/{{ rke_binary_version }}/rke_linux-amd64"
rke_cluster_bin: "./rke-{{ rke_binary_version }}"
rke_cluster_kube_config: "kube_config_config-{{ inventory_hostname }}.yml"
rke_cluster_config: "config-{{ inventory_hostname }}.yml"

helm_binary_version: v3.1.1
helm_binary_download_url: "https://get.helm.sh/helm-{{ helm_binary_version }}-linux-amd64.tar.gz"
helm_binary: "./helm"
helm_home: ".helm"

kubectl_binary_version: v1.17.2
kubectl_binary_download_url: "https://storage.googleapis.com/kubernetes-release/release/{{ kubectl_binary_version }}/bin/linux/amd64/kubectl"
kubectl_binary: "./kubectl-{{ kubectl_binary_version }}"

rancher_repo: rancher-stable
rancher_repo_url: "https://releases.rancher.com/server-charts/stable"

kubernetes_version: v1.17.2-rancher1-2
rancher_version: v2.3.5

rancher_failover_ip: []

rancher_hostname: ""
rancher_admin_password: ""
rancher_admin_initial_password: admin

## Due to https://bugzilla.redhat.com/show_bug.cgi?id=1527565
rke_ssh_user: centos
rke_network_interface: eth0


# Cert Manager for Lets Encrypt Certs
certmanager_enabled: false
rancher_certmanager_version: 0.13.1
jetstack_repo: jetstack
jetstack_repo_url: https://charts.jetstack.io

# When certmanager is not enabled, make sure to to this: https://rancher.com/docs/rancher/v2.x/en/installation/options/tls-secrets/
```

Dependencies
------------

* none

License
-------

GPLv3

Author Information
------------------

* Sebastian Plattner (plattner@puzzle.ch)
