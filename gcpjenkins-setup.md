Step-by-Step Instructions:
1. Prepare GCP Environment
Create a GCP Account:

Sign up for a Google Cloud account if you do not already have one.
Set Up a Project:

Create a new project in the GCP Console to organize your resources.
Set Up Service Account:

Navigate to IAM & Admin > Service accounts.
Create a new service account with Editor role for managing resources.
Create and securely save the JSON key file for this service account.
2. Create and Configure VM Instance
Create a VM Instance:

From the GCP Console, go to Compute Engine > VM instances.
Click "Create Instance" to set up a new VM.
Configure VM Settings:

Choose Machine Type:
A standard machine type such as n1-standard-1 should be adequate for a basic setup.
Choose an OS Image:
Use an appropriate Linux distribution (e.g., Ubuntu 18.04 LTS or Debian).
Firewall:
Allow HTTP (port 80) and HTTPS (port 443) traffic.
Allow inbound traffic on port 8080 (default Jenkins port) and port 22 (SSH).
Add Storage:

Typically, an 8-10 GB boot disk should be sufficient for Jenkins installation. Adjust if needed.
Connect to the VM:

After the VM is created, connect to it using SSH from the GCP Console.
3. Install Jenkins
Update System Packages:

Update the package listings on your VM.
Install Java:

Jenkins requires Java. Install OpenJDK using the package manager.
Add Jenkins Repository:

Add the Jenkins repository to your system's package manager.
Install Jenkins:

Install Jenkins via the package manager.
Start Jenkins Service:

Enable and start the Jenkins service to run it automatically after system startup.
Adjust Firewall Rules:

Ensure the VM firewall and GCP firewall rules allow traffic to relevant ports (8080 for Jenkins).
4. Initial Jenkins Setup
Access Jenkins Web Interface:

Open your web browser and navigate to http://<Your-VM-Public-IP>:8080.
Unlock Jenkins:

Retrieve the initial admin password from /var/lib/jenkins/secrets/initialAdminPassword on your VM.
Enter the password on the Jenkins web interface to unlock Jenkins.
Customize Jenkins:

Install suggested plugins.
Create an admin user and complete the initial setup wizard.
5. Configure Jenkins for Optimal Use
Install Essential Plugins:

Install necessary plugins such as Git, Pipeline, GCP Credentials, etc.
Configure Global Tool Configuration:

Set up necessary tools like JDK and Git.
Set Up Credentials:

Add the GCP service account credentials to Jenkins Credentials for accessing GCP resources.
Create and Manage Jobs:

Create a new job using the pipeline or freestyle project.
Configure build steps to execute your sample script (e.g., a simple Python script).
6. Create a Sample Job
Create Jenkins Job:

In Jenkins, create a new freestyle or pipeline project.
Define the project source control (e.g., Git repository URL).
Configure Build Steps:

Add build steps to execute your sample file (e.g., shell script to run a Python file).
Set the job to display output on job completion.
Test Job:

Run the job to ensure it builds and executes successfully, displaying the expected output.
7. Commit Changes
Document Setup Steps:

Document all steps performed in a markdown file named gcpjenkins-setup.md.
Create a New Branch:

Create a Git branch named feature-gcp-jenkins.
Commit and Push:

Add the gcpjenkins-setup.md file to your Git repository.
Commit with a clear, descriptive message.
Push the branch to the remote repository.
By following these detailed steps, you will have a Jenkins server set up on GCP ready for continuous integration tasks, capable of handling competitive programming test cases effectively.
