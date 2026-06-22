## Day 12: Add and Manage Tags for Azure Virtual Machines

### Task parameters:
1. Add the tag Environment=dev to the virtual machine named datacenter-vm. 

### 1. Check resource group exists:

```bash 
az group list –output table
```

### 2. Check existing resources:

```bash 
az resource list –output table
```

### 3. Set tag to VM:

```bash 
az vm update -n datacenter-vm -g kml_rg_main-d9522f33f83b4c82 --set tags.Environment=dev
```
