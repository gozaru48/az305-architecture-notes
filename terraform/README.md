# Terraform Practice: VNet, Subnet, and Virtual Machine Deployment

This directory contains a simple Terraform configuration used as part of my preparation for the Microsoft AZ-305 certification.  
It demonstrates how to deploy a virtual network, subnet, and a virtual machine in Microsoft Azure using Infrastructure as Code (IaC) principles.

## Objective

To gain hands-on experience with Terraform for designing and deploying core Azure infrastructure in a reproducible and scalable way.

## Resources Deployed

- Azure Resource Group
- Virtual Network (VNet)
- Subnet
- Public IP Address
- Network Interface Card (NIC)
- Ubuntu Linux Virtual Machine

## File Structure

- `main.tf`: Core Terraform configuration
- `variables.tf`: Input variables for flexible deployment
- `outputs.tf`: Outputs such as public IP address
- `terraform.tfvars`: (Optional) Predefined variable values

## Sample Snippet (main.tf)

```hcl
resource "azurerm_virtual_network" "vnet" {
  name                = "vnet-demo"
  address_space       = ["10.0.0.0/16"]
  location            = azurerm_resource_group.rg.location
  resource_group_name = azurerm_resource_group.rg.name
}
