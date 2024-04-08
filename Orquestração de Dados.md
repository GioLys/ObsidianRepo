
> A orquestração de dados é um **processo automatizado** que **controla uma rede de tarefas**, criando relações lógicas de dependência entre elas. Além disso, a orquestração permite o **monitoramento** dessa rede, chamado _**pipeline**_

## <span style="color:#ffc000">Conheça as ferramentas de orquestração de dados</span> 

Existem diversas **ferramentas específicas para orquestração de dados**, que nos fornecem soluções completas. Elas permitem monitorar o andamento das atividades e estabelecer relações complexas entre as partes, com **diferentes gatilhos** (ou triggers, em inglês). Porém, elas podem ter propósitos finais diferentes. Conheça algumas das ferramentas:

### **Apache Airflow**

Esse é o **nome mais conhecido** quando falamos de orquestração de dados. O **Apache Airflow** reúne todos esses elementos em **Python**, a linguagem de programação predominante na área de Engenharia de Dados, e em um ambiente de **código aberto** (ou _open source_), onde há uma **comunidade ativa de desenvolvedores**. A ferramenta foi criada em 2014 para lidar com o fluxo de informações do aplicativo Airbnb e, em 2016, se tornou um **projeto _open source_ da Apache**.

O Airflow se baseia no conceito de **DAGs**, uma sigla para **Directed Acyclic Graph (Grafo Acíclico Dirigido)**. As DAGs agrupam tarefas e as relações entre elas, definindo como deve ser a execução do processo. Uma tarefa não pode ter início no seu fim, por isso, não completa um ciclo! Mas a ferramenta permite criar lógicas complexas, em que a execução depende de todos os passos, ou de pelo menos um dos passos anteriores ter sido completado, ou nenhum.

<span style="color:#00b0f0">Exemplo de uma DAG:</span> 

![[Pasted image 20240408193626.png]]

