# Laboratory

> This guide is for experienced software developers who want to deploy applications to OpenStack clouds. If you are familiar with OpenStack but have not created a cloud application in general or an OpenStack application in particular, this section teaches you how to program with OpenStack components. 
[Writing your first OpenStack application](http://developer.openstack.org/firstapp-shade/getting_started.html)


# Getting Started

- [Getting Started](http://developer.openstack.org/firstapp-shade/getting_started.html)

## Choose your OpenStack SDK

Python!

## What you need

### Apt-Get Install

```sh
root@debiando:~# apt-get install python-pip python-dev python-requests
```

### Pip Install

```sh
root@debiando:~# pip install -U pip setuptools requests
root@debiando:~# pip install shade os-client-config ipaddress oslo.config python-heatclient futures
root@debiando:~# pip install python-ironicclient
root@debiando:~# pip install python-designateclient decorator
```
## How you interact with OpenStack

- [Public Clouds](http://git.openstack.org/cgit/openstack/os-client-config/tree/os_client_config/vendors)

```sh
my-provider:
    profile: $PROVIDER_NAME
    auth:
        username: $YOUR_USERNAME
        password: $YOUR_PASSWORD
        project_name: $YOUR_PROJECT
    region_name: $REGION
```

```sh
root@debiando:~# cat clouds.yaml
clouds:
  internapNYJ:
      profile: 
      auth:
        project_name: 
        username: 
        password: 
      region_name: 
  internapAMS:
      profile: 
      auth:
        project_name: 
        username: 
        password: 
      region_name: 
```

```sh
root@debiando:~# nano helloshade.py
```

```python
from shade import *

simple_logging(debug=True)
conn = openstack_cloud(cloud='')
```

```sh
root@debiando:~# python helloshade.py
root@debiando:~# 
```

## Flavors and images


```sh
root@debiando:~# nano helloshade.py
```

```python
from shade import *

simple_logging(debug=True)
conn = openstack_cloud(cloud='internapNYJ')

images = conn.list_images()
for image in images:
    print(image)

```

```json
root@debiando:~# python helloshade.py
Munch({
  'status': u'active',
  'properties': {
    u'iweb__1__visible': u'1',
    u'version': u'2012.r2',
    u'architecture': u'x86_64',
    u'build_version': u'101',
    u'os_type': u'windows',
    u'virtual_size': u'42949672960',
    u'distro': u'windows'
  },
  'virtual_size': None,
  'NAME_ATTR': 'name',
  'name': u'Windows Server 2012 R2',
  'deleted': False,
  'checksum': u'0220af63a7febb2e9036f6fb30cbe1ab',
  'created_at': u'2016-07-07T17:56:01.000000',
  'disk_format': u'qcow2',
  'updated_at': u'2016-07-07T18:25:08.000000',
  'owner': u'b89d3a2aafd74370a5ba516477ab18fb',
  'human_id': None,
  'min_disk': 40,
  'protected': False,
  'min_ram': 1024,
  'container_format': u'bare',
  'id': u'9b335517-96d1-4131-95f7-9bef7005d3b4',
  'is_public': True,
  'deleted_at': None,
  'HUMAN_ID': False,
  'size': 6605504512
})Munch({
  'status': u'active',
  'properties': {
    u'iweb__1__visible': u'1',
    u'iweb__1__network_models': u'active_passive',
    u'version': u'6.0U2',
    u'architecture': u'x86_64',
    u'build_version': u'5',
    u'os_type': u'linux',
    u'virtual_size': u'16106127360',
    u'distro': u'esxi'
  },
  'virtual_size': None,
  'NAME_ATTR': 'name',
  'name': u'ESXi 6.0 U2',
  'deleted': False,
  'checksum': u'1bccea560454d3a8fe419c56f47a5be2',
  'created_at': u'2016-06-28T15:06:25.000000',
  'disk_format': u'qcow2',
  'updated_at': u'2016-06-28T15:12:41.000000',
  'owner': u'b89d3a2aafd74370a5ba516477ab18fb',
  'human_id': None,
  'min_disk': 15,
  'protected': False,
  'min_ram': 4096,
  'container_format': u'bare',
  'id': u'48dc172e-1fb3-4ad6-ac4c-a6e24e8c5565',
  'is_public': True,
  'deleted_at': None,
  'HUMAN_ID': False,
  'size': 575143936
})Munch({
  'status': u'active',
  'properties': {
    u'iweb__1__visible': u'1',
    u'version': u'7',
    u'architecture': u'x86_64',
    u'build_version': u'32',
    u'os_type': u'linux',
    u'virtual_size': u'10737418240',
    u'distro': u'centos'
  },
  'virtual_size': None,
  'NAME_ATTR': 'name',
  'name': u'CentOS 7',
  'deleted': False,
  'checksum': u'148ec76d53cd126c198e79aedbdfaf69',
  'created_at': u'2016-05-26T16:33:03.000000',
  'disk_format': u'qcow2',
  'updated_at': u'2016-05-26T16:34:53.000000',
  'owner': u'b89d3a2aafd74370a5ba516477ab18fb',
  'human_id': None,
  'min_disk': 10,
  'protected': False,
  'min_ram': 256,
  'container_format': u'bare',
  'id': u'67ae9c62-4276-49b9-b53d-c0b7cf3eca6f',
  'is_public': True,
  'deleted_at': None,
  'HUMAN_ID': False,
  'size': 699882496
})Munch({
  'status': u'active',
  'properties': {
    u'iweb__1__visible': u'1',
    u'version': u'6',
    u'architecture': u'x86_64',
    u'build_version': u'112',
    u'os_type': u'linux',
    u'virtual_size': u'10737418240',
    u'distro': u'centos'
  },
  'virtual_size': None,
  'NAME_ATTR': 'name',
  'name': u'CentOS 6',
  'deleted': False,
  'checksum': u'ee159e60ad43a72b745bb48a192dcd22',
  'created_at': u'2016-03-21T15:29:51.000000',
  'disk_format': u'qcow2',
  'updated_at': u'2016-03-21T15:34:57.000000',
  'owner': u'b89d3a2aafd74370a5ba516477ab18fb',
  'human_id': None,
  'min_disk': 10,
  'protected': False,
  'min_ram': 256,
  'container_format': u'bare',
  'id': u'f4bcad12-5668-44f7-9ceb-dfd9c00beee0',
  'is_public': True,
  'deleted_at': None,
  'HUMAN_ID': False,
  'size': 664521216
})Munch({
  'status': u'active',
  'properties': {
    u'iweb__1__visible': u'1',
    u'version': u'8',
    u'architecture': u'x86_64',
    u'build_version': u'61',
    u'os_type': u'linux',
    u'virtual_size': u'10737418240',
    u'distro': u'debian'
  },
  'virtual_size': None,
  'NAME_ATTR': 'name',
  'name': u'Debian 8 (Jessie)',
  'deleted': False,
  'checksum': u'96daf66c2cbc2bb70274f02ea299b938',
  'created_at': u'2016-03-16T18:59:20.000000',
  'disk_format': u'qcow2',
  'updated_at': u'2016-03-16T19:06:33.000000',
  'owner': u'b89d3a2aafd74370a5ba516477ab18fb',
  'human_id': None,
  'min_disk': 10,
  'protected': False,
  'min_ram': 256,
  'container_format': u'bare',
  'id': u'ba7ce431-c1ea-4345-949e-96668de5ee02',
  'is_public': True,
  'deleted_at': None,
  'HUMAN_ID': False,
  'size': 781381120
})Munch({
  'status': u'active',
  'properties': {
    u'iweb__1__visible': u'1',
    u'version': u'7',
    u'architecture': u'x86_64',
    u'build_version': u'21',
    u'os_type': u'linux',
    u'virtual_size': u'10737418240',
    u'distro': u'debian'
  },
  'virtual_size': None,
  'NAME_ATTR': 'name',
  'name': u'Debian 7 (Wheezy)',
  'deleted': False,
  'checksum': u'c1dc21ee0d9b5dbe6e8ca7b70a9429a6',
  'created_at': u'2016-03-16T18:55:49.000000',
  'disk_format': u'qcow2',
  'updated_at': u'2016-03-16T18:59:18.000000',
  'owner': u'b89d3a2aafd74370a5ba516477ab18fb',
  'human_id': None,
  'min_disk': 10,
  'protected': False,
  'min_ram': 256,
  'container_format': u'bare',
  'id': u'c217a779-9b82-43b2-b16c-7f2e94a5fe60',
  'is_public': True,
  'deleted_at': None,
  'HUMAN_ID': False,
  'size': 549675008
})Munch({
  'status': u'active',
  'properties': {
    u'iweb__1__visible': u'1',
    u'version': u'14.04',
    u'architecture': u'x86_64',
    u'build_version': u'41',
    u'os_type': u'linux',
    u'virtual_size': u'10737418240',
    u'distro': u'ubuntu'
  },
  'virtual_size': None,
  'NAME_ATTR': 'name',
  'name': u'Ubuntu 14.04 LTS (Trusty Tahr)',
  'deleted': False,
  'checksum': u'9e4c544b79c41f64144b0436824abdd2',
  'created_at': u'2016-03-16T17:52:45.000000',
  'disk_format': u'qcow2',
  'updated_at': u'2016-03-16T17:57:04.000000',
  'owner': u'b89d3a2aafd74370a5ba516477ab18fb',
  'human_id': None,
  'min_disk': 10,
  'protected': False,
  'min_ram': 256,
  'container_format': u'bare',
  'id': u'3c76334f-9644-4666-ac3c-fa090f175655',
  'is_public': True,
  'deleted_at': None,
  'HUMAN_ID': False,
  'size': 741267456
})Munch({
  'status': u'active',
  'properties': {
    u'iweb__1__visible': u'1',
    u'version': u'12.04',
    u'architecture': u'x86_64',
    u'build_version': u'154',
    u'os_type': u'linux',
    u'virtual_size': u'10737418240',
    u'distro': u'ubuntu'
  },
  'virtual_size': None,
  'NAME_ATTR': 'name',
  'name': u'Ubuntu 12.04 LTS (Precise Pangolin)',
  'deleted': False,
  'checksum': u'beea04e10a1fcb9a5f52c4c036ae085b',
  'created_at': u'2016-03-16T17:48:21.000000',
  'disk_format': u'qcow2',
  'updated_at': u'2016-03-16T17:52:17.000000',
  'owner': u'b89d3a2aafd74370a5ba516477ab18fb',
  'human_id': None,
  'min_disk': 10,
  'protected': False,
  'min_ram': 256,
  'container_format': u'bare',
  'id': u'fd8d4483-6dfa-43ba-98d8-8b8487d90f7c',
  'is_public': True,
  'deleted_at': None,
  'HUMAN_ID': False,
  'size': 693042688
})
root@debiando:~# 
```



```sh
root@debiando:~# nano helloshade.py
```

```python
from shade import *

simple_logging(debug=True)
conn = openstack_cloud(cloud='internapNYJ')

flavors =  conn.list_flavors()
for flavor in flavors:
    print(flavor)
```

```json
root@debiando:~# python helloshade.py
Munch({
  'name': u'A1.1',
  'ram': 1024,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 1,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'quota:vif_inbound_average': u'102400',
    u'quota:vif_outbound_average': u'102400',
    u'cpu_allocation_ratio': u'3'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'A1.1',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 20
})Munch({
  'name': u'A1.16',
  'ram': 16384,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 16,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'quota:vif_inbound_average': u'102400',
    u'quota:vif_outbound_average': u'102400',
    u'cpu_allocation_ratio': u'3'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'A1.16',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 320
})Munch({
  'name': u'A1.2',
  'ram': 2048,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 2,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'quota:vif_inbound_average': u'102400',
    u'quota:vif_outbound_average': u'102400',
    u'cpu_allocation_ratio': u'3'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'A1.2',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 40
})Munch({
  'name': u'A1.4',
  'ram': 4096,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 4,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'quota:vif_inbound_average': u'102400',
    u'quota:vif_outbound_average': u'102400',
    u'cpu_allocation_ratio': u'3'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'A1.4',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 80
})Munch({
  'name': u'A1.8',
  'ram': 8192,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 8,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'quota:vif_inbound_average': u'102400',
    u'quota:vif_outbound_average': u'102400',
    u'cpu_allocation_ratio': u'3'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'A1.8',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 160
})Munch({
  'name': u'AS2.1xE3-1230v2.8GB.1x1TB.HDD.1GbE',
  'ram': 8192,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 8,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'capabilities:hardware_cpu_count': u'1',
    u'network:supported_models': u'lacp,flat,active_passive',
    u'capabilities:hardware_storage_1_type': u'HDD',
    u'capabilities:network_model': u'<in> bond',
    u'capabilities:hardware_storage_1_size_gb': u'1000',
    u'capabilities:hardware_storage_raid_controller': u'None',
    u'capabilities:hardware_cpu_model': u'Intel(R) Xeon(R) CPU E3-1230 V2 @ 3.30GHz',
    u'capabilities:hardware_storage_count': u'1',
    u'class': u'metal',
    u'capabilities:hardware_network_link_speed_mbit': u'1000'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'AS2.1xE3-1230v2.8GB.1x1TB.HDD.1GbE',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 1000
})Munch({
  'name': u'AS2.1xE3-1270v2.32GB.1x1TB.HDD.1GbE',
  'ram': 32768,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 8,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'capabilities:hardware_cpu_count': u'1',
    u'network:supported_models': u'lacp,flat,active_passive',
    u'capabilities:hardware_storage_1_type': u'HDD',
    u'capabilities:network_model': u'<in> bond',
    u'capabilities:hardware_storage_1_size_gb': u'1000',
    u'capabilities:hardware_storage_raid_controller': u'None',
    u'capabilities:hardware_cpu_model': u'Intel(R) Xeon(R) CPU E3-1270 V2 @ 3.50GHz',
    u'capabilities:hardware_storage_count': u'1',
    u'class': u'metal',
    u'capabilities:hardware_network_link_speed_mbit': u'1000'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'AS2.1xE3-1270v2.32GB.1x1TB.HDD.1GbE',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 1000
})Munch({
  'name': u'AS2.1xE5-1620v3.32GB.1x2TB.HDD.1GbE',
  'ram': 32768,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 8,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'capabilities:hardware_cpu_count': u'1',
    u'network:supported_models': u'lacp,flat,active_passive',
    u'capabilities:hardware_storage_1_type': u'HDD',
    u'capabilities:network_model': u'<in> bond',
    u'capabilities:hardware_storage_1_size_gb': u'2000',
    u'capabilities:hardware_storage_raid_controller': u'None',
    u'capabilities:hardware_cpu_model': u'Intel(R) Xeon(R) CPU E5-1620 v3 @ 3.50GHz',
    u'capabilities:hardware_storage_count': u'1',
    u'class': u'metal',
    u'capabilities:hardware_network_link_speed_mbit': u'1000'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'AS2.1xE5-1620v3.32GB.1x2TB.HDD.1GbE',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 2000
})Munch({
  'name': u'AS2.1xE5-1650v3.64GB.1x2TB.HDD.1GbE',
  'ram': 65536,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 12,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'capabilities:hardware_cpu_count': u'1',
    u'network:supported_models': u'lacp,flat,active_passive',
    u'capabilities:hardware_storage_1_type': u'HDD',
    u'capabilities:network_model': u'<in> bond',
    u'capabilities:hardware_storage_1_size_gb': u'2000',
    u'capabilities:hardware_storage_raid_controller': u'None',
    u'capabilities:hardware_cpu_model': u'Intel(R) Xeon(R) CPU E5-1650 v3 @ 3.50GHz',
    u'capabilities:hardware_storage_count': u'1',
    u'class': u'metal',
    u'capabilities:hardware_network_link_speed_mbit': u'1000'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'AS2.1xE5-1650v3.64GB.1x2TB.HDD.1GbE',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 2000
})Munch({
  'name': u'AS2.2xE5-2620v1.32GB.1x1TB.HDD.1GbE',
  'ram': 32768,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 24,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'capabilities:hardware_cpu_count': u'2',
    u'network:supported_models': u'lacp,flat,active_passive',
    u'capabilities:hardware_storage_1_type': u'HDD',
    u'capabilities:network_model': u'<in> bond',
    u'capabilities:hardware_storage_1_size_gb': u'1000',
    u'capabilities:hardware_storage_raid_controller': u'None',
    u'capabilities:hardware_cpu_model': u'Intel(R) Xeon(R) CPU E5-2620 0 @ 2.00GHz',
    u'capabilities:hardware_storage_count': u'1',
    u'class': u'metal',
    u'capabilities:hardware_network_link_speed_mbit': u'1000'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'AS2.2xE5-2620v1.32GB.1x1TB.HDD.1GbE',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 1000
})Munch({
  'name': u'AS2.2xE5-2620v3.64GB.1x2TB.HDD.10GbE',
  'ram': 65536,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 24,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'capabilities:hardware_cpu_count': u'2',
    u'network:supported_models': u'lacp,flat,active_passive',
    u'capabilities:hardware_storage_1_type': u'HDD',
    u'capabilities:network_model': u'<in> bond',
    u'capabilities:hardware_storage_1_size_gb': u'2000',
    u'capabilities:hardware_storage_raid_controller': u'None',
    u'capabilities:hardware_cpu_model': u'Intel(R) Xeon(R) CPU E5-2620 v3 @ 2.40GHz',
    u'capabilities:hardware_storage_count': u'1',
    u'class': u'metal',
    u'capabilities:hardware_network_link_speed_mbit': u'10000'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'AS2.2xE5-2620v3.64GB.1x2TB.HDD.10GbE',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 2000
})Munch({
  'name': u'AS2.2xE5-2620v3.64GB.1x480GB.SSD.10GbE',
  'ram': 65536,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 24,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'capabilities:hardware_cpu_count': u'2',
    u'network:supported_models': u'lacp,flat,active_passive',
    u'capabilities:hardware_storage_1_type': u'SSD',
    u'capabilities:network_model': u'<in> bond',
    u'capabilities:hardware_storage_1_size_gb': u'480',
    u'capabilities:hardware_storage_raid_controller': u'None',
    u'capabilities:hardware_cpu_model': u'Intel(R) Xeon(R) CPU E5-2620 v3 @ 2.40GHz',
    u'capabilities:hardware_storage_count': u'1',
    u'class': u'metal',
    u'capabilities:hardware_network_link_speed_mbit': u'10000'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'AS2.2xE5-2620v3.64GB.1x480GB.SSD.10GbE',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 480
})Munch({
  'name': u'AS2.2xE5-2630v3.64GB.1x2TB.HDD.10GbE',
  'ram': 65536,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 32,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'capabilities:hardware_cpu_count': u'2',
    u'network:supported_models': u'lacp,flat,active_passive',
    u'capabilities:hardware_storage_1_type': u'HDD',
    u'capabilities:network_model': u'<in> bond',
    u'capabilities:hardware_storage_1_size_gb': u'2000',
    u'capabilities:hardware_storage_raid_controller': u'None',
    u'capabilities:hardware_cpu_model': u'Intel(R) Xeon(R) CPU E5-2630 v3 @ 2.40GHz',
    u'capabilities:hardware_storage_count': u'1',
    u'class': u'metal',
    u'capabilities:hardware_network_link_speed_mbit': u'10000'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'AS2.2xE5-2630v3.64GB.1x2TB.HDD.10GbE',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 2000
})Munch({
  'name': u'AS2.2xE5-2630v3.64GB.1x480GB.SSD.10GbE',
  'ram': 65536,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 32,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'capabilities:hardware_cpu_count': u'2',
    u'network:supported_models': u'lacp,flat,active_passive',
    u'capabilities:hardware_storage_1_type': u'SSD',
    u'capabilities:network_model': u'<in> bond',
    u'capabilities:hardware_storage_1_size_gb': u'480',
    u'capabilities:hardware_storage_raid_controller': u'None',
    u'capabilities:hardware_cpu_model': u'Intel(R) Xeon(R) CPU E5-2630 v3 @ 2.40GHz',
    u'capabilities:hardware_storage_count': u'1',
    u'class': u'metal',
    u'capabilities:hardware_network_link_speed_mbit': u'10000'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'AS2.2xE5-2630v3.64GB.1x480GB.SSD.10GbE',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 480
})Munch({
  'name': u'B1.1',
  'ram': 4096,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 1,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'quota:vif_inbound_average': u'507000',
    u'quota:vif_outbound_average': u'507000',
    u'cpu_allocation_ratio': u'1'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'B1.1',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 20
})Munch({
  'name': u'B1.16',
  'ram': 61440,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 16,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'quota:vif_inbound_average': u'1024000',
    u'quota:vif_outbound_average': u'1024000',
    u'cpu_allocation_ratio': u'1'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'B1.16',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 320
})Munch({
  'name': u'B1.2',
  'ram': 8192,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 2,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'quota:vif_inbound_average': u'507000',
    u'quota:vif_outbound_average': u'507000',
    u'cpu_allocation_ratio': u'1'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'B1.2',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 40
})Munch({
  'name': u'B1.4',
  'ram': 15360,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 4,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'quota:vif_inbound_average': u'1024000',
    u'quota:vif_outbound_average': u'1024000',
    u'cpu_allocation_ratio': u'1'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'B1.4',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 80
})Munch({
  'name': u'B1.8',
  'ram': 30720,
  'ephemeral': 0,
  'request_ids': [
    
  ],
  'vcpus': 8,
  'x_openstack_request_ids': [
    
  ],
  'extra_specs': Munch({
    u'quota:vif_inbound_average': u'1024000',
    u'quota:vif_outbound_average': u'1024000',
    u'cpu_allocation_ratio': u'1'
  }),
  'swap': u'',
  'os-flavor-access:is_public': True,
  'rxtx_factor': 1.0,
  'id': u'B1.8',
  'is_public': True,
  'OS-FLV-EXT-DATA:ephemeral': 0,
  'disk': 160
})
root@debiando:~# 
```

### Images

```json
  'name': u'Ubuntu 14.04 LTS (Trusty Tahr)',
  ...
  'id': u'3c76334f-9644-4666-ac3c-fa090f175655',
```

```python
from shade import *

simple_logging(debug=False)
conn = openstack_cloud(cloud='internapNYJ')

image_id = '3c76334f-9644-4666-ac3c-fa090f175655'
image = conn.get_image(image_id)
print(image)
```

```json
root@debiando:~# python helloshade.py
Munch({
  'status': u'active',
  'properties': {
    u'iweb__1__visible': u'1',
    u'version': u'14.04',
    u'architecture': u'x86_64',
    u'bild_version': u'41',
    u'os_type': u'linux',
    u'virtual_size': u'10737418240',
    u'distro': u'ubuntu'
  },
  'virtual_size': None,
  'NME_ATTR': 'name',
  'name': u'Ubuntu 14.04 LTS (Trusty Tahr)',
  'deleted': False,
  'checksum': u'9e4c544b79c41f64144b0436824abd2',
  'created_at': u'2016-03-16T17:52:45.000000',
  'disk_format': u'qcow2',
  'updated_at': u'2016-03-16T17:57:04.000000',
  'ownr': u'b89d3a2aafd74370a5ba516477ab18fb',
  'human_id': None,
  'min_disk': 10,
  'protected': False,
  'min_ram': 256,
  'container_frmat': u'bare',
  'id': u'3c76334f-9644-4666-ac3c-fa090f175655',
  'is_public': True,
  'deleted_at': None,
  'HUMAN_ID': False,
  'sze': 741267456
})
root@debiando:~#
```

### Flavors

```json
root@debiando:~# python helloshade.py
Munch({
  'name': u'A1.1',
  'ram': 1024,
  ...
  'disk': 20
```
###

```sh
root@debiando:~# nano helloshade.py
```

```sh
root@debiando:~# python helloshade.py
root@debiando:~# 
```

```python
ex_userdata = '''#!/usr/bin/env bash

curl -L -s https://git.openstack.org/cgit/openstack/faafo/plain/contrib/install.sh | bash -s -- \
-i faafo -i messaging -r api -r worker -r demo
'''

from shade import *
conn = openstack_cloud(cloud='internapNYJ')

conn.delete_server(name_or_id='all-in-one')
#images = conn.list_images()
#for image in images:
#print(image)

#flavors =  conn.list_flavors()
#for flavor in flavors:
#    print(flavor)
#print("ooooooooo")

image_id ='3c76334f-9644-4666-ac3c-fa090f175655'
image = conn.get_image(image_id)
#print(image)
#print("ooooooooo")

flavor_id = 'A1.1'
flavor = conn.get_flavor(flavor_id)
#print(flavor)
network= conn.list_networks()
#network_id = '93ab6b4f-25e7-44ed-b1a4-671d70b25b69'
nics=[{'net-id':'93ab6b4f-25e7-44ed-b1a4-671d70b25b69'},{'net-id': '30da5249-14be-4b53-81e6-9b9c1568df67'}]

#print(network)


# this is for delete an instance

print('Checking for existing SSH keypair...')
keypair_name = 'demokey'
pub_key_file = '/root/.ssh/id_rsa.pub'

if conn.search_keypairs(keypair_name):
    print('Keypair already exists. Skipping import.')
else:
    print('Adding keypair...')
    conn.create_keypair(keypair_name, open(pub_key_file, 'r').read().strip())

for keypair in conn.list_keypairs():
    print(keypair)

#f_ip=conn.available_floating_ip()

#print('Checking for existing security groups...')
#sec_group_name = 'all-in-one'
#if conn.search_security_groups(sec_group_name):
#    print('Security group already exists. Skipping creation.')
#else:
#    print('Creating security group.')
#    conn.create_security_group(sec_group_name, 'network access for all-in-one application.')
#    conn.create_security_group_rule(sec_group_name, 80, 80, 'TCP')
#    conn.create_security_group_rule(sec_group_name, 22, 22, 'TCP')

#print(conn.search_security_groups(sec_group_name))
instance_name = 'all-in-one'
testing_instance = conn.create_server(wait=True,
    name=instance_name,
    image=image_id,
    flavor=flavor_id,
    #network= network_id,
    key_name=keypair_name,
    security_groups=['default'],
    nics=nics )
print(testing_instance)

instances = conn.list_servers()
#for instance in instances:
#    print(instance)

#print('The Fractals app will be deployed to http://%s' % f_ip['floating_ip_address'] )



```