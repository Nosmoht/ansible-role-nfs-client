nfs-client
==========
- [Introduction](#introduction)
- [Requirements](#requirements)
- [Variables](#variables)
- [Usage](#usage)

# Introduction
Ansible role to install and configure NFS client.

# Requirements
Ansible

# Variables

| Name | Description | Default |
|:-----|:------------|:--------|
| nfs_client_package_name | Package name | nfs-utils |
| nfs_client_package_state | Package state | present |
| nfs_client_service_names | Service names | depends on __ansible_os_family__ and __ansible_distribution_major_version__ |
| nfs_client_service_state | Service state | running |
| nfs_client_service_enabled | Service enabled | true |
| nfs_client_mounts | List of dictionaries describing NFS mount points | [] |

# Usage
```yaml
---
- hosts: server
  vars:
    nfs_client_mounts:
    - src: nfs-server.example.com
      name: /mnt/nfs
      opts: rw,rsize=32768,wsize=32786      
  roles:
  - role: nfs-client
```