## Day 1: Create SSH Key Pair for Azure Virtual Machine 

---

### Task parameters:
1. For this task, create an SSH key pair with the following requirements: 
2. The name of the SSH key pair should be nautilus-kp. 
3. The key pair type must be RSA.

### 1. Create local RSA key pair:

```bash 
ssh-keygen -t rsa -f ~/.ssh/nautilus-kp
```
### 2. Check the public key exists

```bash
ls -l ~/.ssh/nautilus-kp.pub
```

### 3. Check we are logged into Azure

```bash
showcreds
```

### 4. Add public key into Azure resource group

```bash
az sshkey create --resource-group "rg-grp" --name "nautilus-kp" --public-key "@~/.ssh/nautilus-kp.pub"
```

### 5. Verify it has been added into the resource group

```bash
az sshkey list --output table
```