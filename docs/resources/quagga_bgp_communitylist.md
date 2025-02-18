---
page_title: "opnsense_quagga_bgp_communitylist Resource - terraform-provider-opnsense"
subcategory: Quagga
description: |-
  Configure community lists for BGP.
---

# opnsense_quagga_bgp_communitylist (Resource)

Configure community lists for BGP.

## Example Usage

```terraform
// Configure a community list
resource "opnsense_quagga_bgp_communitylist" "example0" {
  enabled     = false
  description = "communitylist0"

  number     = 100
  seq_number = 99
  action     = "deny"

  community = "example.*"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `community` (String) The community you want to match. You can also regex and it is not validated so please be careful.
- `number` (Number) Set the number of your Community-List. 1-99 are standard lists while 100-500 are expanded lists.
- `seq_number` (Number) The ACL sequence number (10-99).

### Optional

- `action` (String) Set permit for match or deny to negate the rule. Defaults to `"permit"`.
- `description` (String) An optional description for this prefix list. Defaults to `""`.
- `enabled` (Boolean) Enable this community list. Defaults to `true`.

### Read-Only

- `id` (String) UUID of the community list.

