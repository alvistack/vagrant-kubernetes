# Docker Image Packaging for Ubuntu

## 20.04.1-XalvistackY - TBC

### Major Changes

## 20.04.1-4alvistack7 - 2020-10-14

### Major Changes

  - Refine Molecule matrix

## 20.04.1-4alvistack2 - 2020-08-26

### Major Changes

  - Upgrade minimal Ansible Lint support to 4.3.2
  - Install SQLite, MariaDB and PostgreSQL with Role
  - Upgrade Travis CI test as Ubuntu Focal based
  - Upgrade minimal Ansible support to 2.10.0
  - Remove Ubuntu 19.10 support

## 20.04-4alvistack4 - 2020-06-10

### Major Changes

  - Revamp `create`, `side_effect`, `verify` and `destroy` logic
  - Replace `tini` with `catatonit`
  - Rename `post_tasks.yml` as `side_effect.yml`
  - Add Ubuntu 20.04 support
  - Remove Ubuntu 16.04 support

## 18.04.4-4alvistack4 - 2020-03-05

### Major Changes

  - Revamp with Molecule and `docker commit`
  - Consolidate molecule tests into `default` (noop)
  - Hotfix for systemd
  - Replace `duplicity` with `restic`
  - Add Ubuntu 19.10 support

## 18.04.3-alvistack1 - 2020-01-15

### Major Changes

  - Replace `dumb-init` with `tini`, as like as `docker --init`
  - Replace `java` with `openjdk`
  - Replace `nodejs` with `node`
  - Include release specific vars and tasks

## 18.04.3-2alvistack3 - 2019-11-05

### Major Changes

  - Upgrade minimal Ansible support to 2.9.0
  - Upgrade Travis CI test as Ubuntu Bionic based
  - Default with Python 3
  - Hotfix for en\_US.utf8 locale
  - Prepend executable if command starts with an option
  - Improve `ENTRYPOINT` and `CMD`

## 18.04.2-0alvistack8 - 2019-05-20

### Major Changes

  - Bugfix "Build times out because no output was received"
  - Upgrade minimal Ansible support to 2.8.0

## 18.04.2-0alvistack6 - 2019-04-15

### Major Changes

  - Porting to Molecule based
  - Add rclone support

## 18.04.1-0alvistack7 - 2018-12-06

### Major Changes

  - Add CVS, SVN, GIT, Mercurial and Perforce support
  - Replace Oracle Java JDK with OpenJDK
  - Upgrade Node.js version

## 18.04.1-0alvistack4 - 2018-11-20

### Major Changes

  - Deploy with roles in master branch
  - CI with ansible-lint
  - Add /root/.ssh/config
  - Set correct permission for /root/.ssh during bootup

## 18.04.1-0alvistack3 - 2018-11-09

### Major Changes

  - Skip container re-bootstrap in background during bootup
  - Preinstall with PHP, Node.js and Java

## 18.04.1-0alvistack1 - 2018-10-29

  - Ubuntu 16.04/18.04 based
  - Handle ENTRYPOINT with dumb-init
  - Handle `CMD` with SSHD
  - Self initialize with Ansible, by dogfooding with Ansible Playbook
