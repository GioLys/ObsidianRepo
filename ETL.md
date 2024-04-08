
> Extrair, transformar e carregar (ETL) é o processo que as organizações orientadas a dados usam para coletar dados de várias fontes e reuni-los para dar suporte à descoberta, à geração de relatórios, à análise e à tomada de decisões.

As origens de dados podem ser muito diversas em tipo, formato, volume e confiabilidade, de modo que os dados precisam ser processados para serem úteis quando reunidos. Os armazenamentos de dados de destino podem ser bancos de dados, data warehouses ou data lakes, dependendo das metas e da implementação técnica.

## <span style="color:#ffc000">As três etapas distintas do ETL</span>

**Extrair**  
Durante a extração, o ETL identifica os dados e os copia de suas origens, de forma que possa transportar os dados para o armazenamento de dados de destino. Os dados podem vir de fontes estruturadas e não estruturadas, incluindo documentos, emails, aplicações de negócios, bancos de dados, equipamentos, sensores, terceiros e muito mais.

**Transformar**  
Como os dados extraídos são brutos em sua forma original, eles precisam ser mapeados e transformados para prepará-los para o armazenamento de dados eventual. No processo de transformação, o ETL valida, autentica, desduplica e/ou agrega os dados de formas que tornam os dados resultantes confiáveis e consultáveis.

**Carregar**  
O ETL move os dados transformados para o armazenamento de dados de destino. Esta etapa pode implicar o carregamento inicial de todos os dados de origem ou pode ser o carregamento de alterações incrementais nos dados de origem. Você pode carregar os dados em tempo real ou em lotes programados.