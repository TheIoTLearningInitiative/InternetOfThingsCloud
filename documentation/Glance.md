# Glance

> The Glance project provides a service where users can upload and discover data assets that are meant to be used with other services. This currently includes images and metadata definitions. Glance image services include discovering, registering, and retrieving virtual machine images. Glance has a RESTful API that allows querying of VM image metadata as well as retrieval of the actual image. VM images made available through Glance can be stored in a variety of locations from simple filesystems to object-storage systems like the OpenStack Swift project. [Glance](http://docs.openstack.org/developer/glance/)

- Metadata
  - OS Type
  - Size
  - Format

- Architecture
  - glance-api
  - glance-regustry
  - Database
  - Image Store

- Image Formats
  - ISO
  - QCOW2
  - Raw
  - VDI
  - VHD
  - VMDK
  - AKI
  - AMI
  - ARI
  - OVF

- Creating Nova Instance from an Image
  - vda
  - vdb
  - vdc

- Image Status
  - Queued
  - Saving
  - Active
  - Killed
  - Deleted
  - Pending_Delete

- Image members and sharing concept
  - public-images
  - my-owned-images
  - images-of-which-i-am-a-member

# Glare

> Going beyond storing just VM images
> Based on Glance v2 API and supports different artifacts types, like containers, various templates, application packages, and not just VM images only
> Support for community App catalog, Collection of Ready-to-use applications
> > Murano Packages
> > Heat Templates
> Experimental Phase 

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