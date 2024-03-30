
# <span style="color:#7030a0">Tipos de dados</span>

### Dados Qualitativos:

Os dados qualitativos descrevem qualidades ou características não numéricas de um objeto ou fenômeno. Eles são geralmente descritivos e não podem ser expressos em termos de quantidade. Os dados qualitativos são frequentemente divididos em várias subcategorias:

1. **Nominais**: Esses dados representam categorias sem ordem ou hierarquia. <span style="color:#00b0f0">Exemplos</span> incluem cor dos olhos, gênero, raça, etc.
    
2. **Ordinais**: Esses dados têm uma ordem específica, mas a diferença entre os valores não é necessariamente uniforme ou mensurável. <span style="color:#00b0f0">Exemplos</span> incluem nível de satisfação (baixo, médio, alto), classificação de filmes (bom, regular, ruim), etc.
    

### Dados Quantitativos:

Os dados quantitativos são mensuráveis e expressos numericamente. Eles podem ser subcategorizados em:

1. **Discretos**: Valores que são contáveis e geralmente inteiros. <span style="color:#00b0f0">Exemplos</span> incluem número de filhos, número de carros em uma garagem, etc.
    
2. **Contínuos**: Valores que podem assumir qualquer valor dentro de um intervalo específico. <span style="color:#00b0f0">Exemplos</span> incluem altura, peso, temperatura, etc.
    

Os dados quantitativos podem ser analisados usando técnicas estatísticas mais avançadas devido à sua natureza numérica, enquanto os dados qualitativos muitas vezes exigem métodos diferentes de análise, como análise de conteúdo, análise de discurso, etc.

# <span style="color:#7030a0">Distribuição de frequência </span>

A distribuição de frequências é uma forma de organizar dados estatísticos para que seja mais fácil entender sua estrutura e padrões. Em essência, ela mostra quantas vezes cada valor ocorre em um conjunto de dados. Este tipo de distribuição é amplamente utilizado em estatística descritiva para resumir grandes conjuntos de dados e para obter uma visão geral da distribuição dos valores.

#### Para criar uma distribuição de frequências, os seguintes passos são seguidos:

1. **Identificação dos valores únicos**: Primeiro, os valores únicos presentes nos dados são identificados. Em conjuntos de dados numéricos, isso significa listar todos os diferentes valores únicos presentes.
2. **Contagem de ocorrências**: Em seguida, a frequência de cada valor único é contada. Isso envolve contar quantas vezes cada valor ocorre nos dados.

![[Pasted image 20240327153133.png]]

3. **Organização dos dados**: Os valores únicos são geralmente organizados em ordem crescente ou decrescente, e suas frequências correspondentes são listadas ao lado deles.

![[Pasted image 20240327153319.png]]

4. **Apresentação visual**: Uma vez que os dados foram organizados e as frequências atribuídas a cada valor, muitas vezes é útil representar essa informação visualmente, através de histogramas, gráficos de barras, ou até mesmo tabelas.

![[Pasted image 20240327153508.png]]

#### 2º opção: Distribuição de frequências qualitativas

```bash
sexo = { 0: 'Masculino',
        1: 'Feminino'}

cor = { 0: 'Indígena',
        2: 'Branca',
        4: 'Preta',
        6: 'Amarela',
        8: 'Parda',
        9: 'Sem declaração'}
```

Utilizaremos **pd.crosstab()** para fazer uma tabulação cruzada de duas frequências, sendo elas cor e sexo:

```
frequencia = pd.crosstab(dados.Sexo, dados.Cor)
```

![[Pasted image 20240327154824.png]]

Faremos o tratamento dos dados para renomear colunas e linhas e retornar a porcentagem das frequências:

```sql
percentual = pd.crosstab(dados.Sexo,
                         dados.Cor,
                         normalize = True) * 100
percentual.rename(index = sexo, inplace = True)
percentual.rename(columns = cor, inplace = True)
```

![[Pasted image 20240327155028.png]]

<span style="color:#00b0f0">Exemplo: </span> Utilizar dados.Renda para calcular a renda média de acordo com sexo e cor a partir da tabela de percentuais

```sql
percentual = pd.crosstab(dados.Sexo,
                         dados.Cor,
                         aggfunc = 'mean',
                         values = dados.Renda)
percentual.rename(index = sexo, inplace = True)
percentual.rename(columns = cor, inplace = True)
percentual
```

![[Pasted image 20240327155440.png]]

Para isso foi utlizado o método de função agregadora que permite que você especifique uma função ou um dicionário de funções para aplicar a diferentes colunas do DataFrame.

# <span style="color:#7030a0">Histograma </span>

Um histograma é um tipo de gráfico de barras utilizado na estatística para representar a distribuição de frequências de um conjunto de dados contínuos ou discretos. Ele divide o intervalo de valores em compartimentos (também chamados de "bins" ou intervalos de classe) e mostra a frequência com que os dados caem em cada compartimento.
### Como funciona:

