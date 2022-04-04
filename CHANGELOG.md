# Vagrant Box Packaging for Kubernetes

## YYYYMMDD.Y.Z - TBC

### Major Changes

  - Support Fedora 36
  - Support Ubuntu 22.04
  - Support Ansible community package 5.5.0
  - Remove Kubernetes 1.20 suport
  - Support Ansible community package 5.4.0

## 20220211.1.1 - 2022-02-11

### Major Changes

  - Remove Ubuntu 21.04 support
  - Skip package upgrade before running molecule

## 20211231.1.3 - 2021-12-31

### Major Changes

  - Support Fedora Rawhide
  - Support Debian Testing
  - Remove openSUSE Leap 15.2 support
  - Upgrade minimal Ansible community package support to 4.10
  - Support Kubernetes 1.23
  - Support Kubernetes 1.22

## 20211020.1.1 - 2021-10-20

### Major Changes

  - Install dependencies with package manager
  - Upgrade minimal Ansible community package support to 4.7.0
  - Rename prefix with `kube_`

## 20210718.1.1 - 2021-07-18

### Major Changes

  - Upgrade minimal Ansible community package support to 4.2.0
  - Support Kubernetes 1.21
  - Support Kubernetes 1.20
  - Support Kubernetes 1.19
  - Revamp with Packer

## 1.19.3-4alvistack1 - 2020-10-23

  - Ubuntu 18.04/20.04 based
  - Base box running by [Vagrant Libvirt Provider](https://github.com/vagrant-libvirt/vagrant-libvirt)
  - Provision by [Ansible](https://www.ansible.com/) and [Molecule Vagrant Plugin](https://github.com/ansible-community/molecule-vagrant)
