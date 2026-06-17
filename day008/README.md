## Day 8: Attach Managed Disk to Azure Virtual Machine

### Task parameters:
1. An existing VM named devops-vm and a managed disk named devops-disk already exist in the centralus region.
2. Attach the disk devops-disk to the VM devops-vm as a data disk.
3. Ensure the disk is attached to the VM devops-vm.
4. Make sure that the virtual machine initialization has been completed before submitting this task.

### 1. Check resource group exists:

```bash 
az group list --output table
```

### 2. Confirm VM + disk exists: 

```bash 
az resource list --output table
```

### 3. Attach disk:

```bash 
az vm disk attach --vm-name devops-vm --name devops-disk --resource-group kml_rg_main-4656c21615154d6f
```

### 4. Verify disk attached to vm:

```bash 
az disk show --name devops-disk --resource-group kml_rg_main-4656c21615154d6f --query managedBy
```

### 5. Verify VM shows disk is attached:

```bash
az vm disk list --resource-group kml_rg_main-4656c21615154d6f --vm-name devops-vm -o table
```
