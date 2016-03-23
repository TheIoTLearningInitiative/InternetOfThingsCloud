Getting Started
==

> DevStack
> > An OpenStack Community Production

> > DevStack's mission is to provide and maintain tools used for the installation of the central OpenStack services from source (git repository master, or specific branches) suitable for development and operational testing. It also demonstrates and documents examples of configuring and running services as well as command line client usage. [DevStack](https://wiki.openstack.org/wiki/DevStack)

- [Open Stack Wiki](https://wiki.openstack.org/wiki/Getting_Started)
- [Open Stack Homepage How To Get Started](https://www.openstack.org/software/start/)

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
xe1gyq@jessie:~/openstack/devstack$ ./stack.sh
...
ENTER A PASSWORD TO USE FOR THE DATABASE.
ENTER A PASSWORD TO USE FOR RABBIT.
ENTER A SERVICE_PASSWORD TO USE FOR THE SERVICE AUTHENTICATION.
ENTER A PASSWORD TO USE FOR HORIZON AND KEYSTONE (20 CHARS OR LESS).
...
xe1gyq@jessie:~/openstack$ devstack/tools/create-stack-user.sh
```

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
