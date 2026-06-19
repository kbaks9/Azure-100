## Day 9: Attach Network Interface Card (NIC) to Azure Virtual Machine

### Task parameters:
1. An existing VM named devops-vm and a network interface named devops-nic already exist in the westus region.
2. Attach the network interface devops-nic to the VM devops-vm.
3. Ensure the NIC's status is attached before submitting the task.
4. Make sure that the virtual machine initialization has been completed before submitting this task.


### 1. Check resource group exists:

```bash 
az group list --output table
```

### 2. Confirm resources within resource group exists: 

```bash 
az resource list --resource-group kml_rg_main-c3e9b0d8b8ab4905 --output table
```

### 3. Check if NIC is attached to VM:

```bash 
az vm nic list --resource-group kml_rg_main-c3e9b0d8b8ab4905 --vm-name devops-vm
```

### 4. Stop and deallocate VM:
```bash 
az vm deallocate --resource-group kml_rg_main-c3e9b0d8b8ab4905 --vm-name devops-vm
```

### 5. Attach NIC to VM: 

```bash
az vm nic add  --resource-group kml_rg_main-c3e9b0d8b8ab4905 --vm-name devops-vm --nics devops-nic
```

### 6. Start VM again:

```bash
az vm start --resource-group kml_rg_main-c3e9b0d8b8ab4905 --name devops-vm
```

### 7. Verify NIC is attached:

```bash
az vm nic list --resource-group kml_rg_main-c3e9b0d8b8ab4905 --vm-name devops-vm --output table
```

> Replacing `--resource-group` & `--vm-name` with `-g` & `-n` going forwards from here.