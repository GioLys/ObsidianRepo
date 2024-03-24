<span style="color:#ffc000">Material Utilizado:</span>
- arquivo csv
- google colab
- notebook google colab

```
import pandas as pd

url = link csv
pd.read_csv(url)
```

**.read_csv():** lê o conteúdo apenas pela separação por vírgulas, deve-se passar o parâmetro sep='' para especificar o tipo de separador da tabela

> 	Outros formatos de leitura de dados: read_excel(), read_json(), read_json(), read_html(), read_sql().

```
pd.read_csv(url, sep = ';')
```

**.head() e .tail():** retorna uma quantidade limitada de linhas, se não for passado a quantidade de linhas no parâmetro, retorna 5 linhas. Head puxa as linhas do ínicio e tail puxa as linhas do final
**.type():** retorna o tipo de dados dentro de uma variável