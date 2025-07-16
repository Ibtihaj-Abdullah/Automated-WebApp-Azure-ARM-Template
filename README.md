# Automated-WebApp-Azure-ARM-Template
This is an ARM Template code to deploy a basic app on Azure using App Service.

# Template Explanation
* Code is pretty self-explanatory because of parameterization. The task of four service deployments, namely Azure App Service, Azure SQL Database, Azure Storage Account, and VNet with a Subnet, is done in the code.
* Tags are also defined in the code:
    * "Environment": "Test Project"
    * "Owner": "Ebtihaj"
    * "Project": "ARMDeployment"
* An output for Website URL is also defined in the code which gives a visible output on CLI.
* The template was also parameterized rather than hardcoding the parameters in resources, which gives flexibility.
* App Service category "Web App + Database" is chosen, which removes the hassle of connecting DB to App Service. Flexible SQL Server service is chosen as the engine as it is highly managed by Azure.

# Challenge and Resolution
* Define an NSG deployment in the code to add two inbound traffic rules to allow traffic inbound at port 443 and port 80 (necessary to access the website through browsers).
* Also parameterized the properties to allow custom service for all protocols.

# Task Steps
## 1. Resource Group
   a. Create Resource group "armtask" using command:
      ```bash
      az group create --name "armtask" --location "Canada Central"
      ```
## 2. Template Deployment
   a. Create a new instance of Azure CLI and upload the `arm1.json` file which contains the template code.
   b. Run the following command to deploy the template:
      ```bash
      az deployment group create --resource-group "armtask" --template-file "arm1.json"
      ```
## 3. Post Deployment
   a. Open Policy resource in Azure.
   b. Search for the definition named "Require a tag and its value on resources."
   c. Assign this policy to scope:
      * Subscription: Azure Students
      * Resource Group: armtask
