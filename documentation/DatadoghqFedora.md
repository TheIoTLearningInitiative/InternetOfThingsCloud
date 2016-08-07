# DataDogHq Fedora

```sh
root@debiando:~# ./deploy_droplet.py openstackiando
Queueing creation of droplet 'openstackiando'...Failed to create Droplet: You specified an invalid image for Droplet creation.
Droplet fuzzy name provided. Finding droplet ID...done, 21795167 (openstackiando)
Waiting for droplet to become active..done (0s)
IP: 138.68.60.125
Run the following (in order): 
ssh root@138.68.60.125 'bash -s' < stack_setup.sh
ssh root@138.68.60.125
sudo -iu stack /usr/local/src/devstack/stack.sh
root@debiando:~# 
```

```sh
root@debiando:~# ssh root@138.68.60.125
root@138.68.60.125's password: 
Last login: Sun Aug  7 05:21:56 2016 from 198.199.98.143
[root@openstackiando ~]# 
```

```sh
[root@openstackiando ~]# yum install git
```

```sh
[root@openstackiando ~]# git clone https://git.openstack.org/openstack-dev/devstack
Cloning into 'devstack'...
remote: Counting objects: 34873, done.
remote: Compressing objects: 100% (16528/16528), done.
remote: Total 34873 (delta 24744), reused 27611 (delta 17870)
Receiving objects: 100% (34873/34873), 6.77 MiB | 9.82 MiB/s, done.
Resolving deltas: 100% (24744/24744), done.
Checking connectivity... done.
[root@openstackiando ~]# 
```

```sh
[root@openstackiando ~]# cd devstack/
[root@openstackiando devstack]# ls
clean.sh    exercise.sh       FUTURE.rst   LICENSE          README.md     stackrc   unstack.sh
data        extras.d          gate         MAINTAINERS.rst  run_tests.sh  stack.sh
doc         files             HACKING.rst  Makefile         samples       tests
exerciserc  functions         inc          openrc           setup.cfg     tools
exercises   functions-common  lib          pkg              setup.py      tox.ini
[root@openstackiando devstack]# 
```

```sh
```

```sh
```

```sh
```

```sh
```

```sh
```

```sh
```