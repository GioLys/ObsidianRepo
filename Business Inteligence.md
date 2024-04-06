
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
• Custos elevados (hardware, infraestrutura, licença de software, treinamento e consultoria).
• Alteração nos processos funcionais para adequação às boas práticas.