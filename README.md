# Azure Databricks: Guia Prático

Este repositório contém um guia prático para utilização do Azure Databricks, desde a configuração inicial até a análise de dados com Spark.

## 📋 Índice

- [Introdução](#-introdução)
- [Entendendo o Azure Databricks](#-entendendo-o-azure-databricks)
- [Azure Databricks Exercises](#-azure-databricks-exercises)
- [Explore o Azure Databricks](#-explore-o-azure-databricks)
  - [Provisionando um Databricks](#-provisionando-um-databricks)
  - [Criando um Cluster Manualmente](#-criando-um-cluster-manualmente)
  - [Usando o Spark para Analisar Dados](#-usando-o-spark-para-analisar-dados)
- [Encerramento](#-encerramento)
- [Materiais de Apoio](#-materiais-de-apoio)

## 🎯 Introdução

O Azure Databricks é uma plataforma de análise unificada que combina o melhor do Apache Spark com a simplicidade e escalabilidade do Azure. Este guia prático irá ajudá-lo a dominar os conceitos fundamentais e aplicações práticas do Azure Databricks.

## 🔍 Entendendo o Azure Databricks

O Azure Databricks oferece:

- Ambiente colaborativo para análise de dados
- Processamento distribuído com Apache Spark
- Integração nativa com serviços Azure
- Suporte a múltiplas linguagens (Python, Scala, R, SQL)
- Recursos de IA e machine learning

## 💻 Azure Databricks Exercises

### Exercícios Práticos

1. **Configuração Inicial**

   - Criação de workspace
   - Configuração de permissões
   - Importação de notebooks

2. **Manipulação de Dados**

   - Carregamento de datasets
   - Transformações básicas
   - Visualizações

3. **Análise Avançada**
   - Processamento de dados em larga escala
   - Machine learning
   - Otimização de performance

## 🚀 Explore o Azure Databricks

### Provisionando um Databricks

1. Acesse o portal Azure.
2. Crie um novo recurso.
3. Selecione "Azure Databricks".
4. Configure:
   - Nome do workspace
   - Região
   - Tipo de preço
   - Rede virtual (opcional).

### Criando um Cluster Manualmente

1. Acesse o workspace do Azure Databricks.
2. No menu lateral, clique em **Clusters**.
3. Clique no botão **Create Cluster**.
4. Preencha as informações básicas:
   - **Cluster Name**: Escolha um nome para o cluster (ex.: `cluster-iniciante`).
   - **Cluster Mode**: Selecione "Standard".
   - **Databricks Runtime Version**: Escolha uma versão compatível (ex.: `11.3 LTS`).
   - **Worker Type**: Escolha o tipo de nó (ex.: `Standard_DS3_v2`).
   - **Number of Workers**: Defina o número de nós (ex.: 2).
5. Clique em **Create Cluster** para iniciar a criação.
6. Aguarde até que o cluster esteja no estado **Running**.

### Usando o Spark para Analisar Dados

```python
# Exemplo de análise com Spark
from pyspark.sql import SparkSession
from pyspark.sql.functions import *

# Inicialização
spark = SparkSession.builder.appName("Análise de Dados").getOrCreate()

# Carregamento de dados
df = spark.read.format("csv").load("/mnt/data/raw")

# Análise exploratória
df.show()
df.printSchema()
df.describe().show()

# Transformações
df_transformed = df.select(
    col("id"),
    upper(col("nome")).alias("nome_upper"),
    current_timestamp().alias("data_processamento")
)
```

## 🎓 Encerramento

Este guia forneceu uma introdução prática ao Azure Databricks, cobrindo desde a configuração inicial até a análise de dados com Spark. Continue explorando os recursos e funcionalidades para maximizar o potencial da plataforma.

## 📚 Materiais de Apoio

### Documentação Oficial

- [Microsoft Learn - Azure Databricks](https://learn.microsoft.com/pt-br/azure/databricks/)
- [Documentação do Apache Spark](https://spark.apache.org/docs/latest/)

### Cursos e Tutoriais

- [Azure Databricks Fundamentals](https://learn.microsoft.com/pt-br/training/paths/azure-databricks-fundamentals/)
- [Spark Programming Guide](https://spark.apache.org/docs/latest/rdd-programming-guide.html)

### Comunidade

- [Stack Overflow - Azure Databricks](https://stackoverflow.com/questions/tagged/azure-databricks)
- [GitHub - Exemplos Azure Databricks](https://github.com/Azure/azure-databricks-examples)
