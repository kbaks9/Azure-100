## Day 3: Create VM using Azure CLI

---

### Task parameters:
1.	Create a new Azure Virtual Machine named datacenter-vm using the Azure CLI.
2.	Use the Ubuntu2204 image and set the VM size to Standard_B2s.
3.	Make sure the admin username is set to azureuser and SSH keys are generated for secure access.
4.	Use Standard_LRS storage account, disk size must be 30GB and ensure the VM datacenter-vm is in the running state after creation.

> `NOTE: Day 3 is quite similar to day 2.`

### 1. First, we check for the existing resource group:

```bash 
az group list –output table
```

### 2. Then we will set the parameters for the virtual machine: 

```bash 
az vm create --resource-group "kml_rg_main-62d7cbed840347e1" --name datacenter-vm --image "Ubuntu2204" --storage-sku Standard_LRS --os-disk-size-gb 30 --size Standard_B2s --generate-ssh-keys --admin-username azureuser
```

### 3. Then we will check it is in a running state:

```bash 
az vm list -d --output table
```

> `-d` means --show-details