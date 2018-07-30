# Ansible Cloud: Volume role

An Ansible role for managing volumes on the Cloud in an agnostic cloud provider way.

This role is part of the [ansible-cloud](https://github.com/redhat-cip/ansible-cloud) broader effort.

## Pre-requisites

Please refer to [ansible-cloud](https://github.com/redhat-cip/ansible-cloud) [README.md](https://github.com/redhat-cip/ansible-cloud/blob/master/README.md) to see how to configure your system the proper way for the provide you wish to use.


## Role Variables

| Variable name               | Required  | Default | Type   | Description                     |
|-----------------------------|-----------|---------|--------|---------------------------------|
| cloud_volume_name           | True      | N/A     | String | Name of the volume              |
| cloud_volume_size           | True      | N/A     | Int    | Size of the volume              |
| cloud_volume_region         | True      | N/A     | String | Region where the volume is      |
| cloud_volume_state          | False     | present | String | Should the volume be present    |


## Example

```
---
- hosts: localhost
  vars:
    ansible_cloud_provider: openstack
  tasks:
    - name: Create volume
      include_role:
        name: cloud-volume
      vars:
        cloud_volume_name: ansiblecloud-testvolume
        cloud_volume_size: 20
        cloud_volume_region: regionOne
```


## License

Apache 2.0


## Authors Information

  - Ricardo Carrillo Cruz <ricarril@redhat.com>
  - Yanis Guenane <yguenane@redhat.com>
