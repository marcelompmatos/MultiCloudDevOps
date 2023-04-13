# MultiCloudDevOps
 
## :computer: MultiCloud com DevOps utilizando com provisionamento Terraform

⚡ MultiCloud com DevOps 
## 🛠 Provisionar Banco de Dados MYSQL na Google Cloud , Clusters do GKE - kubernetes e Bucket no S3 AWS 






1. No terminal da AWS opçao action efetuar o upload do arquivo "main.tf"  👋
2. Depois do upoload do Arquivo iremos executar comando do "Terraform "  👋

```bash
  terraform init
  terraform plan
  terraform apply
```

```bash
Tornar o Bucket Privado - inserir o codigo no arquivo e executar os comandos "terraform plan" e "terraform apply"

  resource "aws_s3_bucket_public_access_block" "s3_block" {
  bucket = aws_s3_bucket.s3_bucket.id

  block_public_acls       = true
  block_public_policy     = true
  ignore_public_acls      = true
  restrict_public_buckets = true
}
```


<p align="center">
⚡ Documentação 👋
    (https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
</p>   

