
> A orquestração de dados é um **processo automatizado** que **controla uma rede de tarefas**, criando relações lógicas de dependência entre elas. Além disso, a orquestração permite o **monitoramento** dessa rede, chamado _**pipeline**_

## <span style="color:#ffc000">Conheça as ferramentas de orquestração de dados</span> 

Existem diversas **ferramentas específicas para orquestração de dados**, que nos fornecem soluções completas. Elas permitem monitorar o andamento das atividades e estabelecer relações complexas entre as partes, com **diferentes gatilhos** (ou triggers, em inglês). Porém, elas podem ter propósitos finais diferentes. Conheça algumas das ferramentas:

### Apache Airflow

Esse é o **nome mais conhecido** quando falamos de orquestração de dados. O **Apache Airflow** reúne todos esses elementos em **Python**, a linguagem de programação predominante na área de Engenharia de Dados, e em um ambiente de **código aberto** (ou _open source_), onde há uma **comunidade ativa de desenvolvedores**. A ferramenta foi criada em 2014 para lidar com o fluxo de informações do aplicativo Airbnb e, em 2016, se tornou um **projeto _open source_ da Apache**.

O Airflow se baseia no conceito de **DAGs**, uma sigla para **Directed Acyclic Graph (Grafo Acíclico Dirigido)**. As DAGs agrupam tarefas e as relações entre elas, definindo como deve ser a execução do processo. Uma tarefa não pode ter início no seu fim, por isso, não completa um ciclo! Mas a ferramenta permite criar lógicas complexas, em que a execução depende de todos os passos, ou de pelo menos um dos passos anteriores ter sido completado, ou nenhum.

<span style="color:#00b0f0">Exemplo de uma DAG:</span> 

![[Pasted image 20240408193626.png]]

### Dagster

O **[Dagster](https://dagster.io/)** é um concorrente que se propõe a **resolver problemas** que os desenvolvedores hoje enfrentam com o Airflow. A ferramenta surgiu com a proposta de solucionar alguns problemas específicos que o Airflow não consegue resolver, como testabilidade, organização e escalabilidade_._

### AWS Step Functions

Diferentemente do Airflow, que oferece uma camada de orquestração de dados em cima de outros serviços, o [AWS Step Functions](https://aws.amazon.com/pt/step-functions/) integra serviços da AWS. A grande vantagem da ferramenta é que não há necessidade de saber desenvolver códigos, e você pode realizar todo o seu trabalho diretamente na sua interface.

### Data Factory

Já o [Data Factory](https://azure.microsoft.com/pt-br/products/data-factory) é uma ferramenta da Azure que se propõe não apenas a orquestrar, como também fornecer os recursos necessários para fazer o processamento de dados dentro do pipeline. Lembre que, quando falamos em processar, queremos dizer filtrar e formatar para deixar os dados limpos.

### Flyte

O [Flyte](https://flyte.org/) é uma alternativa de código aberto, com maior foco em Machine Learning e, para isso, possui mecanismos específicos. Por exemplo, o modelo de programação e a integração com outros ecossistemas.

## <span style="color:#ffc000">Fatores para levar em consideração ao escolher a ferramenta de orquestração</span>


- Precificação
- Tamanho da equipe
- Tarefas a serem desenvolvidas