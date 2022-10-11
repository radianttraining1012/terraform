Install Terraform
-----------------

1. Install chocolatey on windows of your laptop
https://chocolatey.org/install

2. Install terraform with below command:
choco install terraform

3. Follow below to install terraform in different OS
https://www.terraform.io/downloads

-----------------
terraform provider version constraint. version arugment is used to specify provider constraint.

terraform {
  required_providers {
    artifactory = {
      source = "jfrog/artifactory"
      version = "6.14.0"
    }
  }
}

provider "artifactory" {
  # Configuration options
}
-----------------
terraform version constraint. required_version is used to specify terraform version constraint.
terraform {
  required_providers {
    artifactory = {
      source = "jfrog/artifactory"
      version = "6.14.0"
    }
  required_version = "~>= 1.3.1"  
  }
}

provider "artifactory" {
  # Configuration options
}

-----------------------
How to upgrade/degrade terraform provider?
Either delete .terraform.lock.hcl file or terraform init -upgrade
-----------------------

Terraform workflow:
1. create/init
2. plan
3. apply

-----------------------

Create ec2.tf file:

provider "aws" {
  region     = "us-east-1"
  access_key = "XXXXX"
  secret_key = "XXXXX"
}

resource "aws_instance" "webvm" {
   ami = "ami-026b57f3c383c2eec"
   instance_type = "t2.micro"
}


terraform init
This will initializes a working directory containing configuration files and install pluggins for required providers.

terraform plan
It will let you preview the actions terraform would take to modify your infrastruture, or save plan which you can apply later.

terraform apply
This will execute the actions proposed in a terraform plan to create, update or destroy infrastructure.
----------

1. Create and execute plan for creation of resources:

terraform plan -out myplan.out
terraform apply myplan.out

This command will show you the content of plan:

terraform show -json myplan.out | jq

2. Create and execute plan for deletion of resources:

terraform plan -destroy -out destroy.out
terraform apply destroy.out


terraform destroy:
It will delete all resources mentioned in your configuration.

-----------------------
