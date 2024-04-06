
> Termo guarda-chuva para descrever um conjunto de conceitos e métodos para melhorar a tomada das decisões de negócio, usando sistemas de suporte baseados em fatos.

BI não surgiu para substituir os demais tipos dos sistemas de suporte a decisões semiestruturadas e não estruturadas (SAD, SAE e DSS), pois, como a própria definição de Business Intelligence determina, BI não se resume a um sistema.

## <span style="color:#ffc000">BI vs. BA</span>

Tal como ocorreu no surgimento das soluções BI, a implementação de  Business Analytics não veio para substituir Business Intelligence, e sim para atender necessidades ainda ligadas a tomadas das decisões. <span style="color:#92d050">O BI tradicional age gerando informações sobre dados passados</span>, dos segundos, minutos, anos ou décadas atrás, para que, por meio da base histórica, explique o que aconteceu e por que aconteceu.

Por sua vez, <span style="color:#92d050">Business Analytics está focado em ajudar aos tomadores de decisão a simular e entender possibilidades do que acontecerá.</span>

## <span style="color:#ffc000">Composição de um BI</span>

![[Pasted image 20240405151412.png]]

## <span style="color:#ffc000">Dados que compõem um BI</span>

**Fontes OLTP**
  
OLTP processa dados em sistemas informáticos, focado em operações CRUD. Não é voltado para BI, mas é uma fonte importante de dados para ele. BI inclui análise de mercado, perfis de clientes, resultados de campanhas, rentabilidade e risco. Fontes de dados incluem ERP, CRM, CMS, SCM, planilhas, arquivos e sistemas departamentais.

**Fontes Externas**

Dados externos são dados que não podem ser encontrados nos sistemas OLTP, mas são necessários e importantes para melhorar a qualidade das informações geradas pelo BI. Exemplos, pesquisas sobre o mercado, informações sobre ações na bolsa, informações vindas do cadastro positivo etc.

**Staging Area (SA)**

A Staging Area é uma área de trabalho que recebe os dados das Fontes Internas e Externas. Os Modelos de dados contidos em uma SA não precisam ser modelados seguindo uma técnica = específica. Os dados são armazenados muito próximo ao seu formato original, pois não serão utilizados para consulta e análises, mas sim como área de cópia, limpeza e transformações feitas pelo ETL.

**Operational Data Store (ODS)**
  
Os bancos de dados operacionais são normalizados e podem ser usados em soluções de BI para análises específicas. Uma Operacional Data Store (ODS) armazena dados atuais ou quase atuais para suportar decisões operacionais diárias, oferecendo uma visão detalhada dos dados de forma corporativa. É orientado ao assunto, integrado e volátil, permitindo atualizações. Os dados vêm de várias fontes, como sistemas ERP, CRM, CMS, etc.

**Data Warehouse (DW)**

Inmon, considerado o pai do Data Warehouse, define DW como um conjunto de dados de apoio às decisões gerenciais, integrado, não volátil, variável em relação ao tempo e baseado em assuntos.

**Data Marts (DM)**
  
Data Marts são subconjuntos dos dados corporativos, focados em assuntos específicos e de valor para um departamento, unidade corporativa ou conjunto de usuários. Geralmente são considerados como parte de um Data Warehouse e definidos pelo escopo funcional que atendem, não pelo tamanho. São uma evolução dos conceitos do Data Warehousing, permitindo a construção mais rápida e direcionada de soluções analíticas. Na metodologia de construção de Data Warehouses, abordagens como Top-Down (Inmon) e Bottom-Up (Kimball) diferem na abordagem de desenvolvimento. Kimball defende a construção incremental a partir de Data Marts, enquanto Inmon preconiza a construção do Data Warehouse como um todo primeiro. A abordagem de Kimball é mais aceita atualmente devido ao tempo de construção menor e retorno de investimento mais rápido.

## <span style="color:#ffc000">Processamento do BI</span>

![[Pasted image 20240405165634.png]]

## <span style="color:#ffc000">Modelagem de Dados</span>

### ETL

Extract Transform Load (Extração Transformação Carga) é o processo de extração, transformação e carga dos dados, oriundos das fontes diversas, em modelos dimensionais no DW, para que os usuários finais possam realizar consultas e tomar decisões.

• **Extração** – Obtenção dos dados brutos, das fontes internas e externas para a SA e para o ODS (quando existente). No exemplo que utilizamos anteriormente, este passo será o responsável por buscar o valor de cada item da NF.

