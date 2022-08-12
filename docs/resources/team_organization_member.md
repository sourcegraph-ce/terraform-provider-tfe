---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "tfe_team_organization_member Resource - terraform-provider-tfe"
subcategory: ""
description: |-
  Add or remove a team member using a tfeorganizationmembership organization_membership.html.
  ~> NOTE On managing team memberships: Terraform currently provides three resources for managing team memberships. This is the preferred method as it allows you to add a member to a team by email address.
  ~> NOTE: This resource requires using the provider with Terraform Cloud or an instance of Terraform Enterprise at least as recent as v202004-1.
---

# tfe_team_organization_member

Add or remove a team member using a [tfe_organization_membership](organization_membership.html).

 ~> **NOTE** On managing team memberships: Terraform currently provides three resources for managing team memberships. This is the preferred method as it allows you to add a member to a team by email address.

 ~> **NOTE:** This resource requires using the provider with Terraform Cloud or an instance of Terraform Enterprise at least as recent as v202004-1.

## Example Usage 

```terraform
resource "tfe_team" "test" {
  name         = "my-team-name"
  organization = "my-org-name"
}

resource "tfe_organization_membership" "test" {
  organization = "my-org-name"
  email = "example@hashicorp.com"
}

resource "tfe_team_organization_member" "test" {
  team_id = tfe_team.test.id
  organization_membership_id = tfe_organization_membership.test.id
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `organization_membership_id` (String) ID of the organization membership.
- `team_id` (String) ID of the team.

### Read-Only

- `id` (String) The ID of this resource.

## Import

Import is supported using the following syntax:

```shell
# Use <TEAM ID>/<ORGANIZATION MEMBERSHIP ID> as the import ID. For example:

terraform import tfe_team_organization_member.test team-47qC3LmA47piVan7/ou-2342390sdf0jj
```