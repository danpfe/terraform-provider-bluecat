---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "bluecat_ip4_available_network Resource - terraform-provider-bluecat"
subcategory: ""
description: |-
  Resource to select an IPv4 network from a list of networks based on availability of IP addresses.
---

# bluecat_ip4_available_network (Resource)

Resource to select an IPv4 network from a list of networks based on availability of IP addresses.

## Example Usage

```terraform
resource "bluecat_ip4_available_network" "network" {
  network_id_list = [1234, 5678, 9101]
}

output "network_id" {
  value = bluecat_ip4_available_network.network.network_id
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- **network_id_list** (List of Number) A list of Network IDs to search for a free IP address. By default, the address with the most free addresses will be returned. See the `random` argument for another selection method. The resource will be recreated if the network_id_list is changed. You may want to use a `lifecycle` customization to ignore changes to the list after resource creation so that a new network is not selected if the list is changed.

### Optional

- **id** (String) The ID of this resource.
- **keepers** (Map of String) An arbitrary map of values. If this argument is changed, then the resource will be recreated.
- **random** (Boolean) By default, the network with the most free IP addresses is returned. By setting this to `true` a random network from the list will be returned instead. The network will be validated to have at least 1 free IP address. Defaults to `false`.
- **seed** (String) A seed for the `random` argument's generator. Can be used to try to get more predictable results from the random selection. The results will not be fixed however.

### Read-Only

- **network_id** (Number) The network ID of the network selected by the resource.


