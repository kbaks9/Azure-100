## Day 4: Create a Virtual Network in Azure

---

### Task Parameters:
1.	Create a Virtual Network (VNet) named datacenter-vnet 
2.	In the eastus region
3.	Give it any IPv4 CIDR block.

### 1. List the available resource groups:

```bash 
az group list –output table
```

### 2. Create the virtual network:

```bash 
az network vnet create --resource-group rg-grp1 --name datacenter-vnet --location eastus --address-prefixes 10.0.0.0/16
```

### 3. Verify that the VNet was created:

```bash 
az network vnet list --resource-group rg-grp1 --output table
```

### Summary

A virtual network (VNet) is a private networking layer in the cloud that enables Azure resources (such as virtual machines) to securely communicate with each other, the internet, and on-premises networks.

It provides isolation and full control over IP addressing, subnets, routing, and network security. A VNet is similar to a traditional network in a physical data centre, but it is fully virtualised and managed within Azure.
