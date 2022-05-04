# Vagrant Box Packaging for Kubernetes

<img src="/alvistack.svg" width="75" alt="AlviStack">

[![Gitlab pipeline status](https://img.shields.io/gitlab/pipeline/alvistack/vagrant-kubernetes/master)](https://gitlab.com/alvistack/vagrant-kubernetes/-/pipelines)
[![GitHub tag](https://img.shields.io/github/tag/alvistack/vagrant-kubernetes.svg)](https://github.com/alvistack/vagrant-kubernetes/tags)
[![GitHub license](https://img.shields.io/github/license/alvistack/vagrant-kubernetes.svg)](https://github.com/alvistack/vagrant-kubernetes/blob/master/LICENSE) -[![Vagrant Box download](https://img.shields.io/badge/dynamic/json?label=alvistack%2Fkubernetes-1.24&query=%24.boxes%5B%3A1%5D.downloads&url=https%3A%2F%2Fapp.vagrantup.com%2Fapi%2Fv1%2Fsearch%3Fq%3Dalvistack%2Fkubernetes-1.24)](https://app.vagrantup.com/alvistack/boxes/kubernetes-1.24)

Kubernetes (K8s) is an open-source system for automating deployment, scaling, and management of containerized applications.

Learn more about Kubernetes: <https://kubernetes.io/>

## Supported Boxes and Respective Packer Template Links

  - [`alvistack/kubernetes-1.24`](https://app.vagrantup.com/alvistack/boxes/kubernetes-1.24)
      - [`libvirt`](https://github.com/alvistack/vagrant-kubernetes/blob/master/packer/libvirt-1.24/packer.json)
      - [`virtualbox`](https://github.com/alvistack/vagrant-kubernetes/blob/master/packer/virtualbox-1.24/packer.json)
  - [`alvistack/kubernetes-1.23`](https://app.vagrantup.com/alvistack/boxes/kubernetes-1.23)
      - [`libvirt`](https://github.com/alvistack/vagrant-kubernetes/blob/master/packer/libvirt-1.23/packer.json)
      - [`virtualbox`](https://github.com/alvistack/vagrant-kubernetes/blob/master/packer/virtualbox-1.23/packer.json)
  - [`alvistack/kubernetes-1.22`](https://app.vagrantup.com/alvistack/boxes/kubernetes-1.22)
      - [`libvirt`](https://github.com/alvistack/vagrant-kubernetes/blob/master/packer/libvirt-1.22/packer.json)
      - [`virtualbox`](https://github.com/alvistack/vagrant-kubernetes/blob/master/packer/virtualbox-1.22/packer.json)

## Overview

  - Packaging with [Packer](https://www.packer.io/)
  - Support [Vagrant](https://www.vagrantup.com/) as default [Kubernetes custom executor](https://docs.gitlab.com/runner/executors/README.html)
  - Support [Libvirt](https://libvirt.org/) with [vagrant-libvirt](https://github.com/vagrant-libvirt/vagrant-libvirt)
  - Support [VirtualBox](https://www.virtualbox.org/)
  - Support [Docker](https://www.docker.com/)

### Quick Start

Once you have [Vagrant](https://www.vagrantup.com/docs/installation) and [VirtaulBox](https://www.virtualbox.org/) installed, run the following commands under your [project directory](https://learn.hashicorp.com/tutorials/vagrant/getting-started-project-setup?in=vagrant/getting-started):

    # Initialize Vagrant
    cat > Vagrantfile <<-EOF
    Vagrant.configure("2") do |config|
      config.vm.hostname = "kubernetes-1.24"
      config.vm.box = "alvistack/kubernetes-1.24"
    
      config.vm.provider :libvirt do |libvirt|
        libvirt.cpu_mode = "host-passthrough"
        libvirt.cpus = 2
        libvirt.disk_bus = "virtio"
        libvirt.disk_driver :cache => "writeback"
        libvirt.driver = "kvm"
        libvirt.memory = 8192
        libvirt.memorybacking :access, :mode => "shared"
        libvirt.nested = true
        libvirt.nic_model_type = "virtio"
        libvirt.storage :file, bus: "virtio", cache: "writeback"
        libvirt.video_type = "virtio"
      end
    
      config.vm.provider :virtualbox do |virtualbox|
        virtualbox.cpus = 2
        virtualbox.memory = 8192
        virtualbox.customize ["modifyvm", :id, "--cpu-profile", "host"]
        virtualbox.customize ["modifyvm", :id, "--nested-hw-virt", "on"]
      end
    end
    EOF
    
    # Start the virtual machine
    vagrant up
    
    # SSH into this machine
    vagrant ssh
    
    # Terminate the virtual machine
    vagrant destroy --force

## Versioning

### `YYYYMMDD.Y.Z`

Release tags could be find from [GitHub Release](https://github.com/alvistack/vagrant-kubernetes/tags) of this repository. Thus using these tags will ensure you are running the most up to date stable version of this image.

### `YYYYMMDD.0.0`

Version tags ended with `.0.0` are rolling release rebuild by [GitLab pipeline](https://gitlab.com/alvistack/vagrant-kubernetes/-/pipelines) in weekly basis. Thus using these tags will ensure you are running the latest packages provided by the base image project.

## License

  - Code released under [Apache License 2.0](LICENSE)
  - Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

## Author Information

  - Wong Hoi Sing Edison
      - <https://twitter.com/hswong3i>
      - <https://github.com/hswong3i>
