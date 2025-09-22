# Terraform module for AWS Batch Job Revision creating

## Author is Yauhen Bichel

## How to use 

```

module "aws_batch_job_revision" {
  source                                      = "./modules/aws_batch_job_revision"

  aws_region                                  = var.aws_region
  env                                         = var.env
  service_domain                              = var.service_domain

  job_definition_name                         = var.aws_batch_job_job_definition_name
  image_name                                  = var.aws_batch_job_revision_image_name
  execution_role                              = var.aws_batch_job_revision_execution_role
  execution_role_arn                          = var.aws_batch_job_revision_execution_role_arn

  job_revision_type                           = var.aws_batch_job_revision_type
  platform_capability                         = var.aws_batch_job_revision_platform_capability
  vcpu                                        = var.aws_batch_job_revision_vcpu
  memory                                      = var.aws_batch_job_revision_memory
  fargate_platform_version                    = var.aws_batch_job_fargate_platform_version
  fargate_platform_operating_system_family    = var.aws_batch_job_fargate_platform_operating_system_family
  fargate_platform_cpu_architecture           = var.aws_batch_job_fargate_platform_cpu_architecture
  assign_public_ip                            = var.aws_batch_job_assign_public_ip
  job_command                                 = var.aws_batch_job_revision_command
  environment_variables_list                  = var.aws_batch_job_revision_environment_variables_list
  secrets_list                                = var.aws_batch_job_revision_secrets_list
  execution_timeout                           = var.aws_batch_job_revision_execution_timeout
  retry_attempts                              = var.aws_batch_job_revision_retry_attempts

  load_date                                   = var.load_date
  load_date_default_enabled                   = var.load_date_default_enabled

  additional_tags = {
    Environment = var.env
    Project     = var.project_name
    Team        = var.team
  }
}

```

## Terratest Tests

>go mod init batch-job-definition-tests

>go get github.com/gruntwork-io/terratest

>go get github.com/stretchr/testify

>go mod tidy

>go test -v
