
> O Apache Airflow é uma plataforma para criar, agendar e monitorar fluxos de trabalho de forma programática. 


Baseado em quatro princípios: dinâmico, Python, extensível e elegante. É escalável e utiliza o conceito de DAGs para representar o fluxo de tarefas. Possui serviços como Scheduler, Executor e Servidor web. Pode ser executado no Python em servidores Linux ou no Docker em computadores pessoais.

### DAGS

DAG é uma abreviação para "Directed Acyclic Graph", que em português significa "Gráfico Acíclico Direcionado".

Em termos simples, um DAG é um tipo de estrutura de dados que consiste em nós (também conhecidos como vértices) conectados por arestas direcionadas, onde as arestas têm uma direção específica e não formam ciclos, sempre com início, meio e fim. Isso significa que você pode percorrer os nós seguindo a direção das setas, mas nunca voltar a um nó que já visitou através dessas arestas.

<span style="color:#00b0f0">Exemplo de gráfico em DAG:</span>

![[Pasted image 20240413133948.png]]

<span style="color:#00b0f0">Exemplo de código em DAG:</span>


1.
![[Pasted image 20240413134418.png]]

2.
```python
import networkx as nx
import matplotlib.pyplot as plt

# Criando um objeto do tipo DAG
DAG = nx.DiGraph()

# Definindo as tarefas e suas dependências
tasks = {
    "A": ["B", "C"],
    "B": ["D"],
    "C": ["D"],
    "D": ["E"],
    "E": ["F"],
    "F": [],
}

# Adicionando as tarefas e suas dependências ao DAG
for task, dependencies in tasks.items():
    DAG.add_node(task)
    for dependency in dependencies:
        DAG.add_edge(task, dependency)

# Visualizando o DAG
pos = nx.spring_layout(DAG)  # Posicionamento dos nós
nx.draw(DAG, pos, with_labels=True, node_color='skyblue', node_size=1500, font_size=12, font_weight='bold', arrowsize=20)
plt.show()
```

Neste código, as tarefas são representadas como chaves em um dicionário, onde os valores são listas de dependências para cada tarefa. As tarefas e suas dependências são então adicionadas ao DAG, e em seguida o DAG é visualizado. Este é um exemplo mais simples que alcança o mesmo resultado.

### Quando o Airflow não é recomendado

 O Airflow não é uma solução de streaming de dados. As tasks não movem dados de um lado para o outro, embora possam ser trocados metadados entre si. Espere-se que os fluxos de trabalho sejam estáticos, ou com poucas mudanças.
 
Espere-se também que os fluxos de trabalho sejam semelhantes de uma execução para outra, o que permite clareza e facilidade do suporte e gerenciamento, para garantir a sua continuidade e perpetuidade.

### Principais componentes para o funcionamento do Airflow

Scheduler, responsável pelo agendamento das Dags e envio das tasks para os workers.
Executor, responsável pela execução das tarefas que caminham as tasks para os workers.
Servidor web, interface web para o usuário interagir e gerenciar as Dags e as tasks.
Uma pasta com Dags, aonde armazenamos os códigos Python.
Metadatos, um banco de dados que atende como repositório da ferramenta, utilizando pelo Scheduler e pelo executor para armazenar os estados das execuções.