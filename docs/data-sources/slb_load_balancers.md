---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "st-alicloud_slb_load_balancers Data Source - st-alicloud"
subcategory: ""
description: |-
  This data source provides the Server Load Balancers in desired region or user account.
---

# st-alicloud_slb_load_balancers (Data Source)

This data source provides the Server Load Balancers in desired region or user account.

## Example Usage

```terraform
provider "st-alicloud" {
  alias  = "slb"
  region = "cn-hongkong"
}

data "st-alicloud_slb_load_balancers" "slbs" {
  provider = st-alicloud.slb

  tags = {
    "app" = "web-server"
    "env" = "basic"
  }
}

output "slb_load_balancers" {
  value = data.st-alicloud_slb_load_balancers.slbs
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Optional

- `client_config` (Block, Optional) Config to override default client created in Provider. This block will not be recorded in state file. (see [below for nested schema](#nestedblock--client_config))
- `name` (String) The name of the SLBs.
- `tags` (Map of String) A map of tags assigned to the SLB instances.

### Read-Only

- `load_balancers` (Attributes List) A list of SLBs. (see [below for nested schema](#nestedatt--load_balancers))

<a id="nestedblock--client_config"></a>
### Nested Schema for `client_config`

Optional:

- `region` (String) The region of the SLBs. Default to use region configured in the provider.
- `zone` (String) The master zone of the SLBs.
- `access_key` (String) The access key that have permissions to list SLBs. Default to use access key configured in the provider.
- `secret_key` (String) The secret key that have permissions to lsit SLBs. Default to use secret key configured in the provider.


<a id="nestedatt--load_balancers"></a>
### Nested Schema for `load_balancers`

Read-Only:

- `id` (String) ID of the SLB.
- `master_zone_id` (String) Master zone of the SLB.
- `name` (String) The name of the SLB.
- `slave_zone_id` (String) Slave zone of the SLB.
- `tags` (Map of String) The tags of the SLB.


