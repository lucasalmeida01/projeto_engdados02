# projeto_engdados02
>Projeto2 - Processamento de dados em streaming gerados por sensores de um parque eólico. Utilizando Python, AWS S3, AWS Kinesis Stream, AWS Firehose, AWS Glue, AWS Athena e SQL

## Objetivo:

Esse sistema tem como objetivo processar dados de sensores de um parque eólico. As aplicações produtoras de dados foram desenvolvidas em Python no google Colab. Cada uma das aplicações produz diferentes dados a cada 10 segundos. 
Usaremos o Kinesis Data Stream para receber o streaming de dados, nas aplicações temos a conexão com o stream.

Após isso, usaremos o Kinesis Firehose para realizar a entrega dos dados, no qual a origem é o stream e o destino é um bucket criado no S3.

Depois usaremos o Glue Catalog para criar um database baseado nos dados que estão no S3 (em formato JSON) e um Crawler para descobrir a estrutura dos dados de forma automática.

Iremos utilizar o Glue Job para salvar nossos dados em um novo bucket no formato Parquet.

Com os dados no formato Parquet e em um novo bucket, iremos usar a ferramenta Athena para realizar consultas com SQL.

![esquema](diagrama.png)

## Resolução:

Foram criados 3 programas em Python utilizando Google colab para representar as aplicações produtoras de dados. Após isso toda o processo de engenharia de dados foi realizado no AWS.

