# Terraform Cross Cutting Concerns

## Recommended Tags in every resource

- A tag which says which tool/process created it
- An Owner tag
- Project (if applicable)
- 

## Default Tags

Currently only [AWS supports default tags](https://www.hashicorp.com/blog/default-tags-in-the-terraform-aws-provider) between the created resources.
In [Azure its still under development](https://github.com/hashicorp/terraform-provider-azurerm/issues/13776).

