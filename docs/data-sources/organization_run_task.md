---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "tfe_organization_run_task Data Source - terraform-provider-tfe"
subcategory: ""
description: |-
  Run tasks https://www.terraform.io/cloud-docs/workspaces/settings/run-tasks allow Terraform Cloud to interact with external systems at specific points in the Terraform Cloud run lifecycle. Run tasks are reusable configurations that you can attach to any workspace in an organization.
  Use this data source to get information about an Organization Run tasks https://www.terraform.io/cloud-docs/workspaces/settings/run-tasks#creating-a-run-task.
---

# tfe_organization_run_task

[Run tasks](https://www.terraform.io/cloud-docs/workspaces/settings/run-tasks) allow Terraform Cloud to interact with external systems at specific points in the Terraform Cloud run lifecycle. Run tasks are reusable configurations that you can attach to any workspace in an organization.

Use this data source to get information about an [Organization Run tasks](https://www.terraform.io/cloud-docs/workspaces/settings/run-tasks#creating-a-run-task).

## Example Usage 

```terraform
data "tfe_organization_run_task" "example" {
  name         = "task-name"
  organization = "my-org-name"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String) Name of the Run task.
- `organization` (String) Name of the organization.

### Optional

- `category` (String) The type of task.
- `enabled` (Boolean) Whether the task will be run.
- `url` (String) URL to send a run task payload.

### Read-Only

- `id` (String) The ID of this resource.
