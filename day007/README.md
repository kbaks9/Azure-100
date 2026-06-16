## Day 7: Create a Public IP Address for Azure VM

---

### Task parameters:
1. Allocate a public IP Address, name it datacenter-pip.

### 1. Check what resource groups are available:

```bash 
az group list --output table
```

### 2. Create public IP Address within resource group:

```bash
az network public-ip create --resource-group rg-grp1 --name datacenter-pip
```

### 3. Verify public IP address has been created:

```bash
az network public-ip list --output table
```