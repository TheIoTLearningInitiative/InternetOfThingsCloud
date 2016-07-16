# Getting Started

- [Intel 01 OpenStack](https://01.org/openstack)

# Public Clouds on the Marketplace

[OpenStack Marketplace](https://www.openstack.org/marketplace/)

## DevStack - an OpenStack Community Production, Quick Start

```sh
root@jessie:~# apt-get install sudo
...
Setting up sudo (1.8.10p3-1+deb8u3) ...
root@jessie:~# visudo
...
stack  ALL=(ALL:ALL) ALL
...
root@jessie:~# visudo
xe1gyq@jessie:~$ sudo apt-get remove python3
xe1gyq@jessie:~$ sudo apt-get remove python
xe1gyq@jessie:~$ sudo apt-get autoremove
xe1gyq@jessie:~$ sudo apt-get install python3.4 python3.4-dev
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
xe1gyq@jessie:~/openstack/devstack$ ./clean.sh
xe1gyq@jessie:~/openstack/devstack$ ls
clean.sh      exerciserc   files             gate         LICENSE          pkg           setup.cfg  tests
data          exercises    functions         HACKING.rst  MAINTAINERS.rst  README.md     setup.py   tools
doc           exercise.sh  functions-common  inc          Makefile         run_tests.sh  stackrc    tox.ini
driver_certs  extras.d     FUTURE.rst        lib          openrc           samples       stack.sh   unstack.sh
xe1gyq@jessie:~/openstack/devstack$ ./stack.sh
...
ENTER A PASSWORD TO USE FOR THE DATABASE.
ENTER A PASSWORD TO USE FOR RABBIT.
ENTER A SERVICE_PASSWORD TO USE FOR THE SERVICE AUTHENTICATION.
ENTER A PASSWORD TO USE FOR HORIZON AND KEYSTONE (20 CHARS OR LESS).
...
This is your host IP address: 192.168.1.70
This is your host IPv6 address: ::1
Horizon is now available at http://192.168.1.70/dashboard
Keystone is serving at http://192.168.1.70:5000/
The default users are: admin and demo
The password: 
2016-03-23 18:07:45.117 | set lvm.conf device global_filter to: global_filter = [ "a|loop0|", "a|loop1|", "r|.*|" ] # from devstack
2016-03-23 18:07:45.192 | stack.sh completed in 2446 seconds.
xe1gyq@jessie:~/openstack/devstack$ devstack/tools/create-stack-user.sh
```

## DevStack - an OpenStack Community Production, Quick Start, Error

```sh
xe1gyq@jessie:~/openstack/devstack$ ./stack.sh
...
ENTER A PASSWORD TO USE FOR THE DATABASE.
ENTER A PASSWORD TO USE FOR RABBIT.
ENTER A SERVICE_PASSWORD TO USE FOR THE SERVICE AUTHENTICATION.
ENTER A PASSWORD TO USE FOR HORIZON AND KEYSTONE (20 CHARS OR LESS).
...
Error on exit
./stack.sh: line 488: generate-subunit: command not found

xe1gyq@jessie:~/openstack$ devstack/tools/create-stack-user.sh
xe1gyq@jessie:~/openstack$ su stack
xe1gyq@jessie:~/openstack/devstack$ sudo pip install -U os-testr
...
xe1gyq@jessie:~/openstack/devstack$ ./stack.sh
xe1gyq@jessie:~/openstack/devstack/$ wget https://pypi.python.org/packages/source/c/cffi/cffi-0.8.6.tar.gz#md5=474b5a68299a6f05009171de1dc91be6
xe1gyq@jessie:~/openstack/devstack/cffi-1.5.2$ tar xvf cffi-0.8.6.tar.gz
xe1gyq@jessie:~/openstack/devstack/cffi-1.5.2$ cd cffi-0.8.6
xe1gyq@jessie:~/openstack/devstack/cffi-1.5.2$ sudo python setup.py install
xe1gyq@jessie:~/openstack/devstack/cffi-1.5.2$ cd ..

```
