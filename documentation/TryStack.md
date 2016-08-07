# TryStack

- [Tutorial Creating Openstack Instance In Trystack](https://edwardsamuel.wordpress.com/2014/10/25/tutorial-creating-openstack-instance-in-trystack/)

```sh
xe1gyq@jessie:~$ ssh -i cloud.key root@8.43.86.117
Enter passphrase for key 'cloud.key': 
Please login as the user "ubuntu" rather than the user "root".

Connection to 8.43.86.117 closed.
xe1gyq@jessie:~$ 
```

```
xe1gyq@jessie:~$ ssh -i cloud.key ubuntu@8.43.86.117
Enter passphrase for key 'cloud.key': 

Welcome to Ubuntu 14.04.4 LTS (GNU/Linux 3.13.0-85-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

  System information as of Sun Aug  7 06:49:50 UTC 2016

  System load:  0.22              Processes:           69
  Usage of /:   4.3% of 19.65GB   Users logged in:     0
  Memory usage: 3%                IP address for eth0: 192.168.1.4
  Swap usage:   0%

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

0 packages can be updated.
0 updates are security updates.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ubuntu@ubuntu:~$ 
```

```sh
ubuntu@ubuntu:~$ uname -a
Linux ubuntu 3.13.0-85-generic #129-Ubuntu SMP Thu Mar 17 20:50:15 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux
ubuntu@ubuntu:~$ 
```