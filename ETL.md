
> Extrair, transformar e carregar (ETL) é o processo que as organizações orientadas a dados usam para coletar dados de várias fontes e reuni-los para dar suporte à descoberta, à geração de relatórios, à análise e à tomada de decisões.

As origens de dados podem ser muito diversas em tipo, formato, volume e confiabilidade, de modo que os dados precisam ser processados para serem úteis quando reunidos. Os armazenamentos de dados de destino podem ser bancos de dados, data warehouses ou data lakes, dependendo das metas e da implementação técnica.

## <span style="color:#ffc000">As três etapas distintas do ETL</span>

**Extrair**  
Durante a extração, o ETL identifica os dados e os copia de suas origens, de forma que possa transportar os dados para o armazenamento de dados de destino. Os dados podem vir de fontes estruturadas e não estruturadas, incluindo documentos, emails, aplicações de negócios, bancos de dados, equipamentos, sensores, terceiros e muito mais.

**Transformar**  
Como os dados extraídos são brutos em sua forma original, eles precisam ser mapeados e transformados para prepará-los para o armazenamento de dados eventual. No processo de transformação, o ETL valida, autentica, desduplica e/ou agrega os dados de formas que tornam os dados resultantes confiáveis e consultáveis.

**Carregar**  
O ETL move os dados transformados para o armazenamento de dados de destino. Esta etapa pode implicar o carregamento inicial de todos os dados de origem ou pode ser o carregamento de alterações incrementais nos dados de origem. Você pode carregar os dados em tempo real ou em lotes programados.

## <span style="color:#ffc000">ELTransform ou ETtransformL: Qual é a diferença?</span>

A etapa de transformação é de longe a mais complexa do processo ETL. Por conseguinte, a ETL e a ELT diferem em dois pontos principais:

- Quando a transformação ocorre
- O local da transformação

Em um data warehouse tradicional, os dados são extraídos primeiro de "sistemas de origem" (sistemas de ERP, sistemas de CRM etc.). As ferramentas OLAP e as consultas SQL dependem da padronização das dimensões dos conjuntos de dados para obter resultados agregados. Isso significa que os dados devem passar por uma série de transformações.

Tradicionalmente, essas transformações foram feitas antes que os dados fossem carregados no sistema de destino, normalmente um data warehouse relacional.

No entanto, à medida que as tecnologias subjacentes de armazenamento e processamento de dados que sustentam o armazenamento de dados evoluem, tornou-se possível efetuar transformações no sistema de destino. Os processos ETL e ELT envolvem áreas de preparação. No ETL, essas áreas são encontradas na ferramenta, sejam elas proprietárias ou personalizadas. Elas ficam entre o sistema de origem (por exemplo, um sistema CRM) e o sistema de destino (o data warehouse).

Por outro lado, com ELTs, a área de preparação está no data warehouse, e o mecanismo de banco de dados que alimenta o DBMS faz as transformações, em vez de uma ferramenta ETL. Portanto, uma das consequências imediatas dos ELTs é que você perde as funções de preparação e limpeza de dados que as ferramentas ETL fornecem para ajudar no processo de transformação de dados.