# Infrastructure as code (IaC)

IaC — it is an approach(подход) to manage and describe the infrastructure with configuration files, without manually editing a configurations on the servers. You can automatically deploy, update the infrastructure through the configuration files of special tools special tools (Terraform, Ansible)

Tools for Iac from clouds?

## IaC better when script?

For example, terraform, when started again with actual .tfstate, terraform updates the infrastructure which is already running and make it to the state of the configuration file (if the infrastructure was created with terraform, it works using the .tfstate file). Regular output commands or scripts will give an error, because the infrastructure already exists. In other words you can't update infrastructure use primaty sctipt with upate. 