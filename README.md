# osx-bootstrap-homebrew

The role to install Homebrew, add taps, install packages via homebrew and mac os applications via homebrew cask.

[![Build Status](https://travis-ci.org/0x4e3/osx-bootstrap-homebrew.svg?branch=master)](https://travis-ci.org/0x4e3/osx-bootstrap-homebrew)
[![GitHub license](https://img.shields.io/github/license/0x4e3/osx-bootstrap-homebrew.svg)](https://github.com/0x4e3/osx-bootstrap-homebrew/blob/master/LICENSE)

## Requirements

No.

## Role Variables

* ```homebrew_taps``` -- list of taps to add;
* ```homebrew_packages``` -- list of packages to install;
* ```homebrew_packages_with_args``` -- list of packages with some extra installation arguments;
* ```homebrew_cask_dir``` -- directory for applications installed with homebrew cask;
* ```homebrew_cask_apps``` -- list of applications to install.

## Dependencies

No.

## Example Playbook

```playbook.yml```:
```yml
---
- host: localhost
  vars_files:
    - vars/homebrew.yml
  roles:
    - 0x4e3.osx-bootstrap-homebrew
```

```vars/homebrew.yml```
```yml
---
homebrew_taps:
  - homebrew/core
  - homebrew/services
  - caskroom/cask
  - petere/postgresql

homebrew_packages:
  - cowsay

homebrew_packages_with_args:
  - name: freetds
    args: "with-msdblib,with-odbc-wide,with-unixodbc"

homebrew_cask_apps:
  - sublime-text
```
