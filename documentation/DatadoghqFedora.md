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

