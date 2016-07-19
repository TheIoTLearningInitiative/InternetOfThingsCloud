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
$ ssh stack@192.168.50.61
stack@192.168.50.61's password:
Welcome to Ubuntu 14.04.4 LTS (GNU/Linux 3.13.0-92-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

  System information as of Tue Jul 19 16:28:06 UTC 2016

  System load:  0.18              Users logged in:       0
  Usage of /:   3.4% of 94.46GB   IP address for eth0:   192.168.50.61
  Memory usage: 42%               IP address for virbr0: 192.168.122.1
  Swap usage:   0%                IP address for br-ex:  172.24.4.1
  Processes:    213

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

3 packages can be updated.
3 updates are security updates.


Last login: Tue Jul 19 16:28:06 2016 from 192.168.50.15
stack@osic-devstack-27:~$ 
```

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

```sh
stack@osic-devstack-36:/etc/nova$ cd
stack@osic-devstack-36:~$
```

## Compute, Nova Setup Restart

```sh
stack@osic-devstack-36:~$ screen -ls
There is a screen on:
        21390.stack     (07/16/16 22:26:44)     (Attached)
1 Socket in /var/run/screen/S-stack.

stack@osic-devstack-36:~$
```

```sh
stack@osic-devstack-36:~$ screen -r
There is a screen on:
        21390.stack     (07/16/16 22:26:44)     (Attached)
There is no screen to be resumed.
stack@osic-devstack-36:~$ 
```

Somehow I removed service 16 n-cpu ... [Cannot restart services on Devstack](https://ask.openstack.org/en/question/1916/cannot-restart-services-on-devstack/)


```sh
 Num Name                                                                  Flags

   0 shell                                                                     $
   1 dstat                                                                  $(L)
   2 key                                                                    $(L)
   3 key-access                                                             $(L)
   4 g-reg                                                                  $(L)
   5 g-api                                                                  $(L)
   6 n-api                                                                  $(L)
   7 q-svc                                                                  $(L)
   8 q-agt                                                                  $(L)
   9 q-dhcp                                                                 $(L)
  10 q-l3                                                                   $(L)
  11 q-meta                                                                 $(L)
  12 n-cond                                                                 $(L)
  13 n-sch                                                                  $(L)
  14 n-novnc                                                                $(L)
  15 n-cauth                                                                $(L)
  16 n-cpu [Removed]
  17 c-api                                                                  $(L)
  18 c-sch                                                                  $(L)
```

We removed "16 n-cpu" so we needed to restart OpenStack in the node 

To dettach from the Console:

```sh
CTRL-A D
```

## OpenStack Services Enable

then we need to resinstall OpenStack using DevStack

```sh
stack@osic-devstack-36:~$ ls
devstack  start.sh
stack@osic-devstack-36:~$ cd devstack/
stack@osic-devstack-36:~/devstack$ ./unstack.sh
...
stack@osic-devstack-36:~/devstack$ ./stack.sh
...
After 5 minutes
...

=========================
DevStack Component Timing
=========================
Total runtime         527

run_process            58
test_with_retry         2
apt-get-update          8
pip_install            85
restart_apache_server  10
wait_for_service        9
apt-get                 7
=========================



This is your host IP address: 192.168.50.62
This is your host IPv6 address: ::1
Horizon is now available at http://192.168.50.62/dashboard
Keystone is serving at http://192.168.50.62/identity/
The default users are: admin and demo
The password: secure
2016-07-19 17:04:26.872 | WARNING:
2016-07-19 17:04:26.872 | Using lib/neutron-legacy is deprecated, and it will be removed in the future
2016-07-19 17:04:26.872 | stack.sh completed in 527 seconds.
stack@osic-devstack-36:~/devstack$ 
```

```sh
stack@osic-devstack-36:~/devstack$ cd /etc/nova/
stack@osic-devstack-36:/etc/nova$ nano nova.conf
```

```
stack@osic-devstack-36:/etc/nova$ screen -ls
There is a screen on:
        12067.stack     (07/19/2016 04:57:39 PM)        (Detached)
1 Socket in /var/run/screen/S-stack.

stack@osic-devstack-36:/etc/nova$

stack@osic-devstack-36:~/devstack$ sudo tail -f /var/log/apache2/horizon_error.log & echo $! >/opt/stack/status/stack/horizon.pid; fg || echo "horizon failed to start" | tee "/opt/stack/status/stack/horizon.failure"
[1] 8301
sudo tail -f /var/log/apache2/horizon_error.log
```

```
CTRL-A "
```

Select 16 n-cpu then Enter

```
  14 n-novnc                                                                $(L)
  15 n-cauth                                                                $(L)
  16 n-cpu                                                                  $(L)
  17 c-api                                                                  $(L)
  18 c-sch                                                                  $(L)
```

then Ctrl-C

```sh
n-cpu failed to start
stack@osic-devstack-36:~/devstack$ sg libvirtd '/usr/local/bin/nova-compute --config-file /etc/nova/nova.conf' & echo $! >/opt/stack/status/stack/n-cpu.pid; fg || echo "n-cpu failed to start" | tee "/opt/stack/status/stack/n-cpu.failure"
```

```sh
2016-07-19 17:09:52.765 WARNING nova.virt.libvirt.driver [req-5e81b559-8336-46e2-874f-9d9ac5bbaf4c None None] Running Nova with a QEMU version less than 1.5.3 is deprecated. The required minimum version of QEMU will be raised to 1.5.3 in the next release.
2016-07-19 17:09:52.820 WARNING nova.compute.monitors [req-5e81b559-8336-46e2-874f-9d9ac5bbaf4c None None] Excluding nova.compute.monitors.cpu monitor virt_driver. Not in the list of enabled monitors (CONF.compute_monitors).
2016-07-19 17:09:52.820 INFO nova.compute.resource_tracker [req-5e81b559-8336-46e2-874f-9d9ac5bbaf4c None None] Auditing locally available compute resources for node osic-devstack-36
2016-07-19 17:09:52.941 INFO nova.compute.resource_tracker [req-5e81b559-8336-46e2-874f-9d9ac5bbaf4c None None] Total usable vcpus: 4, total allocated vcpus: 0
2016-07-19 17:09:52.941 INFO nova.compute.resource_tracker [req-5e81b559-8336-46e2-874f-9d9ac5bbaf4c None None] Final resource view: name=osic-devstack-36 phys_ram=7985MB used_ram=512MB phys_disk=94GB used_disk=0GB total_vcpus=4 used_vcpus=0 pci_stats=[]
2016-07-19 17:09:53.000 INFO nova.compute.resource_tracker [req-5e81b559-8336-46e2-874f-9d9ac5bbaf4c None None] Compute_service record updated for osic-devstack-36:osic-devstack-36
```

then Ctrl-A D

```sh
[detached from 12067.stack]
stack@osic-devstack-36:/etc/nova$
```

# Controller

## Nova Commands

[localhost:8080/dashboard](localhost:8080/dashboard)

```sh
stack@osic-devstack-27:~$ nova flavor-list
ERROR (CommandError): You must provide a username or user ID via --os-username, --os-user-id, env[OS_USERNAME] or env[OS_USER_ID]
stack@osic-devstack-27:~$ nova boot --flavor=2 --image=0000000-0000-0000-0000-0000000000 test
```

## Source Configuration

```sh
stack@osic-devstack-27:~$ cd devstack/
stack@osic-devstack-27:~/devstack$ ls
accrc        extras.d          inc              pkg           stack-screenrc
clean.sh     files             lib              README.md     stack.sh
data         functions         LICENSE          run_tests.sh  tests
doc          functions-common  local.conf       samples       tools
exerciserc   FUTURE.rst        MAINTAINERS.rst  setup.cfg     tox.ini
exercises    gate              Makefile         setup.py      unstack.sh
exercise.sh  HACKING.rst       openrc           stackrc       userrc_early
stack@osic-devstack-27:~/devstack$ source openrc admin admin
```

```
stack@osic-devstack-27:~/devstack$ source openrc admin admin
WARNING: setting legacy OS_TENANT_NAME to support cli tools.
stack@osic-devstack-27:~/devstack$
```

## Nova Service List 

```sh
stack@osic-devstack-27:~/devstack$ nova service-list
+----+------------------+------------------+----------+---------+-------+----------------------------+-----------------+
| Id | Binary           | Host             | Zone     | Status  | State | Updated_at                 | Disabled Reason |
+----+------------------+------------------+----------+---------+-------+----------------------------+-----------------+
| 5  | nova-conductor   | osic-devstack-27 | internal | enabled | up    | 2016-07-19T17:29:16.000000 | -               |
| 7  | nova-scheduler   | osic-devstack-27 | internal | enabled | up    | 2016-07-19T17:29:20.000000 | -               |
| 8  | nova-consoleauth | osic-devstack-27 | internal | enabled | up    | 2016-07-19T17:29:20.000000 | -               |
| 9  | nova-compute     | osic-devstack-27 | nova     | enabled | up    | 2016-07-19T17:29:13.000000 | -               |
| 10 | nova-compute     | osic-devstack-36 | nova     | enabled | up    | 2016-07-19T17:29:18.000000 | -               |
+----+------------------+------------------+----------+---------+-------+----------------------------+-----------------+
stack@osic-devstack-27:~/devstack$
```

## Nova Flavor List

```sh
stack@osic-devstack-27:~/devstack$ nova flavor-list
+----+-----------+-----------+------+-----------+------+-------+-------------+-----------+
| ID | Name      | Memory_MB | Disk | Ephemeral | Swap | VCPUs | RXTX_Factor | Is_Public |
+----+-----------+-----------+------+-----------+------+-------+-------------+-----------+
| 1  | m1.tiny   | 512       | 1    | 0         |      | 1     | 1.0         | True      |
| 2  | m1.small  | 2048      | 20   | 0         |      | 1     | 1.0         | True      |
| 3  | m1.medium | 4096      | 40   | 0         |      | 2     | 1.0         | True      |
| 4  | m1.large  | 8192      | 80   | 0         |      | 4     | 1.0         | True      |
| 42 | m1.nano   | 64        | 0    | 0         |      | 1     | 1.0         | True      |
| 5  | m1.xlarge | 16384     | 160  | 0         |      | 8     | 1.0         | True      |
| 84 | m1.micro  | 128       | 0    | 0         |      | 1     | 1.0         | True      |
| c1 | cirros256 | 256       | 0    | 0         |      | 1     | 1.0         | True      |
| d1 | ds512M    | 512       | 5    | 0         |      | 1     | 1.0         | True      |
| d2 | ds1G      | 1024      | 10   | 0         |      | 1     | 1.0         | True      |
| d3 | ds2G      | 2048      | 10   | 0         |      | 2     | 1.0         | True      |
| d4 | ds4G      | 4096      | 20   | 0         |      | 4     | 1.0         | True      |
+----+-----------+-----------+------+-----------+------+-------+-------------+-----------+
stack@osic-devstack-27:~/devstack$ 
```

## Nova Image List

```sh
stack@osic-devstack-27:~/devstack$ nova flavor-list
+----+-----------+-----------+------+-----------+------+-------+-------------+-----------+
| ID | Name      | Memory_MB | Disk | Ephemeral | Swap | VCPUs | RXTX_Factor | Is_Public |
+----+-----------+-----------+------+-----------+------+-------+-------------+-----------+
| 1  | m1.tiny   | 512       | 1    | 0         |      | 1     | 1.0         | True      |
| 2  | m1.small  | 2048      | 20   | 0         |      | 1     | 1.0         | True      |
| 3  | m1.medium | 4096      | 40   | 0         |      | 2     | 1.0         | True      |
| 4  | m1.large  | 8192      | 80   | 0         |      | 4     | 1.0         | True      |
| 42 | m1.nano   | 64        | 0    | 0         |      | 1     | 1.0         | True      |
| 5  | m1.xlarge | 16384     | 160  | 0         |      | 8     | 1.0         | True      |
| 84 | m1.micro  | 128       | 0    | 0         |      | 1     | 1.0         | True      |
| c1 | cirros256 | 256       | 0    | 0         |      | 1     | 1.0         | True      |
| d1 | ds512M    | 512       | 5    | 0         |      | 1     | 1.0         | True      |
| d2 | ds1G      | 1024      | 10   | 0         |      | 1     | 1.0         | True      |
| d3 | ds2G      | 2048      | 10   | 0         |      | 2     | 1.0         | True      |
| d4 | ds4G      | 4096      | 20   | 0         |      | 4     | 1.0         | True      |
+----+-----------+-----------+------+-----------+------+-------+-------------+-----------+
stack@osic-devstack-27:~/devstack$ nova image-list
WARNING: Command image-list is deprecated and will be removed after Nova 15.0.0 is released. Use python-glanceclient or openstackclient instead.
+--------------------------------------+---------------------------------+--------+--------+
| ID                                   | Name                            | Status | Server |
+--------------------------------------+---------------------------------+--------+--------+
| 2b9c5e8d-4b27-460b-a179-160ae14b896d | cirros-0.3.4-x86_64-uec         | ACTIVE |        |
| ed4ab703-50ee-4436-9a93-d45547788286 | cirros-0.3.4-x86_64-uec-kernel  | ACTIVE |        |
| 010ffd4a-df81-47bc-91a1-9c4f5ead3dc2 | cirros-0.3.4-x86_64-uec-ramdisk | ACTIVE |        |
+--------------------------------------+---------------------------------+--------+--------+
stack@osic-devstack-27:~/devstack$ 
```

## Nova List

```sh
stack@osic-devstack-27:~/devstack$ nova list
+----+------+--------+------------+-------------+----------+
| ID | Name | Status | Task State | Power State | Networks |
+----+------+--------+------------+-------------+----------+
+----+------+--------+------------+-------------+----------+
stack@osic-devstack-27:~/devstack$ 
```

# Nova Boot

```sh
stack@osic-devstack-27:~/devstack$ nova boot --flavor=1 --image=2b9c5e8d-4b27-460b-a179-160ae14b896d hellonova
+--------------------------------------+----------------------------------------------------------------+
| Property                             | Value                                                          |
+--------------------------------------+----------------------------------------------------------------+
| OS-DCF:diskConfig                    | MANUAL                                                         |
| OS-EXT-AZ:availability_zone          |                                                                |
| OS-EXT-SRV-ATTR:host                 | -                                                              |
| OS-EXT-SRV-ATTR:hostname             | hellonova                                                      |
| OS-EXT-SRV-ATTR:hypervisor_hostname  | -                                                              |
| OS-EXT-SRV-ATTR:instance_name        | instance-00000001                                              |
| OS-EXT-SRV-ATTR:kernel_id            | ed4ab703-50ee-4436-9a93-d45547788286                           |
| OS-EXT-SRV-ATTR:launch_index         | 0                                                              |
| OS-EXT-SRV-ATTR:ramdisk_id           | 010ffd4a-df81-47bc-91a1-9c4f5ead3dc2                           |
| OS-EXT-SRV-ATTR:reservation_id       | r-yagpgy7y                                                     |
| OS-EXT-SRV-ATTR:root_device_name     | -                                                              |
| OS-EXT-SRV-ATTR:user_data            | -                                                              |
| OS-EXT-STS:power_state               | 0                                                              |
| OS-EXT-STS:task_state                | scheduling                                                     |
| OS-EXT-STS:vm_state                  | building                                                       |
| OS-SRV-USG:launched_at               | -                                                              |
| OS-SRV-USG:terminated_at             | -                                                              |
| accessIPv4                           |                                                                |
| accessIPv6                           |                                                                |
| adminPass                            | F8vZXbb72JXz                                                   |
| config_drive                         |                                                                |
| created                              | 2016-07-19T17:42:29Z                                           |
| description                          | -                                                              |
| flavor                               | m1.tiny (1)                                                    |
| hostId                               |                                                                |
| host_status                          |                                                                |
| id                                   | 83788f3c-2a20-4d7c-bae5-aea5b5615e34                           |
| image                                | cirros-0.3.4-x86_64-uec (2b9c5e8d-4b27-460b-a179-160ae14b896d) |
| key_name                             | -                                                              |
| locked                               | False                                                          |
| metadata                             | {}                                                             |
| name                                 | hellonova                                                      |
| os-extended-volumes:volumes_attached | []                                                             |
| progress                             | 0                                                              |
| security_groups                      | default                                                        |
| status                               | BUILD                                                          |
| tags                                 | []                                                             |
| tenant_id                            | 6713353d509940fb8bd374ec5ead210f                               |
| updated                              | 2016-07-19T17:42:29Z                                           |
| user_id                              | f79037bbca0c42b39a99d9f0bacc4c38                               |
+--------------------------------------+----------------------------------------------------------------+
```

```sh
stack@osic-devstack-27:~/devstack$ nova list
+--------------------------------------+-----------+--------+------------+-------------+--------------------------------+
| ID                                   | Name      | Status | Task State | Power State | Networks                       |
+--------------------------------------+-----------+--------+------------+-------------+--------------------------------+
| 83788f3c-2a20-4d7c-bae5-aea5b5615e34 | hellonova | ACTIVE | -          | Running     | public=2001:db8::8, 172.24.4.4 |
+--------------------------------------+-----------+--------+------------+-------------+--------------------------------+
stack@osic-devstack-27:~/devstack$
```
