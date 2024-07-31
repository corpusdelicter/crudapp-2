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


