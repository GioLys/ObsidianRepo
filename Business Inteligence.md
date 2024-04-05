
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