```
# Unqork Take Home Kubernetes Deployment

This repository contains Ansible playbooks and a GitHub Actions pipeline for deploying Kubernetes resources. The resources include a namespace, a ConfigMap, and a Secret. This is part of the Unqork take-home assignment.

## Table of Contents

1. [Requirements](#requirements)
2. [Usage](#usage)
3. [Modifications](#modifications)
4. [Running the Playbook](#running-the-playbook)
5. [CI/CD](#cicd)

## Requirements

- Ansible installed ([Ansible Installation Guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html))
- `kubectl` installed and configured with cluster access ([Kubectl Installation Guide](https://kubernetes.io/docs/tasks/tools/install-kubectl/))
- GitHub account ([GitHub Signup](https://github.com/join))
- GitHub Actions enabled on the repository ([GitHub Actions Docs](https://docs.github.com/en/actions))

## Usage

1. Clone this repository.
```
git clone https://github.com/yourusername/yourrepository.git
```
[Git Clone Documentation](https://git-scm.com/docs/git-clone)

2. Navigate into the repository.
```
cd yourrepository
```

3. Run the Ansible playbook.
```
ansible-playbook playbook.yml
```
[Ansible Playbook Documentation](https://docs.ansible.com/ansible/latest/user_guide/playbooks.html)

## Modifications

### Updating Kubernetes Namespace

To change the namespace from the default `steve-test`, update the `kube_namespace` in the `playbook.yml`:

```yaml
set_fact:
  kube_namespace: your-namespace
```
[Kubernetes Namespace Documentation](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/)

### Updating ConfigMap and Secret

To add or change key-value pairs in the ConfigMap or Secret, update the `data` section under the respective resource in the `playbook.yml` file.

```yaml
data:
  NEW_KEY: "new-value"
```
[Kubernetes ConfigMaps and Secrets](https://kubernetes.io/docs/concepts/configuration/)

### Providing Definitions for StatefulSet and HPA

The StatefulSet and HPA are placeholders; you'll need to provide your specific configurations under `definition`:

```yaml
definition:
  # Your StatefulSet/HPA YAML here
```
[StatefulSets](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/)
[Horizontal Pod Autoscaler](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/)

## Running the Playbook

After modifying the playbook to suit your needs, run it using:

```
ansible-playbook playbook.yml
```
[Running Ansible Playbooks](https://docs.ansible.com/ansible/latest/user_guide/playbooks.html)

## CI/CD

A GitHub Actions pipeline is set up to run this playbook automatically whenever changes are pushed to the `main` branch.
[GitHub Actions Workflow](https://docs.github.com/en/actions/learn-github-actions/introduction-to-github-actions)
```

