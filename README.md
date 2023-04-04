# vmupgradeazure
<p align="center">
<img src="https://i.imgur.com/hbO1sQ3.png" alt="Azure Logo"/>
</p>

<h2>How To Upgrade Existing Microsoft VM in Azure</h2>

Hello, my name is Meshach Simotwo and I am a IT Professional. Today I will be teaching you how to upgrade an existing Microsoft server on Azure. I will be using [Learn.Microsoft.Com](https://learn.microsoft.com/en-us/azure/virtual-machines/windows-in-place-upgrade) to help me give a detailed step by step for upgrading.<br>

*<h3>If you do not have a Microsoft Azure subscription and are looking to obtaining one, check out my repository on it!. [How to get a Microsoft Azure Subscription](https://github.com/msimotwo/mszuresubscription)</h3>*

<h2>-Environments and Technologies Used-</h2>

- Microsoft Azure
- PowerShell
- 

<h2>-Quick How-To on making Resource Groups-</h2>

  - Making Resource Group's and Virtual Machines in Microsoft Azure!
    - Create a Resource Group and name it "VMsetup"
    - Create an Azure Virtual Machine Windows 10, 4 vCPUs
      - Name: "VMSetup1"
        - Username: "labuser" (for example/whatever you chose)
        - Password: "VMSetup123!" (for example/whatever you chose)

*<h3>Before you do an upgrade on a VM, review the upgrade requirements.</h3>*

<h2>Windows Versions that are not able for in-place upgrade</h2>
  
  - Windows Server 2012 Datacenter
  - Windows Server 2012 Standard
  - Windows Server 2008 R2 Datacenter
  - Windows Server 2008 R2 Standard

*<h3>A quick message from learn.microsoft.com</h3>*

*- The upgrade media provided by Azure requires the VM to be configured for Windows Server volume licensing. This is the default behavior for any Windows Server VM that was installed from a generalized image in Azure. If the VM was imported into Azure, then it may need to be converted to volume licensing to use the upgrade media provided by Azure. To confirm the VM is configured for volume license activation follow these steps to configure the appropriate KMS client setup key. If the activation configuration was changed, then follow these steps to verify connectivity to Azure KMS service.*
  
<h2>Instructions for upgrading</h2>
 
- The in-place upgrade of the VM requires the managed disks. Its okay, most VM's on Azure use managed disks. Managed disks are like the physical disk but on a virtual level.
- Windows recommends capturing a quick snapshot of the operating system disk and any other data disks on board. *This will enable you to revert to the previous state of the VM if anything fails during the in-place upgrade process.*

- To start an in-place upgrade the upgrade media must be attached to the VM as a Managed Disk. To create the upgrade media, modify the variables in the following PowerShell script for Windows Server 2022. The upgrade media disk can be used to upgrade multiple VMs, but it can only be used to upgrade a single VM at a time. To upgrade multiple VMs simultaneously multiple upgrade disks must be created for each simultaneous upgrade.
- Here is the [Link](https://docs.google.com/document/d/1u3_zoOUYfd8HIRGuitxRaUUYFao06YZ9O-6I9rl8kOs/edit?usp=sharing) for the PowerShell script. Easy copy and paste.
