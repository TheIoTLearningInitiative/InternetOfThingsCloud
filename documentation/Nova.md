# Nova

- [All About Nova-Agent (well, on linux that is)](http://www.syntheticworks.com/rackspace-cloud/linux-rackspace-cloud/all-about-nova-agent-linux/)

```sh
Welcome to Ubuntu 14.04.4 LTS (GNU/Linux 3.13.0-92-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

  System information as of Tue Jul 19 16:29:33 UTC 2016

  System load:  0.33              Users logged in:       0
  Usage of /:   3.4% of 94.46GB   IP address for eth0:   192.168.50.62
  Memory usage: 42%               IP address for virbr0: 192.168.122.1
  Swap usage:   0%                IP address for br-ex:  172.24.4.1
  Processes:    213

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

3 packages can be updated.
3 updates are security updates.


Last login: Tue Jul 19 16:29:34 2016 from 192.168.50.15
stack@osic-devstack-36:~$ 
```

```sh
stack@osic-devstack-27:~$ ls
devstack  start.sh
stack@osic-devstack-27:~$ cd /etc/nova/
stack@osic-devstack-27:/etc/nova$ ls
api-paste.ini  nova-dhcpbridge.conf  rootwrap.conf
nova.conf      policy.json           rootwr
```

# Host 1

```sh
br-tun    Link encap:Ethernet  HWaddr 5e:04:9c:38:9e:4c
          inet6 addr: fe80::a4c6:6ff:fe84:7498/64 Scope:Link
          UP BROADCAST RUNNING  MTU:1500  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:10 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:0 (0.0 B)  TX bytes:828 (828.0 B)

eth0      Link encap:Ethernet  HWaddr fa:16:3e:17:36:7e
          inet addr:192.168.50.62  Bcast:192.168.50.255  Mask:255.255.255.0
          inet6 addr: fe80::f816:3eff:fe17:367e/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:530351 errors:0 dropped:0 overruns:0 frame:0
          TX packets:190592 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:781595878 (781.5 MB)  TX bytes:13716587 (13.7 MB)

lo        Link encap:Local Loopback
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:65536  Metric:1
          RX packets:8029919 errors:0 dropped:0 overruns:0 frame:0
          TX packets:8029919 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:2215290080 (2.2 GB)  TX bytes:2215290080 (2.2 GB)

virbr0    Link encap:Ethernet  HWaddr fa:dc:6c:00:f5:16
          inet addr:192.168.122.1  Bcast:192.168.122.255  Mask:255.255.255.0
          UP BROADCAST MULTICAST  MTU:1500  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:0 (0.0 B)  TX bytes:0 (0.0 B)

stack@osic-devstack-36:~$ 
```