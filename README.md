# azure-ansible
Create and destroy Linux VMs in Microsoft Azure

## Overview
This playbook was created to create and teardown Linux VMs in a specified Azure account. 
- Edit the vms.yml file to customize the names and count of VMs you wish to create or destroy
- The default user account for the vms is `ansible` and this playbook uses vault to store the password for the VMs.  Therefore, you will need to modify remove and recreate your own vault.
- role tags are being used for deployments and teardowns respectively.

## Examples
### Create new Linux VMs 
ansible-playbook site.yml --tags "deploy" --ask-vault-pass -e @vms.yml



## roles
- deploy - Create VMs and all required VM resources, i.e. Resource Group, Virtual Network, NIC, IP, Storage Account
- teardown - Destroy VMS and all required VM resources, i.e. Resource Group, Virtual Network, NIC, IP, Storage Account

## group_vars
### vars.yml
- username
- vmsize
- resource
### vault.yml
encypted 

### vms.yml example
```
---
  vmname:
     - linuxvm1
     - linuxvm2
     - linuxvm3
```



