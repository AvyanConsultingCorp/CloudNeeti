# Getting started with CloudNeeti VM for Azure Marketplace

This article describes how to Automate Governance, Compliance, Reliability and Risk Monitoring for an enterprise using Azure

To deploy CloudNeeti VM from the Azure Marketplace:

1. Log in to the  [Microsoft Azure portal](https://portal.azure.com/).
2. Click Marketplace or click Browse &gt; in the left side navigation, and select Marketplace from the list.
3. In Click the Security + Identity blade and search for CloudNeeti Enterprise.
4. Click CloudNeeti Enterprise
5. In the CloudNeeti Enterprise blade, in Select a deployment model, select Resource Manager.
6. Click Create. The Create virtual machine and Basics blades appear.
7. On the Basics blade, complete the following fields:
    * Name: Type a descriptive name for your virtual machine.
    * VM disk type: Select disk type SSD or HDD
    * User name: Type a user name for logging in to your virtual machine
    * Password: Enter password for logging in to your virtual machine
    * Confirm password: Enter the same password for confirmation
    * Subscription: Select the subscription under which to create your virtual machine
    * Resource group: Specify the resource group to contain all your CloudNeeti VM resources. You can create a new resource group or select an existing resource group
    * Location: Select an Azure region from the Location list
    * Click OK

8. On the Choose a size blade, select a size and pricing tier for your virtual machine, and click Select.
9. On the Settings blade, review the preconfigured values for each field, and click OK. Most fields have additional settings that are not displayed on the Settings  To see all settings, expand each field. after validation, review the Summary information, and then click OK.
10. On the Purchase blade, review the offer details, Terms of use, privacy policy, and Azure Marketplace Terms and then click Purchase. The deployment is submitted
11. It will take approximately 8-10 minutes before your new virtual machine is running
12. When installation is complete, we need to configure certain parameters to open the application, follow below mentioned steps
    * Go to left pane of [Microsoft Azure portal](https://portal.azure.com/) click on Resource Group and find for resource group which is created above under your subscription
    * Then go to virtual machine by clicking the value in Public IP address / DNS name label in the Settings blade set the DNS name. Note the DNS Name you specified it would be \*&lt;DNSname&gt;.&lt;region&gt;.cloudapp.azure.com.  
     \*it will be the Azure region / location which you have selected for creating VM
    * In order to get an access to the CloudNeeti application you must set up an Azure Active Directory (AD) application and assign the required permissions to it Refer [Azure Active Directory application](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal)
    - Create new application id
    - Note application ID and authentication key (password), which you require to enter for registration to CloudNeeti
    - Update Reply URL with DNS name created above                           &lt;DNSname&gt;.&lt;region&gt;.cloudapp.azure.com. 
    - Add API access under required permissions
      - Microsoft Graph
      - Windows Azure Service Management API
      - Azure.ActiveDirectory
    - To access resources in your subscription, you must assign the application to a role refer [Assign application to role](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal#assign-application-to-role)

13. Update Network Security Group rules you must create rules that allow inbound for communication for the CloudNeeti application refer [Opening ports to a VM](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/nsg-quickstart-portal)

1. After you finish these steps, you are ready with CloudNeeti Application, open a browser and go to **:** &lt;DNSname&gt;.&lt;region&gt;.cloudapp.azure.com