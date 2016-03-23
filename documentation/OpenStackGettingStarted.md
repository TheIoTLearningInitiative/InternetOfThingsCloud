Getting Started
==

> DevStack
> > An OpenStack Community Production

> > DevStack's mission is to provide and maintain tools used for the installation of the central OpenStack services from source (git repository master, or specific branches) suitable for development and operational testing. It also demonstrates and documents examples of configuring and running services as well as command line client usage. [DevStack](https://wiki.openstack.org/wiki/DevStack)

- [Open Stack Wiki](https://wiki.openstack.org/wiki/Getting_Started)
- [Open Stack Homepage How To Get Started](https://www.openstack.org/software/start/)

```sh
xe1gyq@jessie:~$ mkdir openstack
xe1gyq@jessie:~$ cd openstack/
xe1gyq@jessie:~/openstack$ git clone git://github.com/openstack-dev/devstack.git
Cloning into 'devstack'...
remote: Counting objects: 33001, done.
remote: Total 33001 (delta 0), reused 0 (delta 0), pack-reused 33000
Receiving objects: 100% (33001/33001), 12.09 MiB | 495.00 KiB/s, done.
Resolving deltas: 100% (22813/22813), done.
Checking connectivity... done.
xe1gyq@jessie:~/openstack$ cd devstack
xe1gyq@jessie:~/openstack/devstack$ ./stack.sh
```
