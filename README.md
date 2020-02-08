# Google Firewall Terraform module

Módulo para Terraform que gerencia simples regras de firewall.

These types of resources are supported:

## Terraform versão

Terraform > 0.12.19

Esta definição encontra-se no arquivo `versions.tf`

## Como utilizar

```hcl
module "firewall" {
  source = "git@github.com/gdglajeado/tf-module-gcp-firewall.git?ref=v1.0"

  name          = "rundeck"
  network       = module.network.self_link
  protocol      = "TCP"
  ports         = ["80", "4440", "443", "22"]
  source_tags   = ["rundeck-stack"]
  source_ranges = ["0.0.0.0/0"]
}
```