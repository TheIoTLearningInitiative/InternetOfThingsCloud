# Laboratory

> This guide is for experienced software developers who want to deploy applications to OpenStack clouds. If you are familiar with OpenStack but have not created a cloud application in general or an OpenStack application in particular, this section teaches you how to program with OpenStack components. 
[Writing your first OpenStack application](http://developer.openstack.org/firstapp-shade/getting_started.html)


# Getting Started


## Apt-Get Install

```sh
root@debiando:~# apt-get install python-pip python-dev python-requests
Reading package lists... Done
Building dependency tree
Reading state information... Done
python-dev is already the newest version.
python-pip is already the newest version.
python-requests is already the newest version.
0 upgraded, 0 newly installed, 0 to remove and 3 not upgraded.
root@debiando:~# 
```

## Pip Install

```sh
root@debiando:~# pip install -U pip setuptools requests
Installing collected packages: pip, setuptools, requests
Successfully installed pip setuptools requests
Cleaning up...
root@debiando:~# 
```

```sh
root@debiando:~# pip install shade os-client-config ipaddress oslo.config python-heatclient futures
Requirement already satisfied (use --upgrade to upgrade): shade in /usr/local/lib/python2.7/dist-packages
Requirement already satisfied (use --upgrade to upgrade): os-client-config in /usr/local/lib/python2.7/dist-packages
Requirement already satisfied (use --upgrade to upgrade): ipaddress in /usr/local/lib/python2.7/dist-packages
Requirement already satisfied (use --upgrade to upgrade): oslo.config in /usr/local/lib/python2.7/dist-packages
Requirement already satisfied (use --upgrade to upgrade): python-heatclient in /usr/local/lib/python2.7/dist-packages
Requirement already satisfied (use --upgrade to upgrade): futures in /usr/local/lib/python2.7/dist-packages
Cleaning up...
root@debiando:~# 
```

```sh
   71  pip install shade
   78  pip install python-novaclient
   80  pip install os_client_config
   81  pip install setuptools
   83  pip install utils
   84  pip install -U pip setuptools
   85  pip install -U requests pip setuptools
   86  pip install distutils
   91  pip install shade
   95  pip install os_client_config
   96  pip install os-client-config
   99  pip install shade
  100  pip install os-client-config
  102  pip install ipaddress
  104  pip install oslo-config
  105  pip install oslo.config
  107  pip install python-heatclient
  110  pip install futures
  112  pip install python-designaclient
  113  pip install python-designateclient
  115  pip install decorator
  117  pip install ironicclient
  118  pip install python-ironicclient
  329  history | grep "pip install"
```


- [](http://developer.openstack.org/firstapp-shade/getting_started.html)

```sh

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