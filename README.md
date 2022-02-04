# Terraform Minimal

## Deploy Terraform Backend
Make sure you have AWS credentials in your environment, or use the `--profile` flag.
```
aws cloudformation deploy --stack-name tf-state-eu-west-1 --template-file ./cloudformation/tf-preparation.yaml --region eu-west-1
```


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