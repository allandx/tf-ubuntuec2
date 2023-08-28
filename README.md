# Ubuntu EC2 terraform code and bash scripting
Repo aims to create a standard Ubuntu Ec2, with its networking components in AWS with Terraform with the following resources:

- Vpc, subnet, route table, SG, IGW, AMI, keypair, instance

AWS authentication:
It authenticates into AWS using credentials file in ~/.aws/config. The profile name is named "cc". Note: if no profile name is set in tf code(provider block), the defualt profile is used. Alternatively, we can use the export command.

EC2 credentials:
As this is for developement purpose using a sandbox environment that ends in a short time frame( meaning resources will be destroyed with x hours), the private key is generated and stored within local files. For e.g. the Private key is downloaded automatically and stored in demokeypair.pem.

This code is a "plug and play" after AWS authentication is done


