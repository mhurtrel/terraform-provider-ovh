---
layout: "ovh"
page_title: "OVH: cloud_regions"
sidebar_current: "docs-ovh-datasource-cloud-regions"
description: |-
  Get the list of regions associated with a public cloud project.
---

# ovh_cloud_regions

~> __DEPRECATED:__ Use [`ovh_cloud_project_regions`](./cloud_project_regions.html) instead.

Use this data source to get the regions of a public cloud project.

## Example Usage

```hcl
data "ovh_cloud_regions" "regions" {
  project_id = "XXXXXX"
  
  has_services_up = ["network"]
}
```

## Argument Reference


* `project_id` - (Required) The id of the public cloud project. If omitted,
    the `OVH_PROJECT_ID` environment variable is used.

* `has_services_up` - (Optional) List of services which has to be UP in regions.
   Example: "image", "instance", "network", "storage", "volume", "workflow", ...
   If left blank, returns all regions associated with the project_id.


## Attributes Reference

`id` is set to the ID of the project. In addition, the following attributes
are exported:

* `names` - The list of regions associated with the project, filtered by services UP.
