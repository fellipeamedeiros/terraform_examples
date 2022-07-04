# Cloud Run and Cloud Sql Terraform Example

## Flie Structure

| File | Description |
| ------ | ------ |
| main.tf | will contain the main set of configuration for your module. You can also create other configuration files and organize them however makes sense for your project. |
| variables.tf | will contain the variable definitions for your module. When your module is used by others, the variables will be configured as arguments in the module block. Since all Terraform values must be defined, any variables that are not given a default value will become required arguments. Variables with default values can also be provided as module arguments, overriding the default value. |
| terraform.tfvars | set the value of the varibles |

## Deploying the infrastructure

Start by initializing the configuration. Run the following command in your terminal:

```sh
terraform init
```

Run the plan command to verify the changes:

```sh
terraform plan
```

If your template is correct, you will see that 3 resources will be created and the service URL will be displayed after the apply.

```sh
Plan: 3 to add, 0 to change, 0 to destroy.

Changes to Outputs:
  + service_url = (known after apply)
```

Run the apply command to apply all the changes:

```sh
terraform apply
```

If everything goes well, you will see this result at the end of the terraform execution:
```sh
Apply complete! Resources: 3 added, 0 changed, 0 destroyed.

Outputs:

service_url = https://teste-cloudrun-4zg32hykhq-ue.a.run.app
```

Check if the service is running using curl command in your terminal:
```sh
curl https://teste-cloudrun-4zg32hykhq-ue.a.run.app

Hello, world!
Version: 1.0.0
Hostname: localhost
```

If you want do delete all the resources:
```sh
terraform destroy
```