• **Transformação** – Limpeza dos dados extraídos, aplicação das regras de negócio e validação dos dados na SA como preparação para carga.

• **Carga** – Inserção dos dados transformados na SA em bases de dados do DW.

## <span style="color:#ffc000">Análise de Dados</span>

### SQL

A linguagem de consulta SQL (Structured Query Language) é muito utilizada para extrair de um banco de dados todas as tuplas que atendem a um conjunto específico de critérios utilizados na consulta.

### OLAP (Processamento Analítico On-Line)

É a capacidade de manipular e analisar um grande volume dos dados através de múltiplas perspectivas e assim monitorar os fatos e indicadores mais relevantes da organização, por meio dos painéis de controle e relatórios executivos desenvolvidos para facilitar a visualização, o entendimento dos fatos e a tomada de decisões. Utiliza técnicas específicas como ranking, comparações, pivot tables, drill down e roll up, slice e dice, entre outras.

<span style="color:#92d050">Os cubos em OLAP podem ser implementados de quatro formas diferentes:</span>

• **ROLAP (Relational On-Line Analytical Processing):** Os dados são armazenados em banco de dados relacionais e cada ação de Slice/Dice é equivalente a adicionar uma condição na cláusula WHERE em uma query SQL. Implementação contida nas figuras deste documento.

• **MOLAP (Multidimensional On-Line Analytical Processing):** Os dados são armazenados em cubos dimensionais, em formatos proprietários das ferramentas, e não em banco de dados relacionais. O usuário monta os cubos e manipula os dados diretamente no servidor OLAP.

• **HOLAP (Hybrid On-Line Analytical Processing):** Combina as vantagens de MOLAP e ROLAP. Para informações do tipo síntese, HOLAP utiliza cubos dimensionais para um retorno do resultado mais rápido. Quando a análise requer mais informação, o HOLAP pode complementar o cubo multidimensional buscando dados no banco de dados relacional.

• **DOLAP (Desktop On-Line Analytical Processing):** Ferramentas que disparam
uma consulta de uma estação cliente para o servidor, que por sua vez retorna
enviando um cubo de volta, para que possa ser analisado pelo usuário.

### Data Mining

Esta é uma técnica de análise para fazer descobertas automáticas sobre padrões ocultos e relacionamentos desconhecidos de similaridade ou discordância entre dados, dentro de um grande volume de dados.

O Data Mining utiliza algoritmos complexos e técnicas de inteligência artificial para fazer tais descobertas e transformá-las em informações úteis para a tomada de decisão e/ou avaliação de resultados. Atualmente, um emprego muito comum desta técnica é seu uso na prevenção de fraude, segmentação de clientes e previsão de comportamento.

## <span style="color:#ffc000">ERP - Enterprise Resource Planning</span>

A sigla ERP significa “Planejamento de Recursos Empresariais”. Um ERP (Enterprise Resource Planning) é um sistema modular, integrado através de um banco de dados comum. Os módulos atendem praticamente todas as áreas e departamentos de uma empresa, de forma que um único evento que tenha dado origem à execução de um processo de um departamento, seja trabalhado pelas demais áreas que tenham alguma responsabilidade paralela ou sequencial sobre ele.

> O ERP pós-moderno é uma estratégia de tecnologia que automatiza e liga capacidades empresariais administrativas e operacionais (como finanças, RH, compras, fabricação e distribuição) com níveis adequados de integração que equilibram os benefícios da integração entre fornecedores e a flexibilidade e agilidade do negócio. Esta definição destaca que existem duas categorias de estratégia ERP: administrativa e operacional.

![[Pasted image 20240405233917.png]]

### Características e Módulos Principais de um ERP

**Estratégia administrativa:**

Se concentra nos aspectos administrativos do ERP, principalmente financeiros, gerenciamento de capital humano e compras indiretas. Algumas indústrias não necessitam de recursos operacionais, tais como fabricação ou distribuição, de modo que elas devem concentrar a estratégia de emprego de um ERP nas funções administrativas são geralmente caracterizadas como indústrias centradas em serviços.

**Estratégia operacional:**

