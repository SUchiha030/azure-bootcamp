# Project 01 - Secure Azure Network for Contoso Retail

## Project Goal

The goal of this project is to build the networking foundation of an Azure environment for a fictional company called Contoso Retail. This project focuses on understanding Azure networking concepts before deploying workloads.

---

# Module 1 - Resource Groups

## What is a Resource Group?

A Resource Group (RG) is a logical container that holds Azure resources related to the same project or application.

Examples of resources:
- Virtual Machines
- Virtual Networks
- Storage Accounts
- Network Security Groups
- Databases

Deleting a Resource Group deletes all resources inside it.

### Why Resource Groups?

- Better organization
- Easier management
- Simplified deployment
- Easier cleanup
- RBAC can be applied at the Resource Group level

---

# Azure Regions

An Azure Region is a geographical location where Microsoft has one or more datacenters.

Examples:
- Central India
- South India
- East US
- West Europe

Choosing the correct region helps reduce latency, meet compliance requirements, and improve availability.

For this project, Central India was selected.

---

# Naming Convention

Resources were named using a consistent naming standard.

Examples:

Resource Group:
rg-contoso-dev-001

Virtual Network:
vnet-contoso-dev-001

Network Security Groups:
nsg-web-001
nsg-app-001
nsg-db-001

Consistent naming makes environments easier to manage.

---

# Tags

Tags are metadata attached to Azure resources.

Tags used:

- Project = Azure Bootcamp
- Environment = Dev
- Owner = Veerta
- CostCenter = Learning

Benefits:
- Cost tracking
- Organization
- Automation
- Governance

---

# Module 2 - Virtual Networks

## What is a Virtual Network?

A Virtual Network (VNet) is Azure's private network.

It allows Azure resources to communicate securely with:
- Other Azure resources
- On-premises networks
- Other VNets

The VNet created:

vnet-contoso-dev-001

Address Space:

10.0.0.0/16

---

# CIDR

CIDR (Classless Inter-Domain Routing) defines the size of a network.

Examples:

10.0.0.0/16 → Large network

10.0.1.0/24 → Smaller subnet

The /16 network was divided into multiple /24 subnets.

---

# Subnets

Subnets divide a Virtual Network into smaller logical segments.

Created subnets:

Web Subnet
10.0.1.0/24

Application Subnet
10.0.2.0/24

Database Subnet
10.0.3.0/24

Benefits:
- Better security
- Better organization
- Easier traffic control
- Easier scaling

---

# Default Subnet

Azure creates a Default Subnet automatically when creating a VNet through the portal.

For production-style environments, it is common to replace it with purpose-specific subnets.

---

# Module 3 - Network Security Groups

## What is an NSG?

A Network Security Group (NSG) filters inbound and outbound network traffic.

Rules are based on:
- Source
- Destination
- Port
- Protocol
- Direction

Created NSGs:

nsg-web-001

nsg-app-001

nsg-db-001

Each NSG was associated with its respective subnet.

---

# NSG vs Azure Firewall

Network Security Group

- Filters traffic using IPs, ports and protocols
- Applied to Subnets or Network Interfaces
- Lightweight security

Azure Firewall

- Managed firewall service
- Centralized security
- Supports application rules
- URL/FQDN filtering
- Threat Intelligence
- Logging

In enterprise environments both services are commonly used together.

---

# Network Watcher

Azure automatically creates NetworkWatcherRG when Network Watcher is enabled.

Purpose:

- Diagnose network problems
- Connection troubleshooting
- IP Flow Verify
- Packet Capture
- NSG Flow Logs

This resource group is Microsoft-managed and should generally not be deleted.

---

# Current Architecture

Resource Group

↓

Virtual Network (10.0.0.0/16)

↓

Web Subnet (10.0.1.0/24)

↓

Application Subnet (10.0.2.0/24)

↓

Database Subnet (10.0.3.0/24)

↓

Each subnet protected by its own Network Security Group

---

# Key Learnings

- Resource Groups logically organize Azure resources.
- Virtual Networks provide private networking inside Azure.
- Subnets divide a VNet into smaller network segments.
- CIDR notation defines network size.
- Network Security Groups secure network traffic.
- Azure Firewall provides advanced centralized protection.
- Network Watcher helps troubleshoot Azure networking.
- Proper planning makes cloud environments easier to manage.

---

# Interview Questions

1. What is a Resource Group?

2. What is the difference between a VNet and a Subnet?

3. What is CIDR?

4. Why use separate subnets?

5. Difference between NSG and Azure Firewall?

6. What is Network Watcher?

7. What happens when a Resource Group is deleted?

8. Why are Tags important?

9. Why shouldn't databases be placed in the same subnet as web servers?

10. Can resources inside one Resource Group exist in different Azure regions?

