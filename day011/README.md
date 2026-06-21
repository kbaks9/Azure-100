## Day 11: Change Azure Virtual Machine Size Using Console

### Task parameters:
1. Change the VM size from Standard_B1s to Standard_B2s for the virtual machine named xfusion-vm.
2. Ensure the VM is in the running state after the size change is complete.

### 1. Check existing resource groups:

```bash 
az group list --output table
```

### 2. Check existing resources:

```bash 
az resource list --output table
```

### 3. Resize the VM:
```bash 
az vm resize -g kml_rg_main-205cfbd45b3d467d -n xfusion-vm --size Standard_B2s
```

### 4. Verify VM is running after resize:

```bash 
az vm show -g kml_rg_main-205cfbd45b3d467d -n xfusion-vm -d --output table
```