As organizações que realizam fabricação, distribuição, varejo etc. (referidas como indústrias centradas em produtos) muito provavelmente estenderão sua estratégia de adoção de um ERP para além das funções administrativas, cobrindo áreas operacionais, como gerenciamento de pedidos, fabricação e cadeia de suprimentos, para maximizar a eficiência operacional. Além disso, organizações com recursos intensivos podem incluir operações e manutenção de ativos em sua
estratégia ERP. Essas organizações podem obter benefícios da integração entre as capacidades administrativas e operacionais, por exemplo, onde as transações operacionais que têm impacto financeiro são refletidas e administradas diretamente nos módulos financeiros.

**Podemos citar como características de um ERP:**

• Um sistema integrado e parametrizável que opera em tempo real ou próximo.
• Possui banco de dados comum que oferece suporte e integração a todos os módulos.
• Oferta uma aparência (UX) consistente em todos os módulos.
• Suporta os processos e implementa controles operacionais e administrativos.
• Emprega a otimização de processos.
• Gera relatórios operacionais e administrativos.
• Possibilita a gestão integrada do negócio.
• Provê a capacidade de planejar a operação.

![[Pasted image 20240406002323.png]]

### Vantagens com a implementação do ERP

O ERP pode melhorar a qualidade e eficiência do negócio ao manter os processos de negócios de uma empresa funcionando de maneira segura, integrada e monitorada. O ERP oferece suporte ao gerenciamento ágil, fornecendo informações praticamente em tempo real, para a tomada de decisões.

Como um dos principais pilares de um ERP é uma <span style="color:#92d050">base de dados comum</span>, essas soluções oferecem maiores oportunidades de colaboração. Dados, documentos, formulários, áudio e vídeo podem ser armazenados e compartilhados e em alguns casos, através de mecanismos específicos de colaboração.

**Podemos elencar como algumas vantagens do uso de um ERP:**

- Otimização dos processos operacionais e administrativos.
- Redistribuição de funções.
- Redução do estoque e de custos.
- Integração e maior colaboração entre as áreas.
- Redução de retrabalhos.
- Monitoramento das operações do início ao fim.
- Geração de informações para tomada de decisões.
- Aumento da agilidade na tomada de decisões.
- Segurança dos dados.
- Solução flexível (novos módulos podem ser adquiridos).
- Aquisição de conhecimento sobre as “Boas Práticas” do segmento.

### Desvantagens com a implementação do ERP

A reengenharia dos processos de negócios para se adequar ao ERP demandará esforços de
levantamento, documentação e treinamentos, geralmente criando restrições por parte dos colaboradores e desviando o foco deles das atividades que desempenham.

Já a customização, como comentamos, pode ser muito problemática e custosa. Um ERP personalizado custa mais caro e, certamente, custará muito mais caro do que soluções sob medida, menos integradas e menos abrangentes.

**Podemos elencar como algumas desvantagens do uso de um ERP:**

- Custos elevados (hardware, infraestrutura, licença de software, treinamento e consultoria).
- Alteração nos processos funcionais para adequação às boas práticas.
- Possível perda de capacidade criativa e vantagens competitivas.
- Impactos sobre os colaboradores.
- Impacto de customizações (quando necessárias).
- Projeto de implementação complexo.
- Problemas no cumprimento de prazos.

### SWOT como Ferramenta de Decisão

<span style="color:#92d050">Strengths (Forças)</span>
<span style="color:#ffc000">Weaknesses (Fraquezas)</span>
<span style="color:#ff0000">Opportunities (Oportunidades)</span>
<span style="color:#ffff00">Threats (Ameaças)</span> 

É um sistema simples e prático que auxilia uma empresa a adotar uma posição estratégica em um determinado ambiente.

**Exemplo: Desenvolver um ERP caseiro**

| <span style="color:#ffff00">Superação tecnológica<br>Riscos na sustentação de novos negócios<br>ou novos requisitos<br>Pouca visão sobre as práticas do mercado<br>Dependência de treinamentos específicos<br>para colaboradores</span><br><br><br><br><br> | <span style="color:#ff0000">Adequação plena às necessidades da<br>empresa<br>Liberdade de criação e de diferenciação<br>(possível vantagem competitiva)</span> |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span style="color:#92d050">Custos mais baixos<br>Software sob medida, customização plena</span><br>                                                                                                                                                        | <span style="color:#ffc000">Dependência de equipe de<br>desenvolvimento interna ou terceirizada<br>Risco de processos desalinhados com o<br>mercado ou com imposições legais</span>               |

## <span style="color:#ffc000">CRM - Customer Relationship Management</span>

