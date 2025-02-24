Step-by-Step Instructions:
1. Prepare Azure Environment
Create an Azure Account:

If you don't already have one, sign up for an Azure account.
Set Up Azure Resource Group:

Create a new Resource Group for your Jenkins server to manage resources cohesively.
Create a Virtual Network (VNet):

Set up a VNet with a public subnet for your Jenkins server.
Configure network security groups (NSGs) to allow necessary inbound traffic, such as SSH (port 22) and HTTP (port 80).
Set Up Azure Role and User:

Create a new Azure Role with permissions to manage Virtual Machines, Storage Accounts, Networking, and other necessary resources.
Create a Service Principal for accessing Azure resources programmatically, ensuring to save the client ID and secret securely.
2. Create and Configure Virtual Machine
Choose an Azure Image:

Select a suitable Linux-based image, such as Ubuntu 18.04 LTS or CentOS.
Create a Virtual Machine:

Use the Azure Portal or Azure CLI to create a new Virtual Machine (e.g., Standard B2s for a minimal setup).
Configure VM Settings:

Network Security Group (NSG):
Ensure the NSG allows inbound traffic on ports 22 (SSH) and 8080 (Jenkins).
Attach Public IP:
Assign a Static Public IP to the VM for consistent accessibility.
Connect to the VM:

Use SSH to connect to your Virtual Machine.
3. Install Jenkins
Update Package Manager:

Update your package repositories to ensure you have the latest listings.
Install Java:

Jenkins requires Java. Use the package manager to install OpenJDK.
Add Jenkins Repository:

Add the Jenkins repository to your package manager.
Install Jenkins:

Use your package manager to install Jenkins.
Start Jenkins Service:

Enable and start the Jenkins service.
Adjust Firewall Rules:

Ensure the Azure NSG and VM firewall allow traffic to relevant ports (8080 for Jenkins).
4. Initial Jenkins Setup
Access Jenkins Web Interface:

Open your web browser and navigate to http://<Your-VM-Public-IP>:8080.
Unlock Jenkins:

Retrieve the initial admin password from /var/lib/jenkins/secrets/initialAdminPassword on your VM.
Enter the password on the Jenkins web interface to unlock Jenkins.
Customize Jenkins:

Install suggested plugins.
Create an admin user and complete the setup.
5. Configure Jenkins for Optimal Use
Install Essential Plugins:

Install plugins such as Git, Pipeline, Azure Credentials, and other necessary tools.
Configure Global Tool Configuration:

Set up tools like Git and JDK in the Jenkins configuration.
Set Up Credentials:

Add Azure Service Principal credentials to Jenkins Credentials for accessing Azure resources.
Create and Manage Jobs:

Create a new job using the pipeline or freestyle project.
Configure build steps to execute your sample script (e.g., a simple Python script).
6. Ensure Security and Maintenance
Enable Automatic Backups:

Set up scheduled jobs to back up Jenkins configurations and jobs to an Azure Storage Account.
Enable Monitoring:

Use Azure Monitor to keep track of Jenkins server performance and logs.
Regular Updates:

Regularly update Jenkins and its plugins to the latest versions.
Final Steps
Documentation:

Document every step in a markdown file named azurejenkins-setup.md.
Commit and Push:

Add the markdown file to your repository.
Commit with a descriptive message and push to the remote repository.
Pull Request:

Create a pull request to merge your changes into the main branch.
By following these steps, you will set up a robust and scalable Jenkins server on Azure, ready for continuous integration tasks and handling competitive programming test cases.
