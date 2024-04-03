
## <span style="color:#ffc000">Conceitos básicos em probabilidade</span> 

1. **Espaço Amostral (S)**: O conjunto de todos os resultados possíveis de um experimento aleatório. É denotado por S.
    
2. **Evento (E)**: Um subconjunto do espaço amostral. É um resultado ou uma coleção de resultados de um experimento aleatório. Por exemplo, se lançarmos um dado, o evento "obter um número par" consiste nos resultados {2, 4, 6}.
    
3. **Probabilidade de um Evento (P(E))**: A medida numérica que descreve a chance de que um evento específico ocorra. A probabilidade de um evento é sempre um número entre 0 e 1, onde 0 significa que o evento é impossível e 1 significa que o evento é certo.

### Distribuições de Probabilidade

**Distribuição de Probabilidade Binomial:*

Um **Evento Binomial** é caracterizado pela possibilidade de ocorrência de apenas **duas categorias**; ou é sim ou é não, verdadeiro e falso, sucesso ou fracasso e etc. A soma dessas duas categorias é o **Espaço Amostral**, ou seja, o total de eventos possíveis dentro de um experimento.

![[Pasted image 20240401162351.png]]

<span style="color:#00b0f0">Exemplos: </span>

- O lançamento de uma moeda pode ter a face "cara" ou a "coroa", e esse é o Espaço Amostral com duas possibilidades.
- Um lançamento de dado de seis faces, só poderemos ter seis resultados possíveis: 1, 2, 3, 4, 5, ou 6.

### Experimento Binomial

1. Realização de n ensaios idênticos.
2. Os ensaios são independentes.
3. Somente dois resultados são possíveis, exemplo: Verdadeiro ou falso; Cara ou coroa; Sucesso ou fracasso.
4. A probabilidade de sucesso é representada por p e a de fracasso por 1−p=q. Estas probabilidades não se modificam de ensaio para ensaio.

### Média da distribuição binomial

O valor esperado ou a média da distribuição binomial é igual ao número de experimentos realizados multiplicado pela chance de ocorrência do evento.

**μ=n×p**

### Desvio padrão da distribuição binomial

O desvio padrão é o produto entre o número de experimentos, a probabilidade de sucesso e a probabilidade de fracasso.

![[Pasted image 20240401163009.png]]

## <span style="color:#ffc000"></span> <span style="color:#ffc000">Cálculo de probabilidades usando Python</span>

```python
from scipy.special import comb
```

### Exemplo: Mega Sena

Em um volante de loteria da Mega Sena temos um total de **60 números** para escolher onde a aposta mínima é de **seis números**. Você que é curiosa(o) resolve calcular a probabilidade de se acertar na Mega Sena com apenas **um jogo**. Para isso precisamos saber quantas **combinações de seis números podem ser formadas com os 60 números disponíveis**.

![[Pasted image 20240401172134.png]]

![[Pasted image 20240401172144.png]]

```python
combinacoes = comb(60, 6)
```

Para calcularmos a <span style="color:#92d050">probabilidade</span> de ganharmos o prêmio com apenas um bilhete, criaremos a variável `probabilidade` sendo igual a `1` dividido pela operação anterior.

```python
probabilidade = 1 / combinacoes
```

Como será um valor muito pequeno, formataremos o retorno com `print()` recebendo `'%0.15f'` entre aspas simples para quinze casas decimais seguido de `%` e `probabilidade` para plotarmos em percentual.

```python
probabilidade = 1 / combinacoes
print('%0.15f' % probabilidade)
```

 A chance de ganharmos na Mega Sena é bem pequena, cerca de<span style="color:#ffff00"> 0,0000000199%</span>.
 
### Exemplo: Concurso para cientista de dados

Em um concurso para preencher uma vaga de cientista de dados temos um total de **10 questões** de múltipla escolha com **3 alternativas possíveis** em cada questão. **Cada questão tem o mesmo valor.** Suponha que um candidato resolva se aventurar sem ter estudado absolutamente nada. Ele resolve fazer a prova de olhos vendados e chutar todas as resposta. Assumindo que a prova **vale 10 pontos e a nota de corte seja 5**, obtenha a probabilidade deste candidato **acertar 5 questões** e também a probabilidade deste candidato **passar para a próxima etapa do processo seletivo**.

 **Qual o número de ensaios (n)?**

n = 10

**Os ensaios são independentes?**

 Sim. A opção escolhida em uma questão não influencia em nada a opção escolhida em outra questão.
 
**Somente dois resultados são possíveis em cada ensaio?**

Sim. O candidato tem duas possibilidades, ACERTA ou ERRAR uma questão.

**Qual a probabilidade de sucesso (p)?**

```makefile
numero_de_alternativas_por_questao = 3
p = 1 / numero_de_alternativas_por_questao
```

**Qual a probabilidade de fracasso (q)?**

```makefile
q = 1 - p
```

**Qual o total de eventos que se deseja obter sucesso (k)?**

k = 5

### <span style="color:#92d050">Solução 1</span> 

```python
probabilidade = (comb(n, k)) * (p ** k) * (q ** (n - k))
print('%0.8f' % probabilidade)
```

