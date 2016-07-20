# DevStack

> DevStack
> > An OpenStack Community Production

> > DevStack's mission is to provide and maintain tools used for the installation of the central OpenStack services from source (git repository master, or specific branches) suitable for development and operational testing. It also demonstrates and documents examples of configuring and running services as well as command line client usage. [DevStack](https://wiki.openstack.org/wiki/DevStack)

> With some technical skills, DevStack is a great option to install and run an OpenStack cloud on your laptop (or even inside the VM on a cloud). DevStack is ideal for potential users who want to see what the Dashboard looks like from an admin or user perspective, and OpenStack contributors wanting to test against a complete local environment.

> DevStack is a series of extensible scripts used to quickly bring up a complete OpenStack environment. It is used interactively as a development environment and as the basis for much of the OpenStack project’s functional testing. [Homepage](http://docs.openstack.org/developer/devstack/)

- [Open Stack Wiki](https://wiki.openstack.org/wiki/Getting_Started)
- [Open Stack Homepage How To Get Started](https://www.openstack.org/software/start/)

```sh
stack@osic-devstack-27:~/devstack$ ls
FUTURE.rst       Makefile   data         exercises  functions-common  local.conf    samples         stack.sh  tox.ini
HACKING.rst      README.md  doc          extras.d   gate              openrc        setup.cfg       stackrc   unstack.sh
LICENSE          accrc      exercise.sh  files      inc               pkg           setup.py        tests     userrc_early
MAINTAINERS.rst  clean.sh   exerciserc   functions  lib               run_tests.sh  stack-screenrc  tools
stack@osic-devstack-27:~/devstack$ nano openrc
```

```sh
#!/usr/bin/env bash
#
# source openrc [username] [projectname]
#
# Configure a set of credentials for $PROJECT/$USERNAME:
#   Set OS_PROJECT_NAME to override the default project 'demo'
#   Set OS_USERNAME to override the default user name 'demo'
#   Set ADMIN_PASSWORD to set the password for 'admin' and 'demo'
...
...
```