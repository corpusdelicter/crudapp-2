TechStack:
Container Runtime    : Docker
CI/CD                : Github Actions
Resource             : Azure App Services
Database             : Azure MySQL Service
Programming Language : Node.js


1. Infrastructure Setup
a. Azure App Service:
	-Sign in to Azure Portal
	-Create an App Service
	-Subscription: Choose/Create New.
	-Resource Group: Choose/Create New.
	-Name: Crudapp-2
	-Publish: Choose "Container".
	-Region: EAST US
	-Click "Review + create" and then "Create".



b. Azure SQL Database:
	-Go to "SQL Databases" and click "Create".
	-Fill in the necessary details:
	-Subscription: Choose/create new subcription
	-Resource Group: Choose/create new
	-Database Name: db-gratis
	-Servername: db-gratis.mysql.database.azure.com
	-Location: East US.
	-Click "Review + create" and then "Create".
	-Configure Firewall Rule: allow appservice ip to connect database

2. Application:
	 This Web application build by Node.js and support CRUD and it's containeraized. please check this url : https://crudapp-2.azurewebsites.net/

3. Security:
   -To control inbound/outbond traffic to Database, I already configured firewall to allow appservice to access this Database.
	 -Go to Azure Mysql Server --> Settings --> Networking --> Firewall Rule --> fill the appservice ip

4. CI/CD:
   -To configure Github Action:
	  Configure Github Action:
  		-Go to Github Repositories --> settings --> Secret and variables
  		-add and fill this variable:
  				-Azure_Credentials:
  	 			 Run this command to get azure credentials:
  	 				az ad sp create-for-rbac --name "yourapp" --role contributor --scopes /subscriptions/subscriptionID/resourceGroups/resourcegroupID --sdk-auth
  		-Azure_Webapp_name
  		-Registry_Username
  		-Regirstry_Password
  		-add folder .github/workflows
  		-add file deploy-to-azure.yml Please check this url : https://github.com/corpusdelicter/crudapp-2/blob/main/.github/workflows/deploy-to-azure.yml
