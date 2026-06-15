## Day 6: Create a Subnet in Azure Virtual Network

---

### Task Parameters:
1. Create a Virtual Network (VNet) named devops-vnet 
2. One subnet named devops-subnet within the VNet in the eastus region.
3. Make sure the IPv4 address range is 10.0.0.0/16.

### 1. List the available resource groups:

```bash 
az group list –-output table
```

### 2. Create the virtual network:

```bash 
az network vnet create --resource-group kml_rg_main-c190e79958934222 --name devops-vnet --subnet-name devops-subnet --location eastus --address-prefixes 10.0.0.0/16
```

### 3. Verify that the VNet was created:

```bash 
az network vnet list --resource-group kml_rg_main-c190e79958934222 --output table
```

### Summary

Understanding VNet vs Subnet Address Spaces

A Virtual Network (VNet) defines the overall IP address space available for your Azure network.

For example:

```text
VNet: 10.0.0.0/16
```

A `/16` network contains **65,536 IP addresses**.

Subnets are smaller network segments created within the VNet address space. A subnet must fit entirely within the VNet's address range.

Example:

```text
VNet: 10.0.0.0/16

Subnet A: 10.0.1.0/24
Subnet B: 10.0.2.0/24
Subnet C: 10.0.3.0/24
Subnet D: 10.0.4.0/24
```

Each `/24` subnet contains **256 IP addresses** (251 usable in Azure, as Azure reserves 5 addresses per subnet).

By creating several `/24` subnets within a `/16` VNet, only a small portion of the available address space is used, leaving room for additional subnets in the future.

> **Note:** In this task, Azure automatically creates `devops-subnet` with a `/24` address range because no subnet prefix was explicitly specified.
