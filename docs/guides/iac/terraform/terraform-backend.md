# Terraform Backend

## Backend Initialization

Steps to create a new Backend:
- Write Terraform code to create the backend storage and deploy that code with a local backend.
- Go back to the Terraform code, add a remote backend configuration to it and run terraform init to copy your local state to the cloud.

## Backend Removal

If you ever wanted to delete the backend storage, you’d have to do this two-step process in reverse:
- Go to the Terraform code, remove the backend configuration, and rerun terraform init to copy the Terraform state back to your local disk.
- Run terraform destroy to delete the S3 bucket and DynamoDB table.

## Backend Encryption
- Azure Storage Accounts already store encrypted data in disk.
- Assign correct role assignments in Azure Storage Account for the terraform state.
- Encrypt using CMKs so the [cloud doesn't accidently get access to your data](https://zoph.me/posts/2021-12-22-the-day-when-aws-support-got-access-to-your-data/).
- Encrypt sensitive values (secrets) when [terraform supports it](https://github.com/hashicorp/terraform/issues/9556#issuecomment-1011607151).