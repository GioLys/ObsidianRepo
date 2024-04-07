
1. **Data Lake**: Um data lake é um repositório centralizado de dados brutos, não processados e estruturados, geralmente armazenados em seu formato nativo. Ele é projetado para armazenar grandes volumes de dados de várias fontes em seu estado original. Data lakes são frequentemente utilizados em ambientes onde os tipos e as estruturas dos dados podem variar muito, e onde a análise exploratória e a descoberta de insights são prioridades.
    
2. **Data Warehouse**: Um data warehouse, por outro lado, é um sistema de gerenciamento de dados utilizado para armazenar e analisar dados estruturados de maneira otimizada para consultas e análises de negócios. Os dados em um data warehouse geralmente são organizados e modelados de acordo com um esquema específico, facilitando a recuperação de informações e a geração de relatórios.
    

O conceito de "<span style="color:#00b0f0">data lakehouse</span>" combina aspectos desses dois modelos. Ele propõe uma abordagem híbrida que combina a escalabilidade e a flexibilidade de um data lake com as capacidades de processamento e análise de um data warehouse. Assim, um data lakehouse busca unificar a capacidade de armazenamento de dados brutos e não processados de um data lake com a capacidade de executar análises sofisticadas e consultas complexas em dados estruturados, como em um data warehouse.

## <span style="color:#ffc000">Plataforma Databricks</span> 

A plataforma Databricks é uma plataforma de análise de dados na nuvem que é construída sobre o Apache Spark, uma poderosa estrutura de processamento de big data. Ela fornece um ambiente unificado para análise de dados, permitindo que equipes de dados trabalhem em colaboração usando linguagens como SQL, Python, Scala e R.

A Databricks fornece suporte para construção e gerenciamento de Data Lakes e Data Warehouses, além de funcionalidades avançadas de machine learning e processamento de dados em tempo real.

Quanto ao "data lakehouse" especificamente, a Databricks oferece recursos e funcionalidades que podem ser utilizados para implementar uma arquitetura de data lakehouse. Isso inclui:

1. **Armazenamento de dados**: A Databricks pode ser usada para armazenar dados brutos em seu formato nativo em um data lake, geralmente utilizando serviços de armazenamento na nuvem como o Azure Data Lake Storage ou o Amazon S3.
    
2. **Processamento de dados**: A plataforma Databricks permite o processamento distribuído e paralelo de grandes volumes de dados usando o Apache Spark. Isso possibilita a realização de transformações, limpeza e preparação de dados em escala.
    
3. **Consulta e análise**: Com a capacidade de executar consultas SQL, análises e machine learning em larga escala, a Databricks permite que os usuários realizem análises complexas e gerem insights a partir dos dados armazenados no data lakehouse.
    
4. **Gerenciamento de metadados e governança**: A Databricks oferece recursos para o gerenciamento de metadados, controle de acesso e governança de dados, ajudando a garantir a qualidade e a segurança dos dados em todo o ciclo de vida.

### DeltaLake

Delta Lake é uma tecnologia desenvolvida pela Databricks que estende o Apache Spark para lidar com problemas comuns encontrados em ambientes de big data, como garantir a integridade dos dados, escalabilidade e confiabilidade em operações de ingestão, atualização e exclusão de dados.

A Delta Lake adiciona funcionalidades como controle de transações ACID (Atomicidade, Consistência, Isolamento e Durabilidade) para operações de leitura e gravação, gerenciamento de metadados para rastrear versões e esquemas de dados, suporte para otimização de consultas e atualizações incrementais. Isso permite que os usuários mantenham dados de alta qualidade e consistentes em seus data lakes.

### Photon

Photon é um motor de consulta vetorizado nativo da Databricks de alto desempenho que executa suas cargas de trabalho SQL e chamadas de API DataFrame de maneira mais rápida para reduzir seu custo total por carga de trabalho.

Aqui estão as principais características e vantagens de usar o Photon:

- Suporte para SQL e operações equivalentes de DataFrame com tabelas Delta e Parquet.
- Consultas aceleradas que processam dados mais rapidamente e incluem agregações e junções.
- Melhor desempenho quando os dados são acessados repetidamente do cache de disco.
- Desempenho robusto de varredura em tabelas com muitas colunas e muitos arquivos pequenos.
- Escrita mais rápida em Delta e Parquet usando UPDATE, DELETE, MERGE INTO, INSERT e CREATE TABLE AS SELECT, incluindo tabelas amplas que contêm milhares de colunas.
- Substitui junções de classificação e mesclagem por junções de hash.
