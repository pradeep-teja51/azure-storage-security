# Azure Storage Account Firewall & Private Endpoint Lockdown

A secure Azure Blob Storage architecture designed to prevent public access and allow storage connectivity through a private network path.

## Project Overview

This project demonstrates how Azure Storage can be secured using network isolation, Private Endpoints, Private DNS, firewall restrictions, Azure Policy, and security hardening.

The project was implemented and tested using Azure for Students.

## Architecture

```text
Internet / Public Client
          |
          | Public access
          ↓
   Azure Storage Account
   Public Network: Disabled
          |
          |
     Private Endpoint
          |
          ↓
   Private DNS Zone
privatelink.blob.core.windows.net
          |
          ↓
   Virtual Network
   10.0.0.0/16
          |
          ├── Private Endpoint Subnet
          |      10.0.1.0/24
          |
          └── Test Client Subnet
                 10.0.2.0/24
                      |
                      ↓
               Ubuntu Test VM
