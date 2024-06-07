# CI/CD Pipeline with Jenkins on AWS

## Step 1: AWS Account Login and EC2 Instance Creation

- **Login to AWS Account:** Access your AWS Management Console using your credentials.
  
- **Navigate to EC2 Dashboard:** Once logged in, locate the EC2 service from the AWS dashboard.
  
- **Launch Instance:** Click on the "Launch Instance" button to initiate the process of creating a new EC2 instance.
  
- **Choose an Amazon Machine Image (AMI):** Select the appropriate AMI based on your requirements. This could be a standard Linux or Windows image.
  
- **Choose Instance Type:** Choose the instance type based on your workload needs, considering factors like CPU, memory, storage, and networking capacity.
## Step 2: Installation of Java

1. **Update Package Repository:**
sudo apt update


2. **Install Java:**
sudo apt install default-jre


3. **Verify Java Installation:**
java -version


Expected Output:
openjdk version "17.0.8" 2023-07-18
OpenJDK Runtime Environment (build 17.0.8+7-Debian-1deb12u1)
OpenJDK 64-Bit Server VM (build 17.0.8+7-Debian-1deb12u1, mixed mode, sharing)


## Step 3: Weekly Release Installation

- **Download Jenkins Key:**
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/debian/jenkins.io-2023.key


- **Add Jenkins Repository:**
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian binary/" | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null


- **Update Package Repository:**
sudo apt-get update

- **Install Jenkins:**
sudo apt-get install jenkins
Jenkins is then installed using the apt package manager.

## Step 4: Jenkins Login and Project Repository Setup

- **Access Jenkins Web Interface:**
Open a web browser and navigate to the Jenkins URL. Typically, this would be `http://<your-ec2-instance-ip>:8080`.

- **Login to Jenkins:**
Enter your Jenkins credentials to log in to the Jenkins dashboard.

- **Install Recommended Plugins (Optional):**
Upon first login, Jenkins may prompt you to install recommended plugins. It's advisable to install these plugins for optimal functionality.

- **Create New Item:**
Click on the "New Item" link on the Jenkins dashboard to create a new project.

- **Enter Project Name:**
Give your project a descriptive name and select the appropriate project type (e.g., Freestyle project, Pipeline).

- **Configure Source Code Management (SCM):**
Choose your version control system (e.g., Git) and provide the repository URL of your project.

- **Set Build Triggers (Optional):**
Configure build triggers based on your requirements (e.g., poll SCM, webhook triggers).

- **Configure Build Steps:**
Define the build steps needed to build and deploy your project. This may include compiling code, running tests, and packaging artifacts.

- **Save and Apply Changes:**
Once you have configured the project settings, save your changes to create the project.

- **Run Build:**
Trigger the first build manually to verify that Jenkins can successfully fetch the source code from your repository and execute the build steps.

## Step 5: Deployment Execution Shell Command

- **Navigate to Project Configuration:**
Go to the configuration page of your Jenkins project.

- **Add Build Step:**
Scroll down to the build section of your project configuration and add a new build step.

- **Select Execute Shell:**
Choose "Execute shell" from the list of available build steps.

- **Write Deployment Script:**
Write the shell script that contains the commands required to deploy your project. This script will vary depending on your project type and deployment requirements.


