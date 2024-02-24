# projeto_engdados02
>Projeto2 - Processamento de dados em streaming gerados por sensores de um parque eólico. Utilizando Python, AWS S3, AWS Kinesis Stream, AWS Firehose, AWS Glue, AWS Athena e SQL

## Objetivo:

Esse sistema tem como objetivo processar dados de sensores de um parque eólico. As aplicações produtoras de dados foram desenvolvidas em Python no Google Colab. Cada uma das aplicações produzem diferentes dados a cada 10 segundos. 
Usaremos o Kinesis Data Stream para receber o streaming de dados.

Após isso, usaremos o Kinesis Firehose para realizar a entrega dos dados, no qual a origem é o stream e o destino é um bucket criado no S3.

Utilizaremos o Glue Catalog para criar um database baseado nos dados que estão no S3 (em formato JSON) e um Crawler para descobrir a estrutura dos dados de forma automática.

Após isso, é a vez do Glue Job para que possamos salvar nossos dados em um novo bucket no formato Parquet. Não será realizada nenhuma transformação nos dados.

Com os dados no formato Parquet e em um novo bucket, iremos usar a ferramenta Athena para realizar consultas com SQL.

![esquema](imagem.png)

## Resolução:

Foram criados 3 programas em Python utilizando Google colab para representar as aplicações produtoras de dados. Após isso toda o processo de engenharia de dados foi realizado no AWS.

