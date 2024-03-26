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

> 	<span style="color:#ffc000">Cuidado! Dependendo da versão do pandas, ele poderá dar erro caso os tipos de dados agrupados não sejam totalmente numéricos, para evitar é preciso tratar o groupby</span>

```
dados.groupby('Tipo').mean(numeric_only=True)
```

<span style="color:#00b0f0">Exemplo:</span> Agrupar a partir da coluna 'Tipo', selecionando apenas dados da coluna 'Valor' com visualização e formato de dataframe, ordenando do menor para o maior.

```
dados.groupby('Tipo')[['Valor']].mean().sort_values('Valor')
```

**.plot():** plotagem de gráfico a partir da query selecionada do dataframe

	Principais parâmetros do método .plot():
	
	1. kind: Especifica o tipo de gráfico a ser plotado. Alguns valores são:
	    - 'line': Gráfico de linha (padrão)
	    - 'bar': Gráfico de barras verticais
	    - 'barh': Gráfico de barras horizontais
	    - 'scatter': Gráfico de dispersão
	    - 'hist': Histograma
	    - 'box': Diagrama de caixa
	    - 'kde': Estimativa de densidade kernel
	    - 'pie': Gráfico de pizza
	2. x: Nome ou posição da coluna a ser usada no eixo x do gráfico.
	3. y: Nome ou posição da coluna a ser usada no eixo y do gráfico.
	4. ax: Objeto do eixo Matplotlib em que o gráfico será desenhado.
	5. subplots: Se True, cria um subplot para cada coluna.
	6. figsize: Tamanho da figura a ser criada.
	7. title: Título do gráfico.
	8. grid: Se True, desenha as linhas de grade no gráfico.
	9. legend: Se True, mostra a legenda.
	10. color: Cor do gráfico.
	11. label: Rótulo para a legenda.
	12. style: Estilo do gráfico (por exemplo, '-o' para linha com pontos).

<span style="color:#00b0f0">Exemplo:</span>  Gráfico da variável dados_graph, gráfico com barras horizontais, título 'Valores Imóveis', tamanho da figura '14, 8', cor rosa

```
dados_graph = dados.groupby('Tipo')[['Valor']].mean().sort_values('Valor')
dados_graph.plot(kind='barh', title='Valores Imóveis', figsize=(14,8), color='pink')
```

![[Pasted image 20240324202253.png]]

**.query():** permite que sejam selecionadas linhas de acordo com uma condição específica

<span style="color:#00b0f0">Exemplo:</span>  Selecionar apenas o imóveis comerciais da tabela

```
imoveis_comerciais = ['Conjunto Comercial/Sala', 
                      'Prédio Inteiro', 'Loja/Salão', 
                      'Galpão/Depósito/Armazém', 
                      'Casa Comercial', 'Terreno Padrão',
                      'Loja Shopping/ Ct Comercial',
                      'Box/Garagem', 'Chácara',
                      'Loteamento/Condomínio', 'Sítio',
                      'Pousada/Chalé', 'Hotel', 'Indústria']

dados.query('@imoveis_comerciais in Tipo')
```

**.value_counts():** conta quantas vezes o tipo de dado aparece no database. Retorna uma series
**.value_counts(normalize=True)**: retorna o mesmo dado em formato de porcentagem
**.to_frame():** coverte uma series em um dataframe
**.rename():** renomeia uma coluna

```
df_exemplo.rename(columns={'Tipo': 'Percentuais'}, inplace=True)
```

# <span style="color:#7030a0"> Tratando e filtrando dados</span>

**.isnull():** retorna true ou false para dados nulos
**.isnull().sum():** retorna a quantidade de dados nulos
**.fillna():** substitui os valores nulos pelo valor descrito entre parenteses, geralmente é 0
**.drop():** é usado para remover linhas e colunas.
	Parâmetros:
	- axis: utlizado para especificar a remoção de linhas ou colunas, 1 para colunas e 0 para linhas
	- inplace: especificar que as alterações serão aplicadas no dataframe, true ou false
**.to_csv():** salva o dataframe em arquivo csv. Ao salvar ele cria um índice novo para a tabela mesmo que ela ja tenha uma. Para salvar sem criar o índice deve-se passar o parâmetro <span style="color:#00b0f0">index=false</span>

> O Pandas oferece diversos métodos para salvar arquivos em diferentes formatos. Alguns exemplos são:

- `to_csv()`: salva o DataFrame em um arquivo CSV (Comma-Separated Values);
- `to_excel()`: salva o DataFrame em um arquivo Excel;
- `to_json()`: salva o DataFrame em um arquivo JSON (JavaScript Object Notation).

# <span style="color:#7030a0"> Manipulação de dados</span>

<span style="color:#ffc000">Criando colunas numéricas:</span>

```
dados['Valor_por_mes'] = dados['Valor'] + dados['Condominio']
```

Foi criada a coluna Valor por mês, passando como dados a somatória dos dados contidos nas colunas Valor e Condomínio