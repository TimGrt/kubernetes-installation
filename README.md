# Kubernetes Installation with kubeadm
Ansible Playbooks to deploy different Kubernetes cluster distributions, originally intended to be installed on Raspberry Pi's.

[![Ansible Lint](https://github.com/TimGrt/kubernetes-installation/actions/workflows/ci.yml/badge.svg)](https://github.com/TimGrt/kubernetes-installation/actions/workflows/ci.yml) [![CodeFactor](https://www.codefactor.io/repository/github/timgrt/kubernetes-installation/badge)](https://www.codefactor.io/repository/github/timgrt/kubernetes-installation)

The following Kubernetes distributions can be deployed:
* K8s
* K3s
* minikube

## Requirements
Minimum Ansible requirements:

* ansible-base (2.10.0 or higher)

**or**

* ansible-core (2.11.0 or higher)

The following Ansible Collections are necessary:
* ansible.posix
* community.general
* community.kubernetes

Missing collections can be installed with the provided `requirements.yml` file.
```bash
ansible-galaxy collection install -r requirements.yml
```

The target nodes need CentOS 7 as the operating system.   
I prepare my Pi cluster with the playbook from this repository: https://github.com/TimGrt/prepare-rpi-hosts

## Execution
Adjust the inventory file.  

Execute playbook to install K8s:
```bash
ansible-playbook -i hosts k8s-install.yml
```

Execute playbook to install K3s:
```bash
ansible-playbook -i hosts k3s-install.yml
```

Execute playbook to install minikube:
```bash
ansible-playbook -i hosts minikube.yml
```

## Author
Created 2020 by Tim Grützmacher