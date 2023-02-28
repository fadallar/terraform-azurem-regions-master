# Azure regions module
[![Changelog](https://img.shields.io/badge/changelog-release-green.svg)](CHANGELOG.md) [![Notice](https://img.shields.io/badge/notice-copyright-yellow.svg)](NOTICE) [![Apache V2 License](https://img.shields.io/badge/license-Apache%20V2-orange.svg)](LICENSE) [![TF Registry](https://img.shields.io/badge/terraform-registry-blue.svg)](https://registry.terraform.io/modules/claranet/regions/azurerm/)

This module is the work of [Claranet](https://github.com/Claranet/).

This Terraform module is designed to help in using the AzureRM terraform provider.

It provides for an Azure region given in standard format, CLI format or slug format the corresponding Azure standard format, a short format used for resource naming, the CLI format and a slug format.

It also provides the [paired region](https://docs.microsoft.com/en-us/azure/availability-zones/cross-region-replication-azure) associated to the current one.

Please refer to the [regions.tf](regions.tf) file for available regions.
Complete regions mapping is also available in [REGIONS.md](REGIONS.md) documentation.

<!-- BEGIN_TF_DOCS -->

## Usage

```hcl
module "azure_region" {
  source  = "XXX/regions/azurerm"
  version = "x.x.x"

  azure_region = "eu-west"
}
```

## Providers

No providers.

## Modules

No modules.

## Resources

No resources.

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| azure\_region | Azure Region standard name, CLI name or slug format | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| location | Azure region in standard format |
| location\_cli | Azure region in Azure CLI name format |
| location\_short | Azure region in short format for resource naming purpose |
| location\_slug | Azure region in slug format |
| paired\_location | Azure paired region with the current one. All formats available as attributes.<pre>object({<br>  location (string): Azure paired region in standard format<br>  location_short (string): Azure paired region in short format for resource naming purpose<br>  location_cli (string): Azure paired region in CLI name format<br>  location_slug (string): Azure paired region in slug format<br>})</pre> |
<!-- END_TF_DOCS -->

## Related documentation

Azure regions: [azure.microsoft.com/en-us/global-infrastructure/regions/](https://azure.microsoft.com/en-us/global-infrastructure/regions/)
