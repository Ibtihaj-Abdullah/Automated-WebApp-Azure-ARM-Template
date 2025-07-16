# Automated-WebApp-Azure-ARM-Template
This is a ARM Template code to deploy a basic app on Azure using App Service <br>

# Template Explanation 
▪ Code is pretty self-explanatory because of parameterization. The task of four service deployments namely Azure App Service, Azure SQL Database, Azure Storage Account and Vnet with a Subnet is done in the code <br>
▪ Tags are also defined in the code <br>
  • "Environment": "Test Project", <br>
  • "Owner": "Ebtihaj", <br>
  • "Project": "ARMDeployment" <br>
▪ Output for Website URL is also defined in the code which gives a visible output on CLI <br>
▪ The template was also parameterized rather than hardcoding the parameters in resources which gives flexibility <br>
▪ App Service category “Web App + Database” is chosen which removes the hassle of connecting DB to App Service. Flexible SQL Server service is chosen as engine as it is highly managed by Azure. <br>

# Challenge and resolution 
▪ Define an NSG deployment in the code to add two inbound traffic rules to allow traffic inbound at port 443 and port 80 (necessary to access the website through 
browsers). <br>
▪ Also parameterized the properties to allow custom service for all protocols.

# Task Steps 
# 1. Resource Group <br> 
  a. Create Resource group “armtask” using command  
    ▪ az group create –name “armtask” –location “Canada Central” 
# 2. Template Deployment  
  a. Create a new instance of Azure Cli and upload the arm1.json file which contains the template code 
  b. Run the following command to deploy the template 
    ▪ az deployment group create –resource-group “armtask” –template-file “arm1.json”