1. **Divisão em compartimentos**: O intervalo de valores é dividido em um número específico de compartimentos (bins), que são intervalos mutuamente exclusivos e coletivamente abrangentes que cobrem todo o intervalo de valores dos dados.
    
2. **Contagem de ocorrências**: O histograma conta quantas vezes os dados caem em cada compartimento. Isso significa contar quantas observações de dados estão dentro de cada intervalo.
    
3. **Construção do gráfico**: Os compartimentos são representados no eixo horizontal do gráfico, enquanto a frequência (ou densidade de frequência) é representada no eixo vertical. Normalmente, as barras do histograma não têm espaçamento entre elas, pois representam intervalos contínuos.

### Principais características:

- **Forma da distribuição**: O formato do histograma pode indicar a forma da distribuição dos dados, como simétrica, assimétrica (positiva ou negativa) ou bimodal.
    
- **Centralização e dispersão**: A localização central e a dispersão dos dados podem ser inferidas a partir do histograma. Por exemplo, a média ou mediana pode estar aproximadamente no centro do histograma, e a largura dos compartimentos pode indicar a dispersão dos dados.
    
- **Outliers**: Valores atípicos (outliers) podem ser identificados como observações que caem em compartimentos que estão significativamente afastados dos demais.

##### Plotando Histogramas a partir do Seaborn as sns

Inicialmente, suprimiremos a função de densidade `kde` traçada junto com o Histograma, colocando-o como `False`.

```
ax = sns.distplot(dados.Altura, kde = False)
```

Criada a variável, começaremos a configurar alguns parâmetros em `ax` na mesma célula. Aplicaremos `.figure` com `.set_size_inches()` para configurarmos o tamanho do gráfico com 12 polegadas de largura e 6 de altura que queremos visualizar no notebook.

Em seguida, _setaremos_ o título `'Distribuição de Frequências - Altura'` e o `fontsize` como `18` dentro de `set_title()`.

Em seguida, configuraremos o label do eixo `x` como `'Metros'` e o tamanho de fonte `14` dentro do método `.set_xlabel()`.

Por fim, chamaremos `ax` para mostrarmos o gráfico de fato.

```python
ax = sns.distplot(dados.Altura, kde = False)

ax.figure.set_size_inches(12, 6)
ax.set_title('Distribuição de Frequências - Altura', fontsize=18)
ax.set_xlabel('Metros', fontsize=14)
```


![[Pasted image 20240328161110.png]]

# <span style="color:#7030a0">Medidas de tendência central </span>

### Média

```scss
df['Fulano'].mean()
```

```scss
dados.Renda.mean()
```

### Mediana

Quando "n" for **ímpar**, a posição do elemento mediano será obtido com:

![[Pasted image 20240329131034.png]]

Quando "n" for **par**, será com:

![[Pasted image 20240329131054.png]]


```
notas_fulano = df.Fulano
notas_fulano = notas_fulano.sort_values()
notas_fulano = notas_fulano.reset_index()
n = notas_fulano.shape[0]
elemento_md = (n + 1) / 2
notas_fulano.loc[elemento_md - 1]
```

##### * Mediana com pandas:

```scss
notas_fulano.median()
```

### Moda

```scss
df.mode()
```

# <span style="color:#7030a0">Relação entre medidas de tendência central</span>


![[Pasted image 20240329134549.png]]

1. A variável com **Simetria** é um padrão mais difícil de se encontrar, mas é o mais desejado, onde são iguais ou muito próximas e possuem uma distribuição simétrica.

2. A **Assimetria à Direita** acontece quando há uma grande quantidade de valores que se afunilam de alguma forma, como no caso da pesquisa PNAD sobre a renda mensal, onde a maioria das pessoas é mais pobre justificando o pico em "moda", enquanto a minoria possui grandes rendimentos que aumentam o valor da média.

3. Basicamente a mesma coisa acontece na **Assimetria à Esquerda**, mas a "força" que "puxa" os dados está na direção contrária.

# <span style="color:#7030a0">Medidas separatrizes</span>

### Quartis:

Os quartis dividem os dados em quatro partes iguais, onde:

- O primeiro quartil (Q1) representa o valor abaixo do qual 25% dos dados estão.
- O segundo quartil (Q2), também conhecido como mediana, divide os dados em duas partes iguais.
- O terceiro quartil (Q3) representa o valor abaixo do qual 75% dos dados estão.

##### Você pode calcular os quartis usando a função `numpy.percentile()`:

``` python
import numpy as np

# Exemplo de dados
dados = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])

# Cálculo dos quartis
q1 = np.percentile(dados, 25)
q2 = np.percentile(dados, 50)  # mediana
q3 = np.percentile(dados, 75)

print("Q1:", q1)
print("Mediana (Q2):", q2)
print("Q3:", q3)
```

##### Você pode calcular os quartis usando também a função `numpy ou pandas.quantile()`:

```python
dados.Renda.quantile([0.25, 0.5, 0.75])
```

### Percentis:

