# Azure ARM Template - Multiple Virtual Machines Deployment

## Overview
This Azure Resource Manager (ARM) template facilitates the deployment of multiple virtual machines (VMs) in Azure. It automates the provisioning of virtual machines, associated storage accounts, a virtual network, and network interfaces. The template is designed for flexibility, allowing you to customize various parameters based on your specific requirements.

## Pre-requisites
Ensure you have the following prerequisites before deploying the ARM template:
* Azure Subscription: You must have an active Azure subscription.
* Azure CLI or Azure PowerShell: Choose either Azure CLI or Azure PowerShell for deploying the template.

## Parameters
The template uses the following parameters:
* storageAccountType: Type of storage account (e.g., Standard_LRS).
* vmName: Prefix for naming the virtual machines.
* vmAdminUserName: Administrator username for the virtual machines.
* vmAdminPassword: Administrator password for the virtual machines.
* vmWindowsOSVersion: Windows Server version for the virtual machines.
* containerCount: Number of blob containers within the storage account.

## Variables
The template defines the following variables:
* storageAccountName: Automatically generated storage account name.
* containerNames: Automatically generated names for blob containers.
* vnetPrefix: Virtual network address space.
* vnetSubnet1Name: Name of the first subnet.
* vnetSubnet1Prefix: Address prefix for the first subnet.
* vnetSubnet2Name: Name of the second subnet.
* vnetSubnet2Prefix: Address prefix for the second subnet.
* vmImagePublisher: Publisher of the VM image.
* vmImageOffer: Offer of the VM image.
* vmOSDiskName: Name of the OS disk for virtual machines.
* vmVmSize: Size of the virtual machines.
* vmNicName: Automatically generated network interface name.

## Resources
The ARM template deploys the following Azure resources:
* Storage Account: Creates a storage account with the specified type.
* Blob Containers: Creates the specified number of blob containers within the storage account.
* Virtual Network: Creates a virtual network with two subnets.
* Network Interfaces: Creates network interfaces for the virtual machines.
* Virtual Machines: Deploys multiple virtual machines based on the specified parameters.

## Deployment
Use either Azure CLI or Azure PowerShell to deploy the template:

### Example using Azure CLI 
> az deployment group create --resource-group <ResourceGroupName> --template-file DeployMultipleVMS_ARMTemplate.json --parameters DeployMultipleVMS_ARMTemplate.parameters.json

## Important Notes
* Ensure that you have the necessary permissions to deploy resources in the target Azure subscription and resource group.
* Review the parameters and modify them according to your requirements before deploying the template.
