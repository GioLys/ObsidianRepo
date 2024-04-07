
> A migração de dados é o processo de transferência de dados de um sistema de armazenamento ou ambiente de computação para outro.

Existem muitas razões pelas quais sua empresa pode precisar realizar um projeto de migração dados. Por exemplo, você pode estar substituindo servidores ou dispositivos de armazenamento ou consolidando ou desativando um data center. <span style="color:#92d050">A migração de dados também é uma etapa essencial no processo geral de migração de infraestrutura de TI local para um ambiente de cloud computing.</span> 

### Migração de Dados para Cloud

Muitas empresas estão optando por migrar cargas de trabalho para a cloud na esperança de hospedar seus aplicativos no ambiente de TI de melhor desempenho e mais barato possível. Escolher a solução certa de migração de dados é a parte principal do processo de planejamento de migração para a cloud e deve ser levado em conta mesmo no início desse processo.

Você pode escolher entre várias opções para transferir dados de um data center local para a cloud, mas, de maneira geral, elas se enquadram em duas categorias:

- _Migração on-line_, em que os dados se movem pela Internet ou por uma conexão WAN privada ou dedicada.  
      
- _Migração off-line_, em que os dados são transferido por meio de um dispositivo de armazenamento que é enviado fisicamente de seu data center de origem para o local de armazenamento de cloud de destino.

A melhor opção para o seu projeto de migração dados específico depende do volume de dados que você precisa migrar, da rapidez com que a migração deve ser realizada, dos tipos de cargas de trabalho envolvidas e dos seus requisitos de segurança.

### Migração de Banco de Dados

A migração de banco de dados é um exemplo de migração de carga de trabalho especializada. Muitos provedores de cloud pública e privada oferecem ferramentas que podem auxiliar ou automatizar partes do processo de migração do banco de dados para assegurar que seu banco de dados permaneça protegido durante o transferência e que não ocorra perda ou distorção dos dados. Além disso, a maioria dos provedores de cloud oferece serviços de migração que podem verificar a integridade de seus dados após a transferência.

Geralmente, o primeiro passo no processo de migração do banco de dados envolve a conversão do esquema do banco de dados de origem (se necessário) para que se torne compatível com o banco de dados de destino. O esquema de um banco de dados é como um blueprint de como ele é organizado, controlando sua arquitetura e estrutura lógica. Se o sistema de gerenciamento de banco de dados de destino usar uma linguagem de definição (DDL) que não seja compatível com a origem, o esquema deverá ser convertido.

As próximas etapas serão migrar os dados e configurar as atualizações adicionais contínuas do armazém de dados. Você pode também consolidar diversos bancos de dados diferentes em um durante esse processo, se necessário.

### Fatores a serem considerados ao formular uma esrratégia de migração de dados

**Tipo de carga de trabalho:** Você pode transferir os dados para cargas de trabalho de missão crítica em etapas, testar em intervalos ao longo do processo e manter os sistemas de origem e destino em execução simultaneamente. Alternativamente, você pode planejar uma transferência de larga escala fora do horário comercial (caso seja possível no período disponível).

**Volume de dados:** Quando você migra menos de 10 terabytes (TB) de dados, o envio de dados para seu novo local de armazenamento em um dispositivo de armazenamento fornecido pelo cliente costuma ser o método mais simples e com o melhor custo-benefício. Para transferências envolvendo grandes volumes de dados, ou seja, até diversos petabytes (PB), um dispositivo de migração de dados especializado fornecido pelo provedor de cloud pode ser a opção mais conveniente e acessível. Embora, em teoria, seja possível usar a migração on-line para qualquer volume de dados, as restrições de tempo limitam a viabilidade para grandes volumes de dados.

**Velocidade de conclusão:** Para a migração on-line, o volume de dados transferido e a velocidade da sua conexão de rede determinará o tempo necessário para realizar a migração de dados. Para migrações off-line, o tempo de envio deve ser levado em conta.

### Melhores Práticas

- **Entenda os dados e para que eles são usados**

- **Avalie cuidadosamente os ambientes de origem e destino.**

- **Verifique os requisitos negócios e impacto potencial no início do processo.**

### Riscos

