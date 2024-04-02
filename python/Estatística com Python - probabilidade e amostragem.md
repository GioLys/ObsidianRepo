
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