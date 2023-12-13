# Ubuntu EC2 terraform code 
1. Repo aims to create a standard Ubuntu Ec2, with its networking components in AWS with Terraform with the following resources:

- Vpc, subnet, route table, SG, IGW, AMI, keypair, instance

2. AWS authentication:
It authenticates into AWS using credentials file in ~/.aws/config. The profile name is named "cc". Note: if no profile name is set in tf code(provider block), the default profile is used. Alternatively, we can use the export command.

3. EC2 credentials:
As this is for developement purpose, the private key is generated and stored within local files. For e.g. the Private key is downloaded automatically and stored in demokeypair.pem. Note that this provisioner'local-exec" code only works on linux machines

4. This code is a "plug and play" after AWS authentication is done


ref:
https://cloudkatha.com/how-to-create-key-pair-in-aws-using-terraform-in-right-way/#google_vignette
