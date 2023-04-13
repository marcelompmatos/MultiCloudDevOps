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

9. Acesse o usuário terraform-pt-1.👋

11. Clique em Security credentials.👋

12. Navegue até a seção Access keys.👋

13. Clique em Create access key.👋

![image](https://user-images.githubusercontent.com/76752875/231761785-8d8ac147-8bf4-4626-9427-33eb56fa4288.png)

14. Selecione Command Line Interface (CLI) e I understand the above recommendation and want to proceed to create an access key.👋

15. Clique em Next.👋

16. Clique em Create access key.👋

17. Clique em Download .csv file.👋

18. Após o download finalizar, clique em Done.👋

19. Com o download feito, renomeie o .csv para accessKeys.csv.👋

## 🛠 Google Cloud Platform (GCP)

20. Baixar projeto do git "mission1.zip".👋

21. Acessar a console da GCP e abrir o Cloud Shell👋

22. Fazer o upload dos arquivos accessKeys.csv e mission1.zip para o Cloud Shell👋

23. Após fazer o upload, executar os comandos de preparação dos arquivos:👋

```bash
       mkdir mission1_pt
       mv mission1.zip mission1_pt
       cd mission1_pt
       unzip mission1.zip
       mv ~/accessKeys.csv mission1/pt
       cd mission1/pt
       chmod +x *.sh
```

24. Após fazer o upload, executar os comandos de preparação dos arquivos:👋

```bash
       ./aws_set_credentials.sh accessKeys.csv
       gcloud config set project <your-project-id>
```

25. Clique em Autorize e execute o comando abaixo para setar o projeto no Google Cloud Shell.👋

```bash
      ./gcp_set_project.sh
```
26. Execute o comando para habilitar as APIs do Kubernetes, Container Registry e Cloud SQL.👋

```bash
      gcloud services enable containerregistry.googleapis.com
      gcloud services enable container.googleapis.com
      gcloud services enable sqladmin.googleapis.com
```

## 🛠 OBS IMPORTANTE (NÃO PULE ESTE PASSO):

## 🛠Antes de executar os comandos do terraform, abra o Google Cloud Editor e atualizar o arquivo tcb_aws_storage.tf substituindo o nome do bucket para um exclusivo    (na AWS, os buckets precisam ter nomes únicos).

28. Na linha 4 do arquivo tcb_aws_storage.tf:👋

29. Abra o Google Cloud Editor:👋

30. Substituir xxxx pelas iniciais do seu nome mais dois números: Exemplo: luxxy-covid-testing-system-pdf-pt-jr29:👋

29. Execute os seguintes comandos para provisionar os recursos de infraestrutura:👋

```bash
       cd ~/mission1_pt/mission1/pt/terraform/

       terraform init
       terraform plan
       terraform apply
}
```

![image](https://user-images.githubusercontent.com/76752875/231773587-14add5d7-9025-4c6d-af22-2ab038ed12e7.png)

![image](https://user-images.githubusercontent.com/76752875/231773765-d0ccf4cb-9cc0-426c-95bf-686f784a360d.png)


<aside>
💡 Após acessar o serviço do GKE para criar o cluster, clicar no botão Compare para "Comparar os modes de cluster para entender mais sobre as suas diferenças".
</aside>

## 🛠 [New] Configuração de Rede SQL:

<video playsinline="" controls="" preload="metadata" src="https://file.notion.so/f/s/6ab20977-4163-4519-8d2d-87fbfe5d5f8e/SQL_Networking_Configuration_EDITED.mov?id=bfb62686-39d7-4a2e-8a47-326503de96ac&amp;table=block&amp;spaceId=0d1b678b-cd91-4256-93c7-73b2e82396d5&amp;expirationTimestamp=1681479502098&amp;signature=p8rD1Bz4aup-zCVkzcc8ukNYQwUbSe7bJGh4x3jHiwg" style="display: block; pointer-events: none; width: 100%; background-color: rgb(242, 241, 238);"></video>




[![asciicast]([https://asciinema.org/a/113463](https://file.notion.so/f/s/6ab20977-4163-4519-8d2d-87fbfe5d5f8e/SQL_Networking_Configuration_EDITED.mov?id=bfb62686-39d7-4a2e-8a47-326503de96ac&amp;table=block&amp;spaceId=0d1b678b-cd91-4256-93c7-73b2e82396d5&amp;expirationTimestamp=1681479502098&amp;signature=p8rD1Bz4aup-zCVkzcc8ukNYQwUbSe7bJGh4x3jHiwg))




<p align="center">
⚡ Documentação 👋
    (https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
</p>   

