## Day 10: Attach Public IP to Azure Virtual Machine

### Task parameters:
1. An existing VM named devops-vm-pip and a public IP address named devops-pip already exist.
2. Attach the public IP devops-pip to the network interface of the VM devops-vm-pip.
3. Make sure the VM is properly assigned the public IP.

### 1. Check Existing Resource Groups:

```bash 
az group list --output table
```

### 2. Check Existing NIC IP Configuration: 

```bash 
az network nic ip-config list --resource-group kml_rg_main-6aa39f24e47e427a --nic-name devops-vm-pipVMNic --output table
```

### 3. Attach the Public IP to the VM NIC: 

```bash 
az network nic ip-config update --resource-group kml_rg_main-6aa39f24e47e427a --nic-name devops-vm-pipVMNic --name ipconfigdevops-vm-pip --public-ip-address devops-pip
```

### 4. Verify the Public IP Assignment: 

```bash 
az vm list-ip-addresses --name devops-vm-pip --resource-group kml_rg_main-6aa39f24e47e427a --output table
```

