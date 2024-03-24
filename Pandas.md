<span style="color:#ffc000">Material Utilizado:</span>
- arquivo csv
- google colab
- notebook google colab

```
import pandas as pd

url = link csv
pd.read_csv(url)
```

**read_csv:** lê o conteúdo apenas pela separação por vírgulas, deve-se passar o parâmetro sep='' para especificar o tipo de separador da tabela

```
pd.read_csv(url, sep = ';')
```