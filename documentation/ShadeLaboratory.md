# Laboratory

> This guide is for experienced software developers who want to deploy applications to OpenStack clouds. If you are familiar with OpenStack but have not created a cloud application in general or an OpenStack application in particular, this section teaches you how to program with OpenStack components. 
[Writing your first OpenStack application](http://developer.openstack.org/firstapp-shade/getting_started.html)


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
```