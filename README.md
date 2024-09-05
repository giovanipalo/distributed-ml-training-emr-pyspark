# Projeto de Treinamento Distribuído de Machine Learning com PySpark no Amazon EMR

## Visão Geral

Este é um projeto avançado focado na implementação e deploy de uma stack para treinamento distribuído de Machine Learning utilizando PySpark no Amazon Elastic MapReduce (EMR). O objetivo principal é aproveitar o processamento distribuído para treinar modelos de Machine Learning em larga escala, otimizando o uso de recursos e reduzindo o tempo necessário para o treinamento.

Com o uso do **PySpark**, uma interface Python para o Apache Spark, o projeto aborda desafios comuns de Big Data, permitindo análises complexas e processamento de grandes volumes de dados de forma eficiente.

## Estrutura do Projeto

O projeto é estruturado da seguinte maneira:

1. **Configuração do Cluster EMR**:
   - Configuração de um cluster EMR na AWS para executar tarefas de Machine Learning distribuídas.
   - Utilização de serviços AWS para gerenciamento de recursos e monitoramento.

2. **Stack de Treinamento**:
   - Desenvolvimento de um stack de treinamento escalável e resiliente.
   - Utilização de PySpark para processamento distribuído de dados e treinamento de modelos.

3. **Automatização e Integração Contínua**:
   - Implementação de scripts e templates de infraestrutura como código para garantir replicabilidade e consistência do ambiente.
   - Automatização do deploy e integração contínua.

4. **Melhores Práticas em Ciência de Dados**:
   - Foco na preparação de dados, seleção de modelos e avaliação de desempenho em um contexto distribuído.
   - Adaptação a desafios de dados em escala de petabytes para obter insights profundos a partir de grandes conjuntos de dados.

## Objetivos

- **Escalabilidade**: Aproveitar o processamento distribuído para treinar modelos em larga escala de forma eficiente.
- **Otimização de Recursos**: Reduzir o tempo de treinamento e otimizar o uso dos recursos disponíveis.
- **Robustez**: Criar uma solução que possa lidar com desafios de dados em escala de petabytes.
- **Replicabilidade**: Garantir a consistência e replicabilidade do ambiente através de infraestrutura como código.

## Tecnologias Utilizadas

- **PySpark**: Interface Python para Apache Spark, utilizada para o processamento de dados e treinamento de modelos.
- **Amazon EMR**: Serviço da AWS para gerenciamento de clusters de processamento de Big Data.
- **Infraestrutura como Código**: Scripts e templates para automação e integração contínua.

## Instruções para Execução

1. **Preparação do Ambiente**

   - Abra o terminal ou prompt de comando e navegue até a pasta onde você colocou os arquivos do projeto. Evite usar espaços ou acentos no nome da pasta.

2. **Construção da Imagem Docker**

   ```bash
   docker build -t terraform-image:p2 .
   ```

3. **Criação e execução do Contâiner Docker**

   ```bash
   docker run -dit --name p2 -v ./IaC:/iac terraform-image:p2 /bin/bash
   ```
No Windows, substitua **./IaC** pelo caminho completo da pasta, por exemplo: **C:\SeuCaminho\IaC**.

4. **Verificação das Versões**

   - Verifique as versões do Terraform e do AWS CLI com os seguintes comandos:

   ```bash
   terraform version
   aws --version
   ```
5. **Configuração dos Arquivos**

   - Edite os arquivos **config.tf** e **terraform.tfvars** para incluir seu ID da AWS onde indicado.
   - No script **projeto2.py**, adicione seu ID da AWS e suas chaves AWS onde indicado.

6. **Criação do Bucket S3**

   - Crie manualmente o bucket S3 com o nome **p2-terraform-<id-aws>**, substituindo **<id-aws>** pelo seu ID da AWS.

7. **Execução do Terraform**

   - Execute os comandos abaixo para inicializar e aplicar a configuração do Terraform:

```bash
terraform init
terraform apply
```
8. **Monitoramento**

- Acompanhe a execução do pipeline pela interface da AWS.

## Utilização do Docker

Para este projeto, o Docker foi integrado ao ambiente Linux (Ubuntu) para otimizar o desenvolvimento e assegurar um ambiente consistente e eficiente. Utilizando contêineres Docker, conseguimos garantir a portabilidade dos aplicativos, facilitando a configuração e o gerenciamento de dependências.