É um sistema integrado de gestão com foco no cliente, constituído por um conjunto de
procedimentos, processos e estratégias, organizados e integrados em um modelo de gestão.

Um projeto de software CRM, considerado como bem-sucedido, gera uma visão clara de cada cliente, que serve tanto para melhorar o resultado das vendas e do atendimento, quanto para fortalecer e estabelecer relacionamentos mais longos com ele.

**Os maiores esforços devem se centrar em três tópicos:**

- Automatizar a gestão de marketing.
- Automatizar a gestão comercial, de canais e de força de vendas.
- Automatizar a gestão de serviços aos clientes.

**Nesse contexto, as seguintes características de um software CRM são destacadas, por uma das principais empresas fornecedoras de CRM no mundo:**

- Capacidade de rastrear ativamente e gerenciar as informações dos clientes.
- Capacidade de conectar toda a sua equipe em qualquer dispositivo.
- Consegue capturar informações de forma inteligente dos e-mails dos clientes.
- É capaz de simplificar tarefas repetitivas para que a empresa possa fazer um acompanhamento de leads mais efetivo.
- Deve fornecer recomendações e insights instantâneos.
- Deve ser capaz de expandir e se personalizar, conforme o crescimento da empresa.

**Embora sejam processos eminentemente integrados, pode-se dividir logicamente o CRM em três aspectos fundamentais:**

- CRM Operacional: visa à criação de canais de relacionamento com o cliente.
- CRM Analítico: visa obter uma visão consistente do cliente, usando os dados recolhidos pelo CRM operacional para obter conhecimento que permita otimizar e gerar negócios.
- CRM Colaborativo: foca na obtenção do valor do cliente por meio de colaboração inteligente, baseada em conhecimento.

> Atualmente, considera-se um novo tipo de CRM ainda não muito bem documentado ou estabelecido, intitulado CRM Social que retrata o relacionamento com o cliente através das mídias sociais, incluindo dados disponibilizados pelos próprios clientes em seus perfis.


## <span style="color:#ffc000">Modelagem de Dados - Modelagem Dimensional - Data Warehouse</span>

### Sobre o Data Warehouse:

Inmon, considerado o pai do Data Warehouse, define DW como um conjunto de dados de apoio às decisões gerenciais, integrado, não volátil, variável em relação ao tempo e baseado em assuntos.

- Integrado: os dados são coletados a partir de uma variedade de fontes e fundidos em um todo coerente.
- Não volátil: nenhum dado pode ser alterado ou excluído no DW. Qualquer consulta a um dado relativo a um período de tempo sempre produzirá o
- mesmo resultado; nenhum dado será excluído enquanto não se tornar obsoleto para o negócio. Em soluções de BI específicas para alguns tipos de negócio, isso pode ocorrer.
- Variável em relação ao tempo: todos os dados no data warehouse são identificados com um período de tempo particular. O DW é focado na manutenção do histórico.
- Orientado ao assunto: possui dados que fornecem informações sobre um assunto específico em vez de fazê-lo sobre as operações em curso de uma empresa.

A <span style="color:#92d050">Modelagem de Dados</span> é, por necessidade, parte fundamental da estrutura e do processamento de uma solução DW, pois o modelo deve ser capaz de comportar o armazenamento de todos os dados relevantes, para apoio à tomada de decisões, bem como, prover alto desempenho de acesso, requisito fundamental para processamentos analíticos complexos.

### Sobre o Modelo Dimensional:

A abordagem dimensional tem como objetivos criar bancos de dados para suporte a decisão que apresentem os dados de uma maneira padronizada, intuitiva e que permitam acesso de alto desempenho.

A modelagem dimensional é amplamente aceita como abordagem preferida em soluções DW, porque atende dois requisitos importantes: a entrega de dados compreensíveis para os usuários; e a provisão de desempenho em consultas.

#### Conceitos Básicos:

1) **Fato:**

Fato é uma <span style="color:#92d050">coleção de dados relacionados que representam um evento do negócio</span>, usado em um DW ou DM para análise e tomada de decisões empresariais. Em um Data Warehouse ou Data Mart, ==cada fato é registrado em uma linha de uma tabela também chamada de Fato==, que trata um processo específico do negócio.

Como exemplo, em um modelo que abrange o processo de Vendas, a tabela Fato pode receber o nome de FATO_VENDAS e deve possuir em cada linha, um item de uma venda, armazenado principalmente em atributos numéricos conhecidos como medidas. Neste exemplo, o item de venda é chamado de grão.

