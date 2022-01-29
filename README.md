## Terraform Minimal
```
WITHOUT BACKEND
terraform init -reconfigure
terraform plan -var-file variables.tfvars -out tfplan
terraform apply tfplan

WITH BACKEND
terraform init -reconfigure -backend-config backend.tfvars
terraform plan -var-file variables.tfvars -out tfplan
terraform apply tfplan

QUICK APPLY
terraform apply -var-file variables.tfvars --auto-approve
```