Os percentis dividem os dados em 100 partes iguais, onde o percentil k indica o valor abaixo do qual k% dos dados estão.

Você pode calcular os percentis também usando `numpy.percentile()`:

``` python
# Cálculo dos percentis
p25 = np.percentile(dados, 25)
p50 = np.percentile(dados, 50)  # mediana
p75 = np.percentile(dados, 75)

print("Percentil 25:", p25)
print("Mediana (Percentil 50):", p50)
print("Percentil 75:", p75)
```

##### Você pode calcular os quartis usando também a função `numpy ou pandas.quantile()`:

```python
dados.Renda.quantile([i / 100 for i in range(1, 100)])
```

### Decis:

Os decis dividem os dados em dez partes iguais, onde o décimo decis (D1) representa o valor abaixo do qual 10% dos dados estão, e assim por diante.

```python
# Cálculo dos decis
d1 = np.percentile(dados, 10)
d2 = np.percentile(dados, 20)
# E assim por diante, até d9

print("Décimo decis (D1):", d1)
print("Vigésimo decis (D2):", d2)
# E assim por diante, até d9
```

##### Você pode calcular os quartis usando também a função `numpy ou pandas.quantile()`:

```python
dados.Renda.quantile([i / 10 for i in range(1, 10)])
```


## <span style="color:#ffc000">Boxplot</span>

Um box plot, também conhecido como diagrama de caixa ou gráfico de caixa e bigodes, é um tipo de gráfico utilizado na estatística para representar a distribuição dos dados e identificar a presença de valores atípicos (outliers). Ele fornece uma visualização compacta das medidas de tendência central, dispersão e forma da distribuição dos dados.

![[Pasted image 20240329222455.png]]

### Componentes do box plot:

1. **Caixa (box)**: A caixa do box plot representa o intervalo interquartil (IQR), que é a distância entre o primeiro quartil (Q1) e o terceiro quartil (Q3). A linha no interior da caixa representa a mediana (Q2).
    
2. **Bigodes (whiskers)**: Os bigodes se estendem a partir da caixa até os valores extremos dos dados que não são considerados outliers. A maneira como os bigodes são desenhados pode variar dependendo da implementação, mas geralmente seguem regras específicas relacionadas à dispersão dos dados.
    
3. **Outliers**: Pontos individuais fora dos bigodes são considerados outliers. Eles são valores que estão além de um certo limite definido em relação à dispersão dos dados.
    
4. **Linha central (opcional)**: Algumas versões de box plots podem incluir uma linha vertical ou horizontal representando a média dos dados.

### Visualização do box plot

**Simétrico:**
```python
ax = sns.boxplot( x = 'Altura', y = 'Sexo', data = dados, orient = 'h')
ax.figure.set_size_inches(12, 4)
ax.set_title('Altura', fontsize=18)
ax.set_xlabel('Metros', fontsize=14)
```

![[Pasted image 20240329222724.png]]

**Desigual:**

```python
ax = sns.boxplot( x = 'Renda', data = dados, orient = 'h')
ax.figure.set_size_inches(12, 4)
ax.set_title('Renda', fontsize=18)
ax.set_xlabel('R$', fontsize=14)
```

![[Pasted image 20240329222757.png]]


# <span style="color:#7030a0">Medidas de dispersão</span>

### Desvio médio absoluto:

O desvio médio absoluto (DMA), também conhecido como média de desvios absolutos, é uma medida de dispersão que quantifica a variabilidade dos dados em torno da média. Ele é calculado como a média das diferenças absolutas entre cada valor dos dados e a média dos dados.

```python
(df - df.mean()).abs().mean()
```

### Variância:

##### Diferenças entre variância populacional e variância amostral

1. **Fórmula de cálculo**: A principal diferença está na fórmula de cálculo. A variância populacional usa a média e o tamanho da população, enquanto a variância amostral usa a média e o tamanho da amostra, com uma correção de Bessel.
    
2. **Finalidade**: A variância populacional é usada quando se tem acesso a todos os dados de uma população inteira, enquanto a variância amostral é usada quando se tem apenas uma amostra dos dados e deseja-se estimar a variância da população com base nessa amostra.
    
3. **Estimação vs. Parâmetro**: A variância populacional é um parâmetro que descreve a variabilidade da população, enquanto a variância amostral é uma estimativa do parâmetro populacional com base em uma amostra.

```python
import pandas as pd

# Exemplo de dados
dados = pd.Series([1, 2, 3, 4, 5])

# Calculando a variância amostral
variancia_amostral = dados.var()

# Calculando a variância populacional
variancia_populacional = dados.var(ddof=0)

print("Variância amostral:", variancia_amostral)
print("Variância populacional:", variancia_populacional)
```

Isso calculará a variância amostral e populacional para a série de dados fornecida. O valor padrão de `ddof` é `1`, o que faz com que o método `.var()` calcule a variância amostral. Definindo `ddof=0`, você pode calcular a variância populacional.

### Desvio Padrão:

