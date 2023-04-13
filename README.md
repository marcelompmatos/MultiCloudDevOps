# MultiCloudDevOps
 
## :computer: MultiCloud com DevOps utilizando com provisionamento Terraform

## 🛠 Provisionar Banco de Dados MYSQL na Google Cloud , Clusters do GKE - kubernetes e Bucket no S3 AWS 

⚡ Missão 1

⚡ Amazon Web Services (AWS)

1. Acessar a console da AWS. Na barra de pesquisas, digite IAM. Na seção Services, clique em IAM.  👋

2. Clique em Add user, insira o nome terraform-pt-1 e clique em Next para criar o usuário do tipo programmatic.  👋

![image](https://user-images.githubusercontent.com/76752875/231753016-75ffea2d-a9ed-4c19-b264-12038c89919d.png)

3. Após avançar, em Set permissions, clique no botão Attach existing policies directly. 👋

![image](https://user-images.githubusercontent.com/76752875/231754740-d41b160a-dddb-4797-8c90-d23c0f0c49f2.png)

4. Digite AmazonS3FullAccess em Filter distributions by text, property or value e aperte Enter. 👋

5. Selecione AmazonS3FullAccess. 👋

![image](https://user-images.githubusercontent.com/76752875/231755714-d06d4e66-dd65-4b2d-bee5-d8a44fbf8169.png)

6. Clique em Next. 👋

7. Revise todos os detalhes. 👋

8. Clique em Create user.👋

⚡ [NEW] AWS has recently changed the way to create/download the access key. Follow the new steps:










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

