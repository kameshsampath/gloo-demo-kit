# Gloo Demo Kit

The template project to get started with Gloo Edge/Mesh with Ansible and Minikube

## Required tools

The demo requires the following tools, have them installed and added to `$PATH` before proceeding with the demo,

- [minikube](https://minikube.sigs.k8s.io/docs/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [kustomize](https://kubernetes-sigs.github.io/kustomize/installation/)
- [pipx](https://github.com/pypa/pipx)
- [poetry](https://python-poetry.org/)
- [yq](https://github.com/mikefarah/yq)
- [Helm](https://helm.sh/docs/intro/install/)

Optinally if you want encryption of values/secrets,

- [sops](https://github.com/mozilla/sops)
- [age](https://github.com/FiloSottile/age)

## Ansible Environment

```shell
pipx install poetry 
poetry config  virtualenvs.in-project true
```

Create Ansible pythonenv,

```shell
make shell-venv
```

Install the Ansible roles and collections that will be used during setup,

```shell
make install-roles-and-collections
```

## Kubernetes Cluster

Setup minikube cluster, install extra components and download the tools

```shell
make create-kube-clusters
```

## Deploy Gloo

Setup minikube cluster and components

```shell
make deploy-gloo
```

## Cleanup

Delete the created minikube clusters

```shell
make clean-up
```