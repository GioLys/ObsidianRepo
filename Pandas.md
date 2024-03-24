## <span style="color:#ffc000">Material Utilizado:</span>

- ==**arquivo csv**==
- ==**google colab**==
- ==**notebook google colab**==

# <span style="color:#7030a0">Conhecendo e importando dados</span>

```
import pandas as pd

url = link csv
pd.read_csv(url)
```

**.read_csv():** lê o conteúdo apenas pela separação por vírgulas, deve-se passar o parâmetro sep='' para especificar o tipo de separador da tabela

> 	Outros formatos de leitura de dados: read_excel(), read_json(), read_html(), read_sql().

```
pd.read_csv(url, sep = ';')
```

**.head() e .tail():** retorna uma quantidade limitada de linhas, se não for passado a quantidade de linhas no parâmetro, retorna 5 linhas. Head puxa as linhas do ínicio e tail puxa as linhas do final
**.type():** retorna o tipo de dados dentro de uma variável

# <span style="color:#7030a0">Características dos dados</span>

**.shape:** retorna uma tupla com a quantidade de linhas e a quantidade de colunas
**.columns:** retorna o nome de todas as colunas e o type majoritário
**.info():** retorna as características dos dados de forma detalhada especificando colunas, tipo de dados, quantidade de linhas, et

==Visualização de dados no tipo Series:== ocorre ao realizar a visualização de apenas uma coluna, serão retornados apenas índice e valores
==Visualização de dados no tipo Dataframe:== o retorno dos dados no formato dataframe ocorre sempre ao visualizar mais de uma coluna

# <span style="color:#7030a0">Análise exploratória dos dados</span>

**.mean():** retorna a média da coluna

```
dados = dataframe.csv
dados['Valor].mean()
```

**.groupyby():** agrupa o dataframe a partir de uma coluna, tornando esta coluna o novo <span style="color:#00b0f0">índice</span> do dataframe
	Cuidado! Dependendo da versão do pandas, ele poderá dar erro caso os tipos de dados agrupados não sejam totalmente numéricos, para evitar é preciso tratar o groupby
