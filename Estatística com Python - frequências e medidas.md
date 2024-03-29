
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

### Mediana