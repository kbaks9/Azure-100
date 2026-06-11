## Day 2: Create an Azure virtual machine.

---

### Task parameters:
1.	Use the existing resource group.
2.	The VM name must be nautilus-vm, it should be in southcentralus region.
3.	Use the Ubuntu 24.04 LTS image for the VM.
4.	The VM size must be Standard_B1s.
5.	Attach a default Network Security Group (NSG) that allows inbound SSH (port 22).
6.	Attach a 30 GB storage disk of type Standard HDD.
7.	The rest of the configurations should remain as default.
8.	After completing these steps, make sure you can SSH into the virtual machine.

### 1. Checking the existing resource group:

```bash 
az group list --output table
```

### 2. Create the virtual machines with parameters:

```bash
az vm create --resource-group rg-grp1 --name nautilus-vm --location southcentralus --image Ubuntu2404 --size Standard_B1s --generate-ssh-keys --os-disk-size-gb 30 --storage-sku Standard_LRS --admin-username azureuser
```

### 3. Check IP address of the virtual machine:

```bash
az vm list-ip-addresses --resource-group rg-grp1 --name nautilus-vm --output table
```

### 4. Confirm by using SSH to access the virtual machine:

```bash
ssh azureuser@{real-public-ip}
```
