# Terrafom 

`terraform init` - cheak all .tf files and download the necessary plugins for work. For example a plugin for Azure or AWS

`terraform plan` - shows what will be done (updated, etc.) after apply. Show changes required by the current configuration.

`terraform apply` -  Create or update infrastructure that are specified in .tf files. Creates a `.tfstate` file and checks the state, infrastructure parameters with it. If run again, `apply` will only update the infrastructure to the state that is specified in the .tf files. If you delete the .tfstate file and run apply, it will re-create the infrastructure.

`tfsate` - it is better to store it remotely so that other developers can access it, for example in a Git repository.