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