# jx3-kubernetes-vault

Jenkins X 3.x GitOps repository for a vanilla Kubernetes cluster with on premise vault
        
[![Jenkins X Releases](https://img.shields.io/badge/Jenkins%20X-Releases-blue)](docs/README.md)

**NOTE** that it is left to the user to manage, backup and restore the vault installation once it has been installed. 

For production workloads we recommend you use a cloud provider secret store or [Vault as a service](https://www.hashicorp.com/resources/running-vault-as-a-service-on-hashicorp-cloud-platform) 


## Before you use this repository

You must setup the vault infrastructure first before you [setup the git operator](https://jenkins-x.io/v3/admin/setup/operator/). 

To do this ensure you have helm and helmfile installed then run:

```bash 
cd infra
helmfile install helmfile.yaml
```

Then make sure the vault pod is running correctly in the `jx-vault` namespace:

```bash 
jx secret vault port-forward&
jx secret vault wait
```

Once your vault is up and running you can [setup the git operator](https://jenkins-x.io/v3/admin/setup/operator/) 

