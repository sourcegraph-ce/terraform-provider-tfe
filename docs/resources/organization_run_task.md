---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "tfe_organization_run_task Resource - terraform-provider-tfe"
subcategory: ""
description: |-
  Run tasks https://www.terraform.io/cloud-docs/workspaces/settings/run-tasks allow Terraform Cloud to interact with external systems at specific points in the Terraform Cloud run lifecycle. Run tasks are reusable configurations that you can attach to any workspace in an organization.
  The tfeorganizationrun_task resource creates, updates and destroys Organization Run tasks https://www.terraform.io/cloud-docs/workspaces/settings/run-tasks#creating-a-run-task.
---

# tfe_organization_run_task

[Run tasks](https://www.terraform.io/cloud-docs/workspaces/settings/run-tasks) allow Terraform Cloud to interact with external systems at specific points in the Terraform Cloud run lifecycle. Run tasks are reusable configurations that you can attach to any workspace in an organization.

 The tfe_organization_run_task resource creates, updates and destroys [Organization Run tasks](https://www.terraform.io/cloud-docs/workspaces/settings/run-tasks#creating-a-run-task).

## Example Usage 

```terraform
resource "tfe_organization_run_task" "example" {
  organization = "org-name"
  url          = "https://external.service.com"
  name         = "task-name"
  enabled      = true
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String) Name of the task.
- `organization` (String) Name of the organization.
- `url` (String) URL to send a run task payload.

### Optional

- `category` (String) The type of task.
- `enabled` (Boolean) Whether the task will be run.
- `hmac_key` (String, Sensitive) HMAC key to verify run task.

### Read-Only

- `id` (String) The ID of this resource.

## Import

Import is supported using the following syntax:

```shell
# Use <ORGANIZATION NAME>/<TASK NAME> as the import ID. For example:

terraform import tfe_organization_run_task.test my-org-name/task-name
```