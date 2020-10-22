# Vagrant Box Packaging for Kubernetes

[![Travis](https://img.shields.io/travis/com/alvistack/vagrant-kubernetes.svg)](https://travis-ci.com/alvistack/vagrant-kubernetes)
[![GitHub release](https://img.shields.io/github/release/alvistack/vagrant-kubernetes.svg)](https://github.com/alvistack/vagrant-kubernetes/releases)
[![GitHub license](https://img.shields.io/github/license/alvistack/vagrant-kubernetes.svg)](https://github.com/alvistack/vagrant-kubernetes/blob/master/LICENSE)
[![Vagrant Box](https://img.shields.io/badge/vagrant-alvistack/kubernetes-blue.svg)](https://app.vagrantup.com/alvistack/boxes/kubernetes)

Kubernetes (K8s) is an open-source system for automating deployment, scaling, and management of containerized applications.

Learn more about Kubernetes: <https://kubernetes.io/>

## Supported Tags and Respective `Vagrantfile` Links

  - [`1.19`, `latest`](https://github.com/alvistack/vagrant-kubernetes/blob/master/molecule/1.19/Vagrantfile.j2)
  - [`1.18`](https://github.com/alvistack/vagrant-kubernetes/blob/master/molecule/1.18/Vagrantfile.j2)

## Overview

This Vagrant box makes it easy to get an instance of Kubernetes up and running.

Based on [Roboxes Vagrant Box](https://roboxes.org/) with:

  - Ubuntu 20.04 based
  - Base box running by [Vagrant Libvirt Provider](https://github.com/vagrant-libvirt/vagrant-libvirt)
  - Provision by [Ansible](https://www.ansible.com/) and [Molecule Vagrant Plugin](https://github.com/ansible-community/molecule-vagrant)

### Quick Start

### Bootstrap Vagrant and Libvirt

Start by cloning the repository, checkout the corresponding branch, then bootstrap Vagrant and Libvirt with provided helper script:

    # GIT clone the development branch
    git clone --branch develop https://github.com/alvistack/vagrant-kubernetes
    cd vagrant-kubernetes
    
    # Bootstrap Vagrant and Libvirt
    ./scripts/bootstrap-vagrant.sh

### Start Vagrant Box

How to use this box with Vagrant:

    # Initializes the current directory to be a Vagrant environment
    vagrant init alvistack/kubernetes
    
    # Creates and configures guest machines
    vagrant up

## Versioning

### `alvistack/kubernetes:<version>`

The version tags are rolling release rebuild by [Travis](https://travis-ci.com/alvistack/vagrant-kubernetes) in weekly basis. Thus using these tags will ensure you are running the latest packages provided by the base image project.

## License

  - Code released under [Apache License 2.0](LICENSE)
  - Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

## Author Information

  - Wong Hoi Sing Edison
      - <https://twitter.com/hswong3i>
      - <https://github.com/hswong3i>
