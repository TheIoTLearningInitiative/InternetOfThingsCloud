# Laboratory

```sh
stack@osic-devstack-27:~$ pgrep -l glance
29903 glance-registry
30033 glance-registry
30034 glance-registry
30073 glance-api
30158 glance-api
30159 glance-api
stack@osic-devstack-27:~$ 
```

```sh
stack@osic-devstack-27:~/devstack$ source openrc admin admin
WARNING: setting legacy OS_TENANT_NAME to support cli tools.
stack@osic-devstack-27:~/devstack$ 
```

```sh
stack@osic-devstack-27:~/devstack$ nova image-list
WARNING: Command image-list is deprecated and will be removed after Nova 15.0.0 is released. Use python-glanceclient or openstackclient instead.
+--------------------------------------+---------------------------------+--------+--------+
| ID                                   | Name                            | Status | Server |
+--------------------------------------+---------------------------------+--------+--------+
| 2b9c5e8d-4b27-460b-a179-160ae14b896d | cirros-0.3.4-x86_64-uec         | ACTIVE |        |
| ed4ab703-50ee-4436-9a93-d45547788286 | cirros-0.3.4-x86_64-uec-kernel  | ACTIVE |        |
| 010ffd4a-df81-47bc-91a1-9c4f5ead3dc2 | cirros-0.3.4-x86_64-uec-ramdisk | ACTIVE |        |
+--------------------------------------+---------------------------------+--------+--------+
stack@osic-devstack-27:~/devstack$ glance image-list
+--------------------------------------+---------------------------------+
| ID                                   | Name                            |
+--------------------------------------+---------------------------------+
| 2b9c5e8d-4b27-460b-a179-160ae14b896d | cirros-0.3.4-x86_64-uec         |
| ed4ab703-50ee-4436-9a93-d45547788286 | cirros-0.3.4-x86_64-uec-kernel  |
| 010ffd4a-df81-47bc-91a1-9c4f5ead3dc2 | cirros-0.3.4-x86_64-uec-ramdisk |
+--------------------------------------+---------------------------------+
stack@osic-devstack-27:~/devstack$ openstack image list
+--------------------------------------+---------------------------------+--------+
| ID                                   | Name                            | Status |
+--------------------------------------+---------------------------------+--------+
| 2b9c5e8d-4b27-460b-a179-160ae14b896d | cirros-0.3.4-x86_64-uec         | active |
| 010ffd4a-df81-47bc-91a1-9c4f5ead3dc2 | cirros-0.3.4-x86_64-uec-ramdisk | active |
| ed4ab703-50ee-4436-9a93-d45547788286 | cirros-0.3.4-x86_64-uec-kernel  | active |
+--------------------------------------+---------------------------------+--------+
stack@osic-devstack-27:~/devstack$ 
```

```sh
stack@osic-devstack-27:~/devstack$ glance image-show 2b9c5e8d-4b27-460b-a179-160ae14b896d
+------------------+--------------------------------------+
| Property         | Value                                |
+------------------+--------------------------------------+
| checksum         | eb9139e4942121f22bbc2afc0400b2a4     |
| container_format | ami                                  |
| created_at       | 2016-07-16T22:30:35Z                 |
| disk_format      | ami                                  |
| id               | 2b9c5e8d-4b27-460b-a179-160ae14b896d |
| kernel_id        | ed4ab703-50ee-4436-9a93-d45547788286 |
| min_disk         | 0                                    |
| min_ram          | 0                                    |
| name             | cirros-0.3.4-x86_64-uec              |
| owner            | 6713353d509940fb8bd374ec5ead210f     |
| protected        | False                                |
| ramdisk_id       | 010ffd4a-df81-47bc-91a1-9c4f5ead3dc2 |
| size             | 25165824                             |
| status           | active                               |
| tags             | []                                   |
| updated_at       | 2016-07-16T22:30:35Z                 |
| virtual_size     | None                                 |
| visibility       | public                               |
+------------------+--------------------------------------+
stack@osic-devstack-27:~/devstack$ 
```

```sh
stack@osic-devstack-27:~/devstack$ glance --help
```

```sh
stack@osic-devstack-27:~/devstack$ glance help image-list
usage: glance image-list [--limit <LIMIT>] [--page-size <SIZE>]
                         [--visibility <VISIBILITY>]
                         [--member-status <MEMBER_STATUS>] [--owner <OWNER>]
                         [--property-filter <KEY=VALUE>]
                         [--checksum <CHECKSUM>] [--tag <TAG>]
                         [--sort-key {name,status,container_format,disk_format,size,id,created_at,updated_at}]
                         [--sort-dir {asc,desc}] [--sort <key>[:<direction>]]

List images you can access.

Optional arguments:
  --limit <LIMIT>       Maximum number of images to get.
  --page-size <SIZE>    Number of images to request in each paginated request.
  --visibility <VISIBILITY>
                        The visibility of the images to display.
  --member-status <MEMBER_STATUS>
                        The status of images to display.
  --owner <OWNER>       Display images owned by <OWNER>.
  --property-filter <KEY=VALUE>
                        Filter images by a user-defined image property.
  --checksum <CHECKSUM>
                        Displays images that match the checksum.
  --tag <TAG>           Filter images by a user-defined tag.
  --sort-key {name,status,container_format,disk_format,size,id,created_at,updated_at}
                        Sort image list by specified fields. May be used
                        multiple times.
  --sort-dir {asc,desc}
                        Sort image list in specified directions.
  --sort <key>[:<direction>]
                        Comma-separated list of sort keys and directions in
                        the form of <key>[:<asc|desc>]. Valid keys: name,
                        status, container_format, disk_format, size, id,
                        created_at, updated_at. OPTIONAL.

Run `glance --os-image-api-version 1 help image-list` for v1 help
stack@osic-devstack-27:~/devstack$ 
```


```sh
stack@osic-devstack-27:~/devstack$ source openrc demo demo
WARNING: setting legacy OS_TENANT_NAME to support cli tools.
stack@osic-devstack-27:~/devstack$ glance image-list
+--------------------------------------+---------------------------------+
| ID                                   | Name                            |
+--------------------------------------+---------------------------------+
| 2b9c5e8d-4b27-460b-a179-160ae14b896d | cirros-0.3.4-x86_64-uec         |
| ed4ab703-50ee-4436-9a93-d45547788286 | cirros-0.3.4-x86_64-uec-kernel  |
| 010ffd4a-df81-47bc-91a1-9c4f5ead3dc2 | cirros-0.3.4-x86_64-uec-ramdisk |
+--------------------------------------+---------------------------------+
stack@osic-devstack-27:~/devstack$ 
```

```sh
stack@osic-devstack-27:~/devstack$ mkdir ~/images
stack@osic-devstack-27:~/devstack$ cd ~/images
stack@osic-devstack-27:~/images$ 
```