# MultiCloudDevOps - Missão 1
 
## :computer: MultiCloud com DevOps utilizando para provisionamento o Terraform

## 🛠 Provisionar Banco de Dados MYSQL na Google Cloud , Clusters do GKE - kubernetes e Bucket no S3 AWS 

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

- Após a conclusão do provisionamento da instância do CloudSQL, acesse o serviço do Cloud SQL.
- Clique na sua instância do Cloud SQL.
- Na lateral direita, em Primary Instance, clique em **“Connections”.**
- Em **Instance IP assignment**, habilite o Private IP.
    - Em **Associated Network**, selecione “Default”.
    - Clique em **Set up connection**
    - Enable **Service Networking API (se solicitar)**
    - Selecione **Use an automatically allocated IP range in your network**.
    - Clique em **Continue.**
    - Clique em **Create connection** e aguarde alguns minutos.
- Após finalizar, em **“Connections”**, **Autorized Networks**, clique em **"Adicionar Rede (Add Network)".**
    - Em **New Network**, insira as seguintes informações:
        - **Nome:** Public Access (Apenas para testes)
        - **Network:** 0.0.0.0/0
        - Clique em **Done**.
        - Clique em **Save** e aguarde finalizar a edição do Cloud SQL Instance.

PS: Para ambientes de produção, é recomendado utilizar apenas a Rede Privada para o acesso ao banco de dados. 
⚠️ Nunca fornecer acesso à rede pública (0.0.0.0/0) para os banco de dados de produção.

**Chegando até aqui, você concluiu a implementação da primeira parte do Projeto Hands-on e fez a implementação dos recursos em múltiplos provedores de Cloud utilizando o Terrraform! Parabéns! 🚀🎉**


# MultiCloudDevOps - Missão 2

## :computer: Amazon Web Services

1. Execute os seguintes comandos para provisionar os recursos de infraestrutura:👋

2. Clique em Add user, insira o nome luxxy-covid-testing-system-pt-app1 e clique em Next para criar o usuário do tipo programmatic.👋


![image](https://user-images.githubusercontent.com/76752875/232621454-11b48ace-5934-41f7-86f9-f7a7e8396bf3.png)


3. Após avançar, em Set permissions, clique no botão Attach existing policies directly.👋

![image](https://user-images.githubusercontent.com/76752875/232621552-9df75114-9dc3-41fa-9ff8-9a1800e9eb21.png)

4. Digite AmazonS3FullAccess em Filter distributions by text, property or value e aperte Enter. 👋

5. Selecione AmazonS3FullAccess. 👋

6. Selecione AmazonS3FullAccess👋

![image](https://user-images.githubusercontent.com/76752875/232621838-65d24999-0b30-41df-8a2f-431f2461771d.png)

7. Clique em Next👋

8. Revise todos os detalhes

9. Clique em Create user

## :Passos para fazer o download da chave de acesso

10. Acesse o usuário luxxy-covid-testing-system-pt-app1👋

11. Clique em Security credentials👋

12. Navegue até a seção Access keys👋
 
13. Clique em Create access key 👋

![image](https://user-images.githubusercontent.com/76752875/232622726-1a84ff5c-e53a-4048-a520-da64d87e78bd.png)

13.Selecione Command Line Interface (CLI) e I understand the above recommendation and want to proceed to create an access key. 👋

14. Clique em Next.👋

15. Clique em Create access key.👋

16. Clique em Download .csv file.👋

17. Após o download finalizar, clique em Done.👋

18. Com o download feito, renomeie o .csv para accessKeys.csv👋

## :Google Cloud Platform (GCP)

19. Navegue até a Cloud SQL instance e crie um novo usuário app com a senha welcome123456 no Cloud SQL MySQL database👋

20. Se conecte ao Google Cloud Shell👋

21. Faça o download dos arquivos da missão 2 diretamente para o Cloud Shell usando o comando wget abaixo:👋

```bash
  cd
  mkdir mission2_pt
  cd mission2_pt
  wget https://tcb-public-events.s3.amazonaws.com/icp/mission2.zip
  unzip mission2.zip
```

22. Conecte ao MySQL DB em execução no Cloud SQL (assim que aparecer a janela para colocar a senha, insira welcome123456)👋

```bash
  mysql --host=<public_ip_cloudsql> --port=3306 -u app -p
```

23. Após estar conectado ao banco de dados da instância, crie a tabela de produtos para testes.👋


```bash
  use dbcovidtesting;
  source mission2/pt/db/create_table.sql;
  show tables;
  exit;
```

24. Habilite a Cloud Build API através do Cloud Shell.👋


```bash
  # Comando para habilitar Cloud Build API

  gcloud services enable cloudbuild.googleapis.com
```

## :Known issue during this step


```bash
  ERROR: (gcloud.builds.submit) INVALID_ARGUMENT: could not resolve source: googleapi: Error 403: 989404026119@cloudbuild.gserviceaccount.com does not have storage.objects.get access to the Google Cloud Storage object., forbidden

  Para solucionar:

  1. Acesse o IAM & Admin;
  2. Clique na sua Cloud Build Service Account

  Exemplo: 989404026119@cloudbuild.gserviceaccount.com Cloud Build Service Account

  3. Na sua Cloud Build Service Account, do lado direito, clique em Edit principal
  4. Clique em Add another role (Adicionar outra função);
  5. Clique em Select Role, e filtre por Storage Admin ou gcs. Selecione Storage Admin (Full control of GCS resources).
  6. Clique em Save and retorno para o Cloud Shell.
```

25. Faça o Build da Docker image e suba para o Google Container Registry. Por gentileza, substitua o <PROJECT_ID> com o My First Project ID.👋

```bash
  cd ~/mission2_pt/mission2/pt/app
  gcloud builds submit --tag gcr.io/<PROJECT_ID>/luxxy-covid-testing-system-app-pt
```

26. Abra o Cloud Editor e edite o Kubernetes deployment file (luxxy-covid-testing-system.yaml) e atualize as variáveis abaixo (em vermelho) com o seu <PROJECT_ID> no caminho da imagem Docker no Google Container Registry, AWS Bucket, AWS Keys (do arquivo luxxy-covid-testing-system-pt-app1.csv) e o IP Privado do Cloud SQL Database.👋


```bash
  cd ~/mission2_pt/mission2/pt/kubernetes
  luxxy-covid-testing-system.yaml

  image: gcr.io/<PROJECT_ID>/luxxy-covid-testing-system-app-pt:latest

  - name: AWS_BUCKET
  value: "luxxy-covid-testing-system-pdf-pt-xxxx"
  - name: S3_ACCESS_KEY
  value: "xxxxxxxxxxxxxxxxxxxxx"
  - name: S3_SECRET_ACCESS_KEY
  value: "xxxxxxxxxxxxxxxxxxxx"
  - name: DB_HOST_NAME
  value: "172.21.0.3"
  
```

## :computer: Atenção entrar via console e pegar a conexao no GKE clicar em "CONECTAR" 👋👋👋👋👋👋👋👋👋👋

27. Se conecte ao GKE (Google Kubernetes Engine) cluster via Console (seguir video).👋

28. Faça o Deploy da aplicação COVID-19 Testing Status System no Cluster.👋


```bash
  cd ~/mission2_pt/mission2/pt/kubernetes
  kubectl apply -f luxxy-covid-testing-system.yaml
```

30. Você deve visualizar a aplicação up & running! Congrats! 🎉👋

![image](https://user-images.githubusercontent.com/76752875/232625873-208e9993-2f13-4514-88f7-dcb0218ac66e.png)

# MultiCloudDevOps - Missão 3

## :computer: Google Cloud Platform - Passos para Migração do Banco de Dados MySQL

1. Conectar ao Google Cloud Shell.👋

2. Download o dump do banco de dados.👋

```bash
  cd
  mkdir mission3_pt
  cd mission3_pt
  wget https://tcb-public-events.s3.amazonaws.com/icp/mission3.zip
  unzip mission3.zip
 ```

3. Conectar ao banco de dados MySQL no Cloud SQL. Senha: welcome123456.👋


```bash
  mysql --host=<public_ip_address> --port=3306 -u app -p
 ```
 
4. Importar o dump do banco de dados no Cloud SQL.👋

```bash
 use dbcovidtesting;
 source ~/mission3_pt/mission3/pt/db/db_dump.sql
 ```

5. Checar se os dados foram importados com sucesso.👋 

```bash
 SELECT * FROM records;
 exit;
 ```

## :computer: Amazon Web Services - Passos para a Migração dos arquivos PDF

1. Conectar no AWS Cloud Shell

2. Download dos arquivos PDF (Comprovante de teste negativo escaneado em PDF)

```bash
 mkdir mission3_pt
 cd mission3_pt
 wget https://tcb-public-events.s3.amazonaws.com/icp/mission3.zip
 unzip mission3.zip
 ```
3. Sincronizar os arquivos PDF com o seu bucket criado no AWS S3 usado para o COVID-19 Testing Status System. Altere o nome do bucket para o seu bucket.

```bash
 cd mission3/pt/pdf_files
 aws s3 sync . s3://luxxy-covid-testing-system-pdf-pt-xxxx
 ```
 
 4. Testar a aplicação. Ao testar a aplicação e navegar na opção "Ver registros" você deverá ser capaz de visualizar os dados importados!
  

![image](https://user-images.githubusercontent.com/76752875/233845753-0f6c726d-bef5-4e0d-ab29-5f08e4b7499d.png)


<p align="center">
⚡ Documentação 👋
    (https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
</p> 







