# Ubuntu EC2 terraform code and bash scripting
Repo aims to create a standard Ubuntu Ec2, with its networking components in AWS with Terraform with the following resources:

- Vpc, subnet, route table, SG, IGW, AMI, keypair, instance

AWS authentication:
It authenticates into AWS using credentials file in ~/.aws/config. The profile name is named "cc". Note: if no profile name is set in tf code(provider block), the defualt profile is used.

EC2 credentials:
Key name is "my_key" using existing id_rsa.pub in ~/.ssh located within local machine

This code is a "plug and play" after AWS authentication is done


