# Cert-Manager-Demo

This repo shows how the Cert-Manager ACME Azure DNS integration works.

## Setup

There are some secrets and setup needed to get this repo going.

1. Clone/Fork this repo
2. Create an RG in Azure and note down the name
3. Create a GitHub secret holding an Azure Service Principal following this guide: <https://github.com/Azure/actions-workflow-samples/blob/master/assets/create-secrets-for-GitHub-workflows.md> giving it access to the RG in step 2.
4. Follow the guide: <https://cert-manager.io/docs/configuration/acme/dns01/azuredns/#service-principal> and create a GitHub action secret with the name AZURE_DNS_CONFIG with the base64 value from the guide.
5. Create secrets from step 4 to be able to replace the values in ./yaml/cert-manager/cluster-issuer.yaml. You should have the following secrets in our GitHub repo:
6. The value of the EXAMPLE_CERT GitHub secret is the certificate you want, .e.g, mycert.example.com

- AZURE_CREDENTIALS
- AZURE_CERT_MANAGER_SP_APP_ID
- AZURE_DNS_CONFIG
- AZURE_DNS_ZONE
- AZURE_DNS_ZONE_RESOURCE_GROUP
- AZURE_SUBSCRIPTION_ID
- AZURE_TENANT_ID
- EXAMPLE_CERT

## Status

[![Create AKS](https://github.com/fredrkl/cert-manager-k8s-setup/actions/workflows/createaks.yml/badge.svg)](https://github.com/fredrkl/cert-manager-k8s-setup/actions/workflows/createaks.yml)

[![Deploy to AKS](https://github.com/fredrkl/cert-manager-k8s-setup/actions/workflows/deploy-to-aks.yml/badge.svg)](https://github.com/fredrkl/cert-manager-k8s-setup/actions/workflows/deploy-to-aks.yml)
