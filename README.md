## Usage

If you're using the `terraform-aws-modules/eks/aws` community module

```hcl
# We also want to be sure we can scale the underlying cluster based on scheduler contraints
module "cluster_autoscaler" {
  source = "./modules/cluster-autoscaler"
  cluster_oidc_issuer_url = module.eks.cluster_oidc_issuer_url
  cluster_id = module.eks.cluster_id
  cluster_name = local.cluster_name
}
```

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_cluster_oidc_issuer_url"></a> [cluster\_oidc\_issuer\_url](#input\_cluster\_oidc\_issuer\_url) | The URL on the EKS cluster OIDC Issuer | `string` | `""` | yes |
| <a name="input_cluster_id"></a> [cluster\_id](#input\_cluster\_id) | The name/id of the EKS cluster. Will block on cluster creation until the cluster is really ready. | `string` | `""` | yes |
| <a name="input_cluster_name"></a> [cluster\_name](#input\_cluster\_name) | Name of the EKS cluster. Also used as a prefix in names of related resources. | `string` | `""` | yes |