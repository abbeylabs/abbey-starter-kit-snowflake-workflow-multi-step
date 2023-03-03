# Workflow multi step example

This example shows how to create a multistep Grant Kit workflow.
The example features requesting access to a [Snowflake Role Grant](https://registry.terraform.io/providers/Snowflake-Labs/snowflake/latest/docs/resources/role_grants) 
in two sequential steps, with the first step requiring all reviewers to approve access and 
the second step requiring just one reviewer to approve access.

## Prerequisites

1. Abbey Labs Account - [Sign up for the waitlist](https://abbey.so/sign-up).
2. Snowflake Account

## Usage

1. Initialize the Terraform configuration.

```shell
terraform init
```

2. Create a tfvars file and add in your Snowflake variables.

```shell
echo 'account = "..."\nusername = "..."\npassword = "..."' > dev.tfvars
```

3. Replace the configuration stubs (denoted by `...` strings) in [main.tf](main.tf).
4. Plan and apply your configuration

```shell
terraform plan
terraform apply
```

## Automating Access Requests

Once you've applied your configuration, you can automate your access requests through Abbey with the following steps:

1. Copy the provided GitHub Actions Workflow template.

```shell
cp .github/workflows/abbey-grant-kit-generate-policy-input.yaml.example .github/workflows/abbey-grant-kit-generate-policy-input.yaml
```

2. Add your `SNOWFLAKE_USERNAME` and `SNOWFLAKE_PASSWORD` to your [GitHub Repository Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets).
3. :tada: Congratulations! Your access requests are now automated! You can tell your users to head over
   to the [Abbey App](https://app.abbey.so) to start requesting access!

## :books: Learn More

To learn more about Grant Kits and Grant Workflows, visit the following resources:

- [Abbey Labs Documentation](https://docs.abbey.so) - learn about automating access management with Abbey Labs.