### <span style="color:#92d050">Solução 2 com a biblioteca scipy</span>

```python
from scipy.stats import binom
```

```python
probabilidade = binom.pmf(k, n, p)
print('%0.8f' % probabilidade)
```

### <span style="color:#92d050">-> Obter a probabilidade do candidato passar</span> 

![[Pasted image 20240402115419.png]]

**Opção 1:**

```python
binom.pmf(5, n, p) + binom.pmf(6, n, p) + binom.pmf(7, n, p) + binom.pmf(8, n, p) + binom.pmf(9, n, p) + binom.pmf(10, n, p)
```

**Opção 2:**

```python
binom.pmf([5, 6, 7, 8, 9, 10], n, p).sum()
```

**Opção 3:**

```python
binom.sf(4, n, p)
```


##  <span style="color:#ffc000">Distribuição de Poisson</span>

É empregada para descrever o número de ocorrências em um intervalo de tempo ou espaço específico. Os eventos são caracterizados pela possibilidade de contagem dos sucessos, mas a não possibilidade de contagem dos fracassos.

Como exemplos de processos onde podemos aplicar a distribuição de Poisson temos a determinação do número de clientes que entram em uma loja em determinada hora, o número de carros que chegam em um drive-thru de uma lanchonete na hora do almoço, a determinação do número de acidentes registrados em um trecho de estrada etc.

![[Pasted image 20240402150844.png]]

**Onde:**

**e = constante cujo valor aproximado é 2,718281828459045**

**μ = representa o número médio de ocorrências em um determinado intervalo de tempo ou espaço**

**k = número de sucessos no intervalo desejado**

### Experimento Poisson

1. A probabilidade de uma ocorrência é a mesma em todo o intervalo observado.
2. O número de ocorrências em determinado intervalo é independente do número de ocorrências em outros intervalos.
3. A probabilidade de uma ocorrência é a mesma em intervalos de igual comprimento.

![[Pasted image 20240402151139.png]]

![[Pasted image 20240402151156.png]]

### Exemplo: Delivery

Um restaurante recebe em média **20 pedidos por hora**. Qual a chance de que, em determinada hora escolhida ao acaso, o restaurante receba **15 pedidos**?

**Qual o número médio de ocorrências por hora (μ)?**

media = 20

**Qual o número de ocorrências que queremos obter no período (k)?**

k = 15

### <span style="color:#92d050">Solução 1</span> 

probabilidade = (np.e ** (-media)) * (media ** k) / (np.match.factorial(k))

### <span style="color:#92d050">Solução 2 com bibliotecas python</span>

```python
from scipy.stats import poisson

probabilidade = poisson.pmf(k, media)
print('%0.8f' % probabilidade)
```

##  <span style="color:#ffc000">Distribuição Normal</span>

A distribuição normal é uma das mais utilizadas em estatística. É uma distribuição contínua, onde a distribuição de frequências de uma variável quantitativa apresenta a forma de sino e é simétrica em relação a sua média.

![[Pasted image 20240402180450.png]]

### Características importantes

1. É simétrica em torno da média;
2. A área sob a curva corresponde à proporção 1 ou 100%;
3. As medidas de tendência central (média, mediana e moda) apresentam o mesmo valor;
4. Os extremos da curva tendem ao infinito em ambas as direções e, teoricamente, jamais tocam o eixo x;
5. O desvio padrão define o achatamento e largura da distribuição. Curvas mais largas e mais achatadas apresentam valores maiores de desvio padrão;
6. A distribuição é definida por sua média e desvio padrão;
7. A probabilidade sempre será igual à área sob a curva, delimitada pelos limites inferior e superior.

![[Pasted image 20240402180524.png]]

Onde:

x = variável normal

σ = desvio padrão

μ = média

<span style="color:#92d050">A probabilidade é obtida a partir da área sob a curva, delimitada pelos limites inferior e superior especificados. Um exemplo pode ser visto na figura abaixo.</span> 

![[Pasted image 20240402180559.png]]

Para obter a área acima basta calcular a integral da função para os intervalos determinados. Conforme equação abaixo:

![[Pasted image 20240402180644.png]]

### Tabelas Padronizadas

Maneira mais simplificada de calcular a área da curva

![[Pasted image 20240402181352.png]]

Onde:

x = variável normal com média μ e desvio padrão σ
σ = desvio padrão
μ = média

### Exemplo: Qual sua altura?

Em um estudo sobre as alturas dos moradores de uma cidade verificou-se que o conjunto de dados segue uma **distribuição aproximadamente normal**, com **média 1,70** e **desvio padrão de 0,1**. Com estas informações obtenha o seguinte conjunto de probabilidades:

> **A.** probabilidade de uma pessoa, selecionada ao acaso, ter menos de 1,80 metros.

> **B.** probabilidade de uma pessoa, selecionada ao acaso, ter entre 1,60 metros e 1,80 metros.

> **C.** probabilidade de uma pessoa, selecionada ao acaso, ter mais de 1,90 metros.

![[Pasted image 20240403151206.png]]

