# Kubernetes Vagrant Cluster

A ready-to-run **multi-node Kubernetes cluster** using **Vagrant** and **VirtualBox**.  
Designed for **Windows hosts** to allow anyone to spin up a Kubernetes cluster quickly!

---

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Quick Start](#quick-start)

---

## Overview

This repo provides a fully automated **multi-node Kubernetes environment** using Vagrant and VirtualBox:

- 1 Control Plane (`controlplane`)
- 2 Worker Nodes (`node01`, `node02`)
- Automatic setup of `/etc/hosts` and DNS
- Provisioning scripts for SSH, tmux, vim, and optional kernel tweaks
- Designed to be **fast to bring up** on Windows hosts

---

## Prerequisites

- **Windows 10/11** (or Windows Server with WSL disabled)
- **Vagrant** ≥ 2.x: [https://www.vagrantup.com/downloads](https://www.vagrantup.com/downloads)
- **VirtualBox** ≥ 6.x: [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)
- Internet connection to download the Ubuntu box

Optional but recommended:

- Git Bash, PowerShell, or Windows Terminal for running commands

---

## Quick Start

Clone the repo, start the cluster and choose a CNI - below are Calico (supports Network Policy objects) and Flannel (does not support) or any other CNI of your choice -- happy kubectling!:

```bash
git clone https://github.com/<your-username>/k8s-vagrant-cluster.git
cd k8s-vagrant-cluster
vagrant up
vagrant ssh controlplane
```
Follow the guide to setup your cluster with Kubeadm and instal a CNI, Calico support NP objects, while Flannel does not!:

https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/

kubectl apply -f https://docs.projectcalico.org/manifests/calico.yaml
kubectl apply -f https://raw.githubusercontent.com/flannel-io/flannel/master/Documentation/kube-flannel.yml

Happy kubectling!
