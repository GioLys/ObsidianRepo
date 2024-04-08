 
> Um pipeline de dados é uma série de etapas de processamento para preparar dados corporativos para análise.

As organizações têm um grande volume de dados de várias fontes, como aplicativos, dispositivos de Internet das Coisas (IoT) e outros canais digitais. No entanto, os dados brutos são inúteis; eles devem ser movidos, classificados, filtrados, reformatados e analisados para business intelligence. 

Um pipeline de dados inclui várias tecnologias para verificar, resumir e encontrar padrões nos dados para informar as decisões de negócios. Pipelines de dados bem organizados oferecem suporte a vários projetos de big data, como visualizações de dados, análises exploratórias de dados e tarefas de machine learning.

## <span style="color:#ffc000">Quais são os benefícios de um pipeline de dados?</span>

Os pipelines de dados permitem integrar dados de diferentes fontes e transformá-los para análise. Eles removem silos de dados e tornam sua análise de dados mais confiável e precisa. 

Aqui estão alguns dos principais benefícios de um pipeline de dados:
### **Melhor qualidade dos dados**

Os pipelines de dados limpam e refinam os dados brutos, melhorando sua utilidade para os usuários finais. Eles padronizam formatos para campos como datas e números de telefone enquanto verificam erros de entrada. Eles também removem a redundância e garantem a qualidade consistente dos dados em toda a organização.

### **Processamento eficiente de dados**

Os engenheiros de dados precisam realizar muitas tarefas repetitivas enquanto transformam e carregam dados. Os pipelines de dados permitem que eles automatizem tarefas de transformação de dados e se concentrem em encontrar os melhores insights de negócios. Os pipelines de dados também ajudam os engenheiros de dados a processar mais rapidamente os dados brutos que perdem valor com o tempo.

### **Integração de dados abrangente**

Um pipeline de dados abstrai funções de transformação de dados para integrar conjuntos de dados de fontes diferentes. Ele pode cruzar valores dos mesmos dados de várias fontes e corrigir inconsistências. Por exemplo, imagine que o mesmo cliente faz uma compra em sua plataforma de comércio eletrônico e em seu serviço digital. No entanto, eles escrevem seu nome incorretamente no serviço digital. O pipeline pode corrigir essa inconsistência antes de enviar os dados para análise.

## <span style="color:#ffc000">Como funciona um pipeline de dados?</span>

Assim como uma tubulação de água move a água do reservatório para suas torneiras, um pipeline de dados move os dados do ponto de coleta para o armazenamento. Um pipeline de dados extrai dados de uma fonte, faz alterações e os salva em um destino específico. Explicamos os componentes críticos da arquitetura de pipeline de dados abaixo.

### **Fontes de dados**

Uma fonte de dados pode ser uma aplicação, um dispositivo ou outro banco de dados. Fontes diferentes podem enviar dados para o pipeline. O pipeline também pode extrair pontos de dados usando uma chamada de API, webhook ou processo de duplicação de dados. Você pode sincronizar a extração de dados para processamento em tempo real ou coletar dados em intervalos programados de suas fontes de dados.

### **Transformações**

À medida que os dados brutos fluem pelo pipeline, eles mudam para se tornarem mais úteis para business intelligence. Transformações são operações (como classificação, reformatação, desduplicação, verificação e validação) que alteram dados. Seu pipeline pode filtrar, resumir ou processar dados para atender aos seus requisitos de análise.

### **Dependências**

Como as mudanças acontecem sequencialmente, podem existir dependências específicas que reduzem a velocidade de movimentação de dados no pipeline. Existem dois tipos principais de dependências - técnicas e de negócios. Por exemplo, se o pipeline tiver que esperar que uma fila central seja preenchida antes de prosseguir, é uma dependência técnica. Por outro lado, se o pipeline tiver que pausar até que outra unidade de negócios verifique os dados, é uma dependência de negócios.

### **Destinos**

O endpoint de seu pipeline de dados pode ser um data warehouse, data lake ou outra aplicação de análise de dados ou business intelligence. Às vezes, o destino também é chamado de _coletor de dados_.

Exemplo de um fluxo pipeli