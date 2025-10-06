# 🚀 Desafio DIO - Primeira Stack com AWS CloudFormation

Este repositório contém a entrega do *desafio de AWS CloudFormation da DIO, onde implementei minha primeira stack utilizando o serviço de **Infraestrutura como Código (IaC)* da AWS.

---

## 📌 Objetivo
- Aplicar os conceitos aprendidos em um laboratório prático.  
- Criar uma stack no CloudFormation a partir de um arquivo *YAML*.  
- Provisionar recursos automaticamente na AWS (no meu caso, um bucket S3).  
- Documentar o processo e compartilhar no GitHub.  

---

## 🛠️ Passo a Passo realizado

1. Criei o arquivo template.yaml com a definição de um bucket S3:
   ```yaml
   AWSTemplateFormatVersion: '2010-09-09'
   Description: 'Primeiro template CloudFormation - cria um bucket S3'

   Parameters:
     BucketName:
       Type: String
       Description: Nome do bucket (precisa ser único no mundo)
       AllowedPattern: '^[a-z0-9.-]{3,63}$'

   Resources:
     LabBucket:
       Type: AWS::S3::Bucket
       Properties:
         BucketName: !Ref BucketName
         PublicAccessBlockConfiguration:
           BlockPublicAcls: true
           BlockPublicPolicy: true
           IgnorePublicAcls: true
           RestrictPublicBuckets: true

   Outputs:
     BucketNameOut:
       Value: !Ref LabBucket
       Description: Nome do bucket criado

2.	Acessei o Console da AWS → CloudFormation → Criar pilha → Upload de template.
3.	Subi o arquivo template.yaml e defini o nome do bucket como gabi-bucket-dio2025.
4.	Acompanhei a execução até o status CREATE_COMPLETE.
5.	Validei no serviço Amazon S3 que o bucket foi criado com sucesso.

Evidencias:
- Stack criada no CloudFormation
- Bucket no serviço S3

Conclusão

Com este desafio consegui:
-  Compreender melhor o conceito de Infraestrutura como Código (IaC).
-  Criar e gerenciar recursos da AWS de forma automatizada via CloudFormation.
-  Documentar e versionar meu aprendizado no GitHub.

Este foi meu primeiro passo para usar CloudFormation em projetos mais avançados 🚀
