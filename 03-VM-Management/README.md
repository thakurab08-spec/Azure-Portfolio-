
# Project 03 — Azure VM Deployment & Management

## Overview
Deployed and managed Windows and Linux virtual machines in Azure,
configured high availability using Availability Sets, implemented
secure access via Azure Bastion, created snapshots for backup,
and configured auto-shutdown for cost management.

## What I built

| Component | Details |
| Windows VM | vm-windows-01 — Windows Server 2022, Standard_B1s |
| Linux VM | vm-linux-01 — Ubuntu 22.04 LTS, Standard_B1s |
| Availability Set | avset-vm-lab — 2 fault domains, 5 update domains |
| Secure access | Azure Bastion (Basic tier) — no public RDP/SSH |
| Backup | Snapshot of Windows VM OS disk |
| Cost control | Auto-shutdown at 19:00 GMT with email alert |
| Region | North Europe |

---

## Step-by-step — what I did

### 1. Created Resource Group and VNet
- rg-vm-lab resource group in North Europe
- vnet-vm-lab with subnet-vms (10.0.1.0/24) for VM connectivity

### 2. Deployed Windows Server VM
- Windows Server 2022 Datacenter, Standard_B1s size
- No public IP — access via Bastion only
- Standard HDD OS disk for cost efficiency

### 3. Deployed Linux VM
- Ubuntu Server 22.04 LTS, Standard_B1s
- Same VNet and subnet as Windows VM
- Password authentication configured

### 4. Configured Availability Set
- Created avset-vm-lab with 2 fault domains and 5 update domains
- In production: VMs assigned at creation time to ensure
  Azure places them in separate physical racks
- Protects against hardware failure and planned maintenance

### 5. Set up Azure Bastion for secure access
- Deployed Bastion Basic tier in dedicated AzureBastionSubnet
- Connected to Windows VM via browser-based RDP session
- No RDP (3389) or SSH (22) ports exposed publicly
- Best practice for production VM access

### 6. Created VM snapshot
- Point-in-time snapshot of Windows VM OS disk
- Used for backup before configuration changes
- Can be used to restore or clone the VM

### 7. Configured Auto-shutdown
- Both VMs set to auto-shutdown at 19:00 GMT
- Email notification enabled before shutdown
- Prevents unexpected charges from forgotten running VMs

---

## Screenshots

| Step | Screenshot |
|---|---|
| Resource group | ![RG](screenshots/01-resource-group.png) |
| Windows VM deployed | ![Win](screenshots/02-vm-windows.png) |
| Linux VM deployed | ![Linux](screenshots/03-vm-linux.png) |
| Both VMs running | ![Both](screenshots/04-both-vms-running.png) |
| Availability Set | ![AvSet](screenshots/05-availability-set.png) |
| Bastion connection | ![Bastion](screenshots/06-bastion-connection.png) |
| VM Snapshot | ![Snap](screenshots/07-snapshot.png) |
| Auto-shutdown | ![Shutdown](screenshots/08-auto-shutdown.png) |
| Cleanup complete | ![Clean](screenshots/09-cleanup.png) |

---

## Key concepts demonstrated
- VM deployment — Windows and Linux side by side
- VM sizing — choosing right size for workload and cost
- Availability Sets — fault domains vs update domains
- Azure Bastion — secure access without public IP exposure
- Snapshots — point-in-time disk backup
- Auto-shutdown — cost management best practice
- No public RDP/SSH — security best practice

---

## AZ-104 domains covered
- Domain 3: Deploy and manage Azure compute resources
  - Create and configure VMs
  - Configure VM availability (Availability Sets)
  - Configure VM networking and secure access
  - Manage VM disks and snapshots
