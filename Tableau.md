
Tableau é uma ferramenta líder e tem a melhor experiência de usuários. Com essa ferramenta, você pode capturar os dados brutos e transformá-los em análises descomplicadas, facilitando seu entendimento.

- **Eficácia**: a performance e a linguagem de consulta traduzem as ações em uma consulta de banco de dados. Também possui conectores para a maioria de fonte de dados, como SalesForce, Google BigQuery, Oracle, MS SQL Server, Excel, etc.
- **Simplicidade**: é simples para o(a) usuário(a) e permite “arrastar e soltar” os dados a serem analisados, o que pode reduzir o tempo de aprendizado da ferramenta.
- **Autonomia**: é uma ferramenta “self-service”, ou seja, as pessoas que utilizam o Tableau podem criar suas análises sem depender do departamento de TI.

## <span style="color:#ffc000">Produtos</span>

O Tableau tem duas categorias de produtos:

- **Desenvolvimento**
- **Compartilhamento**

Os produtos de desenvolvimento envolvem a criação de dashboards, painéis, geração de relatórios e visualização de dados. Já os produtos de compartilhamento permitem compartilhar os relatórios e dashboards criados com os produtos de desenvolvimento.

> Basicamente, a principal tarefa do Tableau é conectar e extrair os dados nos seus mais variados formatos. A partir disso, ele começa a fazer as análises, criar métricas, desenvolver dashboards e publicá-los.

## <span style="color:#ffc000">Conceitos iniciais</span>

1. **Dashboard (Painel)**:
    
    - Os dashboards são painéis interativos que combinam várias visualizações para contar uma história ou fornecer uma visão geral dos dados.
    - Eles permitem aos usuários consolidar informações importantes em um único local e oferecem a capacidade de interagir com os dados por meio de filtros e seleções.
    - Os dashboards são altamente personalizáveis, permitindo que os usuários ajustem o layout, as cores e outros elementos visuais para atender às suas necessidades e preferências.

2. **Planilhas (Worksheets)**:
    
    - As planilhas são onde as visualizações individuais são criadas e projetadas.
    - Os usuários podem arrastar e soltar campos de dados para criar gráficos, tabelas e mapas que compõem as visualizações dentro de um dashboard.
    - As planilhas oferecem uma variedade de opções de formatação e personalização para ajustar a aparência e o comportamento das visualizações.

3. **Histórias**:
    
    - As histórias são uma maneira de sequenciar visualizações e narrativas para criar uma experiência guiada de exploração de dados.
    - Elas permitem aos usuários criar uma linha narrativa que destaca tendências, insights ou conclusões específicas a partir dos dados.
    - As histórias podem incluir várias planilhas e dashboards, além de texto descritivo e comentários para fornecer contexto e explicação adicional.

## <span style="color:#ffc000">Dimensões e Medidas</span>

1. **Dimensões**:
    
    - As dimensões são atributos dos seus dados que geralmente são descritivos e qualitativos.
    - Elas são usadas para categorizar, segmentar e organizar os dados em grupos.
    - Exemplos comuns de dimensões incluem nomes de clientes, datas, categorias de produtos, cidades, países, etc.
    - As dimensões geralmente são usadas para definir os níveis de detalhe e agrupamento nas visualizações.
    - Em uma visualização de gráfico de barras, por exemplo, as dimensões normalmente representariam as categorias no eixo x.

2. **Medidas**:
    
    - As medidas são valores numéricos que você deseja analisar, resumir ou comparar.
    - Elas representam aspectos quantitativos dos seus dados, como valores monetários, quantidades, percentagens, etc.
    - Exemplos comuns de medidas incluem vendas totais, lucro, quantidade de produtos vendidos, custo médio, etc.
    - As medidas são usadas para calcular estatísticas, realizar operações matemáticas e criar resumos numéricos dos dados.
    - Em uma visualização de gráfico de barras, as medidas geralmente representariam as alturas das barras no eixo y.

## <span style="color:#ffc000">Tipos de Cálculos</span>

1. **Cálculo de Linha**:
    
    - O cálculo de linha no Tableau é uma técnica que permite calcular valores ao longo de linhas específicas nos seus dados.
    - É útil quando você precisa realizar cálculos que consideram valores em uma linha específica, como diferenças entre valores em colunas adjacentes, por exemplo.
    - Um exemplo comum é calcular a diferença entre valores em colunas consecutivas para mostrar o crescimento ou decrescimento ao longo do tempo.

1. **Agregação**:
    
    - No Tableau, a agregação refere-se à forma como os valores são combinados ou resumidos em uma visualização.
    - Quando você arrasta uma medida para uma visualização, o Tableau geralmente a agregará automaticamente, como somando valores para calcular a soma total de vendas ou calculando a média de uma medida.
    - No entanto, você pode alterar a forma como os dados são agregados usando funções de agregação específicas, como SOMA, MÉDIA, MÁXIMO, MÍNIMO, entre outras.
    - Isso é útil para ajustar a visualização para mostrar os dados da maneira mais relevante para a análise.

## <span style="color:#ffc000">Variáveis continuas e discretas</span>

1. <span style="color:#92d050">Variáveis Contínuas</span>:
    
    - No Tableau, ==variáveis contínuas são sempre representadas por campos numéricos== que podem assumir uma infinidade de valores dentro de um intervalo.
    - Exemplos de variáveis contínuas no Tableau incluem medidas como vendas, temperatura, lucro, tempo decorrido, etc.
    - Ao trabalhar com variáveis contínuas no Tableau, você pode utilizar várias técnicas de análise, como criar cálculos, aplicar funções de agregação e criar visualizações contínuas, como gráficos de linhas ou áreas.
    - Nas quebras, contínuo sempre estará a direita de uma dimensão
    - Contínuo cria eixos

2. <span style="color:#00b0f0">Variáveis Discretas</span>:
    
    - No Tableau, variáveis discretas são geralmente representadas por campos que contêm valores específicos e distintos que não podem ser subdivididos.
    - Exemplos de variáveis discretas no Tableau incluem dimensões como categorias de produtos, nomes de clientes, datas, etc.
    - Ao trabalhar com variáveis discretas no Tableau, você geralmente usa esses campos para segmentar e organizar seus dados em grupos, e pode criar visualizações discretas, como gráficos de barras, gráficos de pizza ou tabelas de contingência.