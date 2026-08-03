# Project 01 – Secure Azure Network for Contoso Retail

## Project Summary

This project demonstrates how to design the foundational networking components for a secure Azure environment. It covers Resource Groups, Virtual Networks, Subnets, Network Security Groups, Infrastructure as Code, and automation using Azure CLI and Terraform.

## Business Requirement

Contoso Retail is migrating from an on-premises infrastructure to Microsoft Azure.
The first objective is to build a secure, scalable network foundation for future application deployment.

---

## Objectives

- [x] Create Resource Group
- [x] Create Virtual Network
- [x] Create Subnets
- [x] Configure Network Security Groups
- [ ] Configure NSG Rules
- [ ] Deploy using Azure Portal
- [ ] Deploy using Azure CLI
- [ ] Deploy using Terraform

---

## Azure Services Used

- Resource Group
- Virtual Network
- Network Security Group

---

## Current Network Design

- Virtual Network: 10.0.0.0/16
- Web Subnet: 10.0.1.0/24
- App Subnet: 10.0.2.0/24
- Database Subnet: 10.0.3.0/24

Each subnet has its own dedicated Network Security Group.

## Architecture

> Architecture diagram will be added after the networking components are deployed.

---

## Lessons Learned

*(We'll update this after each lab.)*

---

## Future Improvements

- Deploy using Bicep
- Add Azure Firewall
- Add Bastion
- Configure Route Tables
- Create Production Environment
