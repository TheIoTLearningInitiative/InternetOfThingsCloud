# Nova

- [All About Nova-Agent (well, on linux that is)](http://www.syntheticworks.com/rackspace-cloud/linux-rackspace-cloud/all-about-nova-agent-linux/)

# IPs

```
192.168.50.61 Abraham
192.168.50.62 Abraham
```

# Log In


# Host Controller

```sh
stack@osic-devstack-27:~$ ifconfig
br-ex     Link encap:Ethernet  HWaddr 2e:99:7d:d9:93:48
          inet addr:172.24.4.1  Bcast:0.0.0.0  Mask:255.255.255.0
          inet6 addr: fe80::7c22:57ff:fedf:2fd1/64 Scope:Link
          inet6 addr: 2001:db8::2/64 Scope:Global
          UP BROADCAST RUNNING  MTU:1500  Metric:1
          RX packets:23 errors:0 dropped:0 overruns:0 frame:0
          TX packets:13 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:1674 (1.6 KB)  TX bytes:1166 (1.1 KB)

br-int    Link encap:Ethernet  HWaddr 9a:8b:6e:27:2e:45
          inet6 addr: fe80::e8b0:5aff:feca:8cef/64 Scope:Link
          UP BROADCAST RUNNING  MTU:1500  Metric:1
          RX packets:3682 errors:0 dropped:0 overruns:0 frame:0
          TX packets:10 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:433508 (433.5 KB)  TX bytes:828 (828.0 B)

br-tun    Link encap:Ethernet  HWaddr a2:a5:35:e1:e5:43
          inet6 addr: fe80::dc42:82ff:fe41:1b0f/64 Scope:Link
          UP BROADCAST RUNNING  MTU:1500  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:10 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:0 (0.0 B)  TX bytes:828 (828.0 B)

eth0      Link encap:Ethernet  HWaddr fa:16:3e:7e:21:e6
          inet addr:192.168.50.61  Bcast:192.168.50.255  Mask:255.255.255.0
          inet6 addr: fe80::f816:3eff:fe7e:21e6/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:532519 errors:0 dropped:0 overruns:0 frame:0
          TX packets:203187 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:780741335 (780.7 MB)  TX bytes:14509318 (14.5 MB)

lo        Link encap:Local Loopback
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:65536  Metric:1
          RX packets:8031481 errors:0 dropped:0 overruns:0 frame:0
          TX packets:8031481 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:2216847350 (2.2 GB)  TX bytes:2216847350 (2.2 GB)

virbr0    Link encap:Ethernet  HWaddr c6:5a:f3:b5:be:2c
          inet addr:192.168.122.1  Bcast:192.168.122.255  Mask:255.255.255.0
          UP BROADCAST MULTICAST  MTU:1500  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:0 (0.0 B)  TX bytes:0 (0.0 B)

stack@osic-devstack-27:~$ 
```


# Compute

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
stack@osic-devstack-36:~$ ifconfig
br-ex     Link encap:Ethernet  HWaddr 46:6b:1a:89:17:41
          inet addr:172.24.4.1  Bcast:0.0.0.0  Mask:255.255.255.0
          inet6 addr: fe80::5cff:39ff:fe2d:4b5b/64 Scope:Link
          inet6 addr: 2001:db8::2/64 Scope:Global
          UP BROADCAST RUNNING  MTU:1500  Metric:1
          RX packets:23 errors:0 dropped:0 overruns:0 frame:0
          TX packets:13 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:1674 (1.6 KB)  TX bytes:1166 (1.1 KB)

br-int    Link encap:Ethernet  HWaddr 3a:24:ec:74:4c:43
          inet6 addr: fe80::24bc:33ff:fe95:c53a/64 Scope:Link
          UP BROADCAST RUNNING  MTU:1500  Metric:1
          RX packets:3677 errors:0 dropped:0 overruns:0 frame:0
          TX packets:10 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:432918 (432.9 KB)  TX bytes:828 (828.0 B)

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

```sh
stack@osic-devstack-36:~$ ls
devstack  start.sh
stack@osic-devstack-36:~$ cd /etc/nova/
stack@osic-devstack-36:/etc/nova$ ls
api-paste.ini  nova-dhcpbridge.conf  rootwrap.conf
nova.conf      policy.json           rootwrap.d
stack@osic-devstack-36:/etc/nova$
```

```sh
stack@osic-devstack-36:/etc/nova$ nano nova.conf
```

```
[DEFAULT]
vif_plugging_timeout = 300
...
transport_url = rabbit://stackrabbit:secure@192.168.50.62:5672/
...
```