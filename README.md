# Installation of IIS Server

##  Project Overview 

Thriving in today's digital landscape requires a reliable and scalable web hosting environment. This project empowers you to achieve this by guiding you through the rapid deployment of an Internet Information Services (IIS) web server on a Microsoft Azure Virtual Machine (VM).

Leveraging the automation capabilities of Azure PowerShell, this step-by-step approach ensures a streamlined and error-free setup, saving you significant time and effort.

Whether you're a beginner in cloud computing or a seasoned professional, this project offers a valuable resource. It equips you to leverage Azure's powerful infrastructure for efficient web hosting.

### Project Goals

*  Automate Infrastructure Setup: Utilize Azure CLI to automate the creation and configuration of an Azure VM.
*  Web Server Deployment: Install and configure IIS, a widely-used web server, on the Azure VM.
*  Verification and Documentation: Verify the IIS installation by accessing the web server and documenting the entire process.

### Key Features

* Resource Group and VM Creation: Instructions on how to create a resource group and an Azure VM using Azure CLI.
* Port Configuration: Steps to open necessary ports to allow web traffic to the IIS web server.
* IIS Installation: Automated installation of IIS web server using PowerShell commands.
* Access and Verification: Methods to verify the IIS installation by accessing the web server via the VM's public IP address or localhost.
* Documentation: Detailed documentation of the entire process, including commands, screenshots, and descriptions, to facilitate easy replication and understanding.

### Prerequisites

* Azure CLI: Installed and configured on your local machine.
* Azure Account: Active subscription to Microsoft Azure.
* RDP Client: Ability to connect to the Azure VM using Remote Desktop Protocol.
* Git and GitHub: Basic knowledge of Git and a GitHub account to document and store the project files.

### Steps Covered

#### Before starting the project, I ensured the Azure PowerShell module was installed and authenticated to my Azure account before running the commands below.

- I logged in using Powershell CLI to authenticate and access Azure resources
  ```powershell
  Connect-AzAccount -TenantId "my tenenantId"
  ```
- I created a Resource Group that establishes a logical container for Azure resources.
  ```powershell
  New-AzResourceGroup -Name 'testRG' -Location 'EASTUS'
  ```
- Create a new Virtual Machine named testVM in the testRG resource group.
- Place it in the EastUS location.
- Associate it with the virtual network testVnet and subnet testSubnet.
- Attach a network security group named testNetworkSecurityGroup.
- Assign a public IP address named testPublicIpAddress.
- Open ports 80 and 3389 for HTTP and RDP access, respectively.
  
  ```PowerShell
  New-AzVm -ResourceGroupName "testRG"
  -Name "testVM"
  -Location "EastUS"
  -VirtualNetworkName "testVnet"
  -SubnetName "testSubnet"
  -SecurityGroupName "testNetworkSecurityGroup"
  -PublicIpAddressName "testPublicIpAddress"
  -Openports 80,3389
  ```
!["Alt Text"](C:\Users\Emmanuel\Pictures\Screenshots)
  
- Installed the IIS web server on the Azure VM using PowerShell
  ```PowerShell
  Install-WindowsFeature -name Web-Server -IncludeManagementTools
  ```
- I Verified the Installation Access on the IIS welcome page to confirm successful installation.
- Capturing and documenting the setup process in a GitHub README file, including a screenshot of the IIS welcome page.


### Benefits

- Clear and concise steps allow others to replicate the setup easily.
- Using Azure CLI and PowerShell scripts to automate the process reduces manual effort and minimizes errors.
- Provides hands-on experience with Azure services, command-line tools, and web server configuration.

### Conclusion

This project is a practical guide for individuals or teams looking to deploy a web server on Azure quickly. It combines the power of Azure's cloud infrastructure with the simplicity of command-line tools to create a scalable and easily manageable web hosting solution. The detailed documentation ensures the process is transparent and reproducible, making it a valuable resource for beginners and experienced professionals in cloud computing and web development.