Segundo Kimball (2011), definir o grão é o passo fundamental de um design dimensional. <span style="color:#92d050">O grão deve estabelecer exatamente o nível de detalhe que será armazenado em uma linha da Tabela Fato.</span> Portanto, o grão deve ser definido antes de escolhermos as dimensões e deve ser o mais atômico possível (Falaremos sobre grão mais à frente).

2) **Medidas:**

<span style="color:#92d050">Uma medida é um atributo numérico de um fato.</span> Por exemplo, em um processo de Vendas, cada item vendido deve ser armazenado em uma linha na tabela Fato e as medidas comuns para esse evento de negócio são: a quantidade vendida, o preço unitário, o custo unitário, o desconto concedido, o valor total, o custo total, o desconto total, o lucro bruto, o valor de imposto, entre outros.

Na maioria dos casos, as medidas, também conhecidas como métricas são aditivas, ou seja, nelas podem ser aplicadas as operações de soma, subtração e média, cruzando-se a seleção por qualquer dimensão.

3) **Dimensões:**

São tabelas que fornecem a base para filtramos e analisarmos as medidas da tabela Fato, permitindo a visualização por aspectos diferentes.

As dimensões normalmente respondem às questões do tipo “Quem?”, “O quê?”, “Quando?”, “Onde?” e “Por quê?”. Elas são os parâmetros ou filtros sobre os quais queremos realizar Online Analytical Processing (OLAP). Por exemplo, <span style="color:#92d050">em um modelo dimensional para a análise de vendas, dimensões comuns são: data, produto, cliente, loja, promoção, vendedor.</span> 

Tabelas dimensionais não são normalizadas e são constituídas por atributos que podem ser arranjados em hierarquias. Uma hierarquia, quando aplicada em uma dimensão, se prevalece da não normalização para facilitar a vida do usuário, que, por natureza, está acostumado com o conceito de agrupamento hierárquico.

<span style="color:#ffff00">Dois exemplos muito comuns são hierarquias de datas e endereços:</span>

- Datas: ano, semestre, trimestre, bimestre, mês, semana e dia da semana.
- Endereço: região, estado, cidade, zona, bairro e endereço.

<span style="color:#00b0f0">Exemplo:</span> Consulta da dimensão Data

![[Pasted image 20240406174549.png]]

<span style="color:#00b0f0">Exemplo de um modelo dimensional:</span>

![[Pasted image 20240406174713.png]]

#### Keys:

**Surrogate Keys:**

Sk ou Surrogate key é uma chave substituta para a chave primária natural dos dados de origem. Uma sk deve ser um identificador único, numérico do tipo inteiro e sequencial, gerado para cada linha de uma entidade dimensional. Em geral, a primeira linha deve ser preenchida com o valor 1, a segunda com o valor 2 e assim por diante.

**Natural Keys:**

Note que as chaves naturais não foram descartadas, elas são trazidas durante a carga, em conjunto com os demais campos das dimensões e recebem o sufixo nk. As chaves naturais são importantes, pois possibilitam a rastreabilidade entre origem e destino dos dados, bem como, podem ser usadas como filtros, quando reconhecidas pelo usuário que se acostumou a pesquisá-las no sistema OLTP de origem.

**Smart Keys:**

Voltando a nossa atenção para a consulta feita na dimensão Data, podemos perceber outra característica diferente, note que o valor da chave primária é formado pela própria data invertida. Esse é um exemplo de chave inteligente, pois ela garante unicidade e ainda aporta um significado real, a própria data a que a linha da tabela corresponde.

### Dimensões degeneradas:

Com os nossos olhos novamente sobre o modelo, podemos identificar um atributo que faz parte da chave composta da tabela Fato, não é uma FK dimensional e possui um sufixo diferente, dd.

O sufixo corresponde ao conceito de Dimensão Degenerada, que, de forma simplificada, é uma dimensão que não possui atributos descritivos relevantes para análise, apenas uma chave natural, absorvida pela tabela Fato.

#### Star Schema, Cubes, OLAP, ROLAP e MOLAP

OLAP (Processamento Analítico On-Line) é a capacidade de manipular e analisar um grande volume de dados através de múltiplas perspectivas e, assim, monitorar os fatos e indicadores mais relevantes da organização para a tomada de decisões.

