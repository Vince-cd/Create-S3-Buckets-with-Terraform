<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Create S3 Buckets with Terraform

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-terraform1)

**Author:** Vince Gayatgay  
**Email:** vincegayatgay132@gmail.com

---

![Image](http://learn.nextwork.org/curious_teal_bold_lulo/uploads/aws-devops-terraform1_9i0j1k2l)

---

## Introducing Today's Project!

In this project, I will demonstrate how to install and configure Terraform, set up AWS credentials in the terminal, and use Terraform to create and manage S3 buckets. The goal is to show how infrastructure can be defined as code by provisioning cloud resources in a repeatable and automated way. 

By the end of this project, you’ll see how to upload files to Amazon S3 using Terraform and understand how these tools work together to streamline cloud deployment and management.

### Tools and concepts

Services I used were AWS S3 for storing files and AWS CLI for managing credentials and interacting with AWS. Key concepts I learned include Infrastructure as Code (IaC), which allows you to define and manage infrastructure through code, as well as how to use Terraform to provision, plan, and apply cloud resources in a repeatable and automated way. I also learned the importance of Terraform commands (init, plan, apply) and how to securely configure AWS access keys for automation.

### Project reflection

This project took me approximately a few hours to complete. The most challenging part was writing the Terraform configuration correctly and ensuring AWS credentials were properly set up, as mistakes could prevent resources from being created. It was most rewarding to see the S3 bucket successfully provisioned in AWS using code, knowing that the infrastructure was automated, repeatable, and under version control.

I chose to do this project today because I wanted to gain hands-on experience with Terraform and AWS, and see how Infrastructure as Code can simplify cloud resource management. Something that would make learning with NextWork even better is more guided, step-by-step project examples with screenshots or videos, so learners can follow along more easily and troubleshoot common issues in real time.

---

## Introducing Terraform

Terraform is an open-source Infrastructure as Code (IaC) tool that allows you to define, provision, and manage cloud and on-premises resources using simple, human-readable configuration files. It enables you to automate infrastructure deployment, track changes safely, and create consistent environments across development, testing, and production.

Infrastructure as Code (IaC) is the practice of managing and provisioning IT infrastructure—such as servers, networks, and storage—using code instead of manual processes. With IaC, you write configuration files that describe the desired state of your infrastructure, and tools like Terraform automatically create, update, and manage those resources in a consistent, repeatable, and version-controlled way.

main.tf is a central file in a Terraform project. It's where I write down what I want in my infrastructure to look like, using Terraform's language. Think of it as the blueprint for building cloud resources.

![Image](http://learn.nextwork.org/curious_teal_bold_lulo/uploads/aws-devops-terraform1_9i0j1k2l)

---

## Configuration files

The configuration is structured in human-readable .tf files, where each block defines providers, resources, and their settings. The advantage of doing this is that infrastructure can be version-controlled, automated, and easily reproduced across environments, making deployments consistent, predictable, and less prone to errors.

### My main.tf configuration has three blocks

The first block indicates the provider, telling Terraform to use AWS and enabling it to translate configuration into API calls. The second block provisions an S3 bucket, creating a storage resource that can be referenced in other parts of the configuration. The third block manages the bucket’s public access settings, ensuring the bucket and its contents are secure by blocking public access through various controls.

![Image](http://learn.nextwork.org/curious_teal_bold_lulo/uploads/aws-devops-terraform1_ljvh9876)

---

## Customizing my S3 Bucket

---

## Terraform commands

I ran terraform init to initialize my Terraform project by downloading the required provider plugins, setting up the backend configuration, and preparing the working directory to use Terraform. This command ensures that Terraform has everything it needs to start managing the infrastructure defined in my configuration files.

Next, I ran terraform plan to preview the changes Terraform will make to my AWS environment based on the configuration files. This command shows which resources will be created, modified, or deleted, allowing me to review and verify the proposed infrastructure changes before actually applying them.

![Image](http://learn.nextwork.org/curious_teal_bold_lulo/uploads/aws-devops-terraform1_3g4h5i6j)

---

## AWS CLI and Access Keys

When I tried to plan my Terraform configuration, I received an error message that says the security token requested included in the request is invalid, because this error means Terraform doesn't have the necessary credentials to access your AWS account. We need to configure AWS credentials for Terraform to use, so that it can create AWS resources on our behalf.



To resolve my error, first I installed AWS CLI, which lets you manage your AWS services from your terminal. Instead of having to use the AWS Management Console, you can now run text commands from your local machine.

In this case, we'll need the CLI

I set up AWS access keys to allow Terraform (and the AWS CLI) to securely authenticate with my AWS account, so it can create, modify, and manage resources on my behalf. These keys act as credentials that grant the necessary permissions for automated infrastructure deployment.

![Image](http://learn.nextwork.org/curious_teal_bold_lulo/uploads/aws-devops-terraform1_7j8k9l0m)

---

## Lanching the S3 Bucket

I ran terraform apply to create or update the AWS resources defined in my Terraform configuration. Running terraform apply will affect my AWS account by actually provisioning, modifying, or deleting resources—such as creating an S3 bucket—based on the plan generated by terraform plan. It turns my code into real, live infrastructure.

The sequence of running terraform init, terraform plan, and terraform apply is crucial because each command builds on the previous one. First, terraform init sets up the project by downloading providers and initializing the working directory. Next, terraform plan lets you preview the changes Terraform will make, giving you a safe opportunity to review before making any modifications. Finally, terraform apply executes those changes, creating or updating the actual infrastructure in your AWS account. Following this order ensures a smooth, predictable, and controlled deployment process.

![Image](http://learn.nextwork.org/curious_teal_bold_lulo/uploads/aws-devops-terraform1_1q2w3e4r)

---

## Uploading an S3 Object

---

---
