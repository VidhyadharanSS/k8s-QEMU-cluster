k8s-QEMU-cluster

This repository provides a fully automated, QEMU-based multi-node Kubernetes cluster setup using `libvirt`, `Vagrant`, and `kubeadm`. It is designed as a local infrastructure lab for low-level systems and kernel experimentation, enabling complete observability and control over virtual machine internals without reliance on Docker Desktop or managed hypervisors.

Key Features

- Bare-metal style cluster provisioning on local machines using QEMU/KVM.
- Automated VM and Kubernetes control-plane setup via Vagrant and shell scripts.
- Modular provisioning with `common.sh`, `master.sh`, and `node.sh`.
- Custom `systemd` units to bridge TAP interfaces for deterministic networking.
- Ingress and CNI plugins configured via declarative YAML.
- Fully reproducible infrastructure with zero manual intervention post-init.

Architecture Overview

The cluster consists of:

- 1 Master node (control plane)
- 2+ Worker nodes (can be extended)
- Bridged virtual network over TAP
- Ingress controller for internal service routing

