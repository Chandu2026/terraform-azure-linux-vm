# terraform-azure-linux-vm
Terraform project for provisioning Azure infrastructure including VNet, Subnet, NSG, Public IP, and Linux Virtual Machine with SSH connectivity.
# Terraform Azure Linux VM Deployment
## Project Overview

This project was created for learning and hands-on practice with Terraform and Microsoft Azure. The main goal of this project was to understand how Infrastructure as Code (IaC) works in real-world cloud environments by provisioning and managing Azure resources using Terraform.

The project was implemented using Visual Studio Code, Terraform, Azure CLI, and Microsoft Azure services.

---

## Technologies Used

- Terraform
- Microsoft Azure
- Azure CLI
- Visual Studio Code
- Linux (Ubuntu)
- SSH
- Infrastructure as Code (IaC)

---

## Azure Resources Created

The following Azure resources were provisioned using Terraform:

- Azure Resource Group
- Virtual Network (VNet)
- Subnet
- Public IP Address
- Network Interface Card (NIC)
- Network Security Group (NSG)
- Linux Virtual Machine (Ubuntu 22.04)
- SSH Connectivity

---

## Project Architecture

```text
Azure Resource Group
│
├── Virtual Network (10.0.0.0/16)
│   └── Subnet (10.0.2.0/24)
│
├── Network Security Group
│   └── Allow SSH (Port 22)
│
├── Public IP Address
│
├── Network Interface Card
│
└── Linux Virtual Machine (Ubuntu)
```

---

## Features

- Infrastructure provisioning using Terraform
- Azure cloud resource automation
- Secure SSH access configuration
- Public IP association with VM
- NSG rule configuration for SSH access
- Real-world cloud troubleshooting experience

---

## Challenges Faced and Resolved

### 1. VM SKU Availability Issue

Initially faced deployment failures because the selected VM size (`Standard_F2`) was unavailable in the selected Azure region.

### Solution

Verified supported VM sizes in Azure and updated the configuration to a supported VM SKU (`Standard_B2as_v2`).

---

### 2. Invalid Azure Region Configuration

Encountered errors due to incorrect Azure region naming in the Terraform configuration.

### Solution

Updated the configuration using valid Azure region identifiers supported by Azure.

---

### 3. Terraform Provider and Backend Errors

Faced dependency lock file issues and backend configuration problems during Terraform initialization.

### Solution

Removed corrupted Terraform cache and lock files, then reinitialized Terraform successfully.

---

### 4. Public IP Resource Configuration Error

Terraform attempted to use an invalid provider because of an incorrect Public IP resource declaration.

### Solution

Corrected the resource type from:

```hcl
resource "public_ip_address_id"
```

to:

```hcl
resource "azurerm_public_ip"
```

---

### 5. Azure Public IP SKU Limitation

Azure subscription restricted Basic SKU Public IP creation.

### Solution

Configured Standard SKU Public IP instead of Basic SKU.

---

### 6. Network Security Group (NSG) Configuration

SSH connection initially timed out because inbound port 22 was blocked.

### Solution

Created and associated a Network Security Group with an inbound SSH rule.

---

### 7. SSH Authentication Issues

Encountered SSH authentication failure due to using the public key instead of the private key.

### Solution

Used the correct private key for SSH access.

---

## Terraform Commands Used

### Initialize Terraform

```bash
terraform init
```

### Validate Terraform Configuration

```bash
terraform validate
```

### Preview Infrastructure Changes

```bash
terraform plan
```

### Apply Infrastructure

```bash
terraform apply
```

### Destroy Infrastructure

```bash
terraform destroy
```

---

## SSH Connectivity

Successfully connected to the Linux Virtual Machine using:

```bash
ssh -i C:/Users/CHANDU/.ssh/id_rsa adminuser@<public-ip>
```

---

## Learning Outcomes

Through this project, I gained practical hands-on experience with:

- Infrastructure as Code (IaC)
- Terraform configuration and state management
- Azure cloud resource provisioning
- Azure networking concepts
- Linux virtual machine deployment
- SSH authentication and remote access
- Cloud troubleshooting and debugging

---

## Screenshots

Add your screenshots here:
- Terraform Apply Output

<img width="1918" height="1078" alt="Screenshot 2026-05-18 232836" src="https://github.com/user-attachments/assets/1147f92e-2576-40af-8465-de2355d0176c" />

- Azure Portal Resources

<img width="1918" height="1078" alt="Screenshot 2026-05-19 000051" src="https://github.com/user-attachments/assets/33322f0e-957d-4e8d-a257-10e5d2412c73" />
- Successful SSH Connection

<img width="1918" height="1078" alt="Screenshot 2026-05-18 232825" src="https://github.com/user-attachments/assets/1a14768e-ea09-4b3c-a3ca-728e22fd38f2" />
- Visual Studio Code Configuration
 
<img width="1918" height="1078" alt="Screenshot 2026-05-18 232710" src="https://github.com/user-attachments/assets/3bd7220f-2dd0-48b0-bfcc-75d7b7795263" />
- Azure VM Overview

<img width="1918" height="1078" alt="Screenshot 2026-05-19 000122" src="https://github.com/user-attachments/assets/9ede8c65-7356-40fd-b7ea-9cb51c4f84e3" />

---

## Future Improvements

- Create reusable Terraform modules
- Configure remote backend using Azure Storage Account
- Add CI/CD pipeline integration
- Add monitoring and logging
- Deploy multi-tier architecture

---

## Author

CHILAKAPATI CHANDRA SEKHAR

---

## Connect With Me

LinkedIn: https://www.linkedin.com/in/chandra-sekhar-chilakapati-81024b383/ 
GitHub: https://github.com/Chandu2026/terraform-azure-linux-vm
