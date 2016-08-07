# i386

```sh
xe1gyq@jessie:~$ sudo apt-get remove python3
xe1gyq@jessie:~$ sudo apt-get remove python
xe1gyq@jessie:~$ sudo apt-get autoremove
xe1gyq@jessie:~$ sudo apt-get install python3.4 python3.4-dev
```

```sh
root@jessie:~# apt-get install sudo
...
Setting up sudo (1.8.10p3-1+deb8u3) ...
root@jessie:~# visudo
...
stack ALL=(ALL) NOPASSWD: ALL
...
root@jessie:~# su stack
stack@jessie:/root$ cd
stack@jessie:~$ 
```

```sh
xe1gyq@jessie:~$ git clone git://github.com/openstack-dev/devstack.git
Cloning into 'devstack'...
remote: Counting objects: 33001, done.
remote: Total 33001 (delta 0), reused 0 (delta 0), pack-reused 33000
Receiving objects: 100% (33001/33001), 12.09 MiB | 495.00 KiB/s, done.
Resolving deltas: 100% (22813/22813), done.
Checking connectivity... done.
xe1gyq@jessie:~$  
```

```sh
xe1gyq@jessie:~/openstack$ cd devstack
stack@jessie:~$ cd devstack
stack@jessie:~/devstack$ ls
clean.sh     files	       lib		run_tests.sh  tools
data	     functions	       LICENSE		samples       tox.ini
doc	     functions-common  MAINTAINERS.rst	setup.cfg     unstack.sh
exerciserc   FUTURE.rst        Makefile		setup.py
exercises    gate	       openrc		stackrc
exercise.sh  HACKING.rst       pkg		stack.sh
extras.d     inc	       README.md	tests
stack@jessie:~/devstack$ 
```

```sh
stack@jessie:~/devstack$ cp samples/local.conf .
stack@jessie:~/devstack$ nano local.conf 
```

```sh
xe1gyq@jessie:~/openstack/devstack$ ./clean.sh
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
```

# Laboratory

```sh
xe1gyq@jessie:~/openstack/devstack$ openstack help
```

```sh
xe1gyq@jessie:~/openstack/devstack$ ls /opt/
stack
xe1gyq@jessie:~/openstack/devstack$ ls /opt/stack/
cinder  data  devstack.subunit  glance  horizon  keystone  logs  neutron  noVNC  nova  requirements  status  tempest
xe1gyq@jessie:~/openstack/devstack$ 
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

```sh
top - 17:37:28 up 3 days, 19:21,  1 user,  load average: 0.45, 0.38, 0.40
Tasks: 214 total,   1 running, 213 sleeping,   0 stopped,   0 zombie
%Cpu(s): 14.2 us,  1.7 sy,  0.0 ni, 84.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
KiB Mem:   8176796 total,  7102060 used,  1074736 free,   163700 buffers
KiB Swap:  2097148 total,        0 used,  2097148 free.  3005672 cached Mem

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU %MEM     TIME+ COMMAND
21697 stack     20   0   34392   7764   2812 S  19.5  0.1  68:14.94 dstat
31449 stack     20   0  221884  70348   6376 S  13.0  0.9 558:58.23 neutron-openvsw
31681 stack     20   0  207812  56280   6388 S  13.0  0.7 553:33.08 neutron-dhcp-ag
31913 stack     20   0  208088  56580   6380 S  13.0  0.7 543:29.51 neutron-l3-agen
    7 root      20   0       0      0      0 S   6.5  0.0  14:24.10 rcu_sched
30749 stack     20   0  273624 114224   6584 S   6.5  1.4  30:18.54 nova-api
31231 stack     20   0  257404  96116   2688 S   6.5  1.2  97:24.07 neutron-server
    1 root      20   0   33596   2916   1476 S   0.0  0.0   0:00.97 init
    2 root      20   0       0      0      0 S   0.0  0.0   0:00.04 kthreadd
    3 root      20   0       0      0      0 S   0.0  0.0   0:01.79 ksoftirqd/0
    4 root      20   0       0      0      0 S   0.0  0.0   0:00.00 kworker/0:0
    5 root       0 -20       0      0      0 S   0.0  0.0   0:00.00 kworker/0:0H
    8 root      20   0       0      0      0 S   0.0  0.0   2:07.14 rcuos/0
    9 root      20   0       0      0      0 S   0.0  0.0   2:04.55 rcuos/1
   10 root      20   0       0      0      0 S   0.0  0.0   1:58.19 rcuos/2
   11 root      20   0       0      0      0 S   0.0  0.0   1:47.49 rcuos/3
   12 root      20   0       0      0      0 S   0.0  0.0   0:00.00 rcu_bh
   13 root      20   0       0      0      0 S   0.0  0.0   0:00.00 rcuob/0
   14 root      20   0       0      0      0 S   0.0  0.0   0:00.00 rcuob/1
   15 root      20   0       0      0      0 S   0.0  0.0   0:00.00 rcuob/2
   16 root      20   0       0      0      0 S   0.0  0.0   0:00.00 rcuob/3
   17 root      rt   0       0      0      0 S   0.0  0.0   0:01.35 migration/0
   18 root      rt   0       0      0      0 S   0.0  0.0   0:01.13 watchdog/0
   19 root      rt   0       0      0      0 S   0.0  0.0   0:01.04 watchdog/1
   20 root      rt   0       0      0      0 S   0.0  0.0   0:01.54 migration/1
   21 root      20   0       0      0      0 S   0.0  0.0   0:00.83 ksoftirqd/1
   22 root      20   0       0      0      0 S   0.0  0.0   0:00.00 kworker/1:0
   23 root       0 -20       0      0      0 S   0.0  0.0   0:00.00 kworker/1:0H
```
