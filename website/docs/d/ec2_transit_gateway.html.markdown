---
subcategory: "EC2"
layout: "aws"
page_title: "AWS: aws_ec2_transit_gateway"
description: |-
  Get information on an EC2 Transit Gateway
---

# Data Source: aws_ec2_transit_gateway

Get information on an EC2 Transit Gateway.

## Example Usage

### By Filter

```terraform
data "aws_ec2_transit_gateway" "example" {
  filter {
    name   = "options.amazon-side-asn"
    values = ["64512"]
  }
}
```

### By Identifier

```terraform
data "aws_ec2_transit_gateway" "example" {
  id = "tgw-12345678"
}
```

## Argument Reference

The following arguments are supported:

* `filter` - (Optional) One or more configuration blocks containing name-values filters. Detailed below.
* `id` - (Optional) Identifier of the EC2 Transit Gateway.

### filter Argument Reference

* `name` - (Required) The name of the field to filter by, as defined by the [underlying AWS API](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_DescribeTransitGateways.html).
* `values` - (Required) List of one or more values for the filter.

## Attribute Reference

In addition to all arguments above, the following attributes are exported:

* `amazon_side_asn` - Private Autonomous System Number (ASN) for the Amazon side of a BGP session
* `arn` - EC2 Transit Gateway Amazon Resource Name (ARN)
* `association_default_route_table_id` - Identifier of the default association route table
* `auto_accept_shared_attachments` - Whether resource attachment requests are automatically accepted.
* `default_route_table_association` - Whether resource attachments are automatically associated with the default association route table.
* `default_route_table_propagation` - Whether resource attachments automatically propagate routes to the default propagation route table.
* `description` - Description of the EC2 Transit Gateway
* `dns_support` - Whether DNS support is enabled.
* `multicast_support` - (Optional) Whether Multicast support is enabled. Required to use `ec2_transit_gateway_multicast_domain`. Valid values: `disable`, `enable`. Default value: `disable`.
* `id` - EC2 Transit Gateway identifier
* `owner_id` - Identifier of the AWS account that owns the EC2 Transit Gateway
* `propagation_default_route_table_id` - Identifier of the default propagation route table.
* `tags` - Key-value tags for the EC2 Transit Gateway
* `vpn_ecmp_support` - Whether VPN Equal Cost Multipath Protocol support is enabled.
