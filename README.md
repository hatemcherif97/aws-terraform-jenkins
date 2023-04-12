Terraform: How To Deploy Jenkins CI/CD Pipelines Using Terraform
===========
### Deploy an EC2 instance bootstrapped with a script to install and run Jenkins.
----------------

#### Resume

In this project, we would like to start using Jenkins as CI/CD tool to create pipelines for DevOps projects. We need to create the Jenkins server using Terraform so that it can be used in other environments and so that changes to the environment are better tracked.

##### step 1:
Export the aws credentiales into Terraform through “Environment Variables”.
 ```
export AWS_ACCESS_KEY_ID=<id>
export AWS_SECRET_ACCESS_KEY=<id>
export AWS_REGION=<region>
 ```
 ##### Step 2: Create Terraform Files
 Create Variables.tf file
 Create main.tf file
 
 ##### Step 3: Deploy our Infrastructure
 Firstly, run the command:
 ```
 terraform init
 ```
 terraform init downloads plugins needed to execute config files.
 Next run the command:
 ```
 terraform plan
 ``` 
 terraform plan creates an execution plan, listing resources that will be created based on the Terraform file.
 Finally run the command:
 ```
 terraform apply -auto-approve
 ```
 terraform apply creates the resource infrastructure as defined in the Terraform file.
 ##### Step 4: Verify Jenkins Deployment

SSH into your instance and run the following command to verify Jenkins has successfully been installed:
 ```
 sudo systemctl status jenkins
 ```
 Now we can access to Jenkins via a web browser
 ```
 http://<instance_ip>:8080
 ```
