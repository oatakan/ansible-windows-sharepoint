# ansible-windows-sharepoint
Ansible playbooks to install Microsoft SharePoint

### Requirements

* sharepoint media downloaded and available (see the variables section below)

### Variable

* Define the following variables in a file passed in using `-e @extra_vars.yml`

```yaml
---
# infra only, vmware or ovirt
provider: vmware #vmware or ovirt

# infra only, multi-node or single-node
deployment: multi  #multi or standalone

# path to MS SQL Server 2016/2019 iso file
mssql_iso_path: \\X.X.X.X\iso\SQLServer2016SP1-FullSlipstream-x64-ENU-DEV.iso

# path to sharepoint media
sharepoint_img_path: \\X.X.X.X\iso\sharepoint_2019.img

# path to sharepoint language pack
sharepoint_language_pack_path: \\X.X.X.X\iso\packages\sp2019\serverlanguagepack.exe

# sharepoint product key
sharepoint_product_key: XXXXX-XXXXX-XXXXX-XXXXX-XXXXX


```

### Run the playbooks:

* Optional: Deploy infra (i.e. VMware VMs):

```bash
ansible-playbook instance_create.yml -e @extra_vars.yml
```

* Provision SharePoint:

```bash
ansible-playbook provision-sharepoint.yml -e @extra_vars.yml
```