
### Banco de dados:

Podemos afirmar que banco de dados é um conjunto de dados ou informações relacionadas entre si. Os bancos de dados podem ser simples ou extremamente complexos. O analista de sistemas deverá propor soluções, levando em consideração o volume de informações que deverá ser armazenado.

**SGBD:** Um SGBD é um software cuja finalidade é gerenciar as informações de um banco de dados, e que também devem organizar, acessar, controlar e proteger as informações contidas no banco de dados. O SGBD tem por objetivo facilitar a vida do programador ou analista, deixando livre para pensar na modelagem e não ficar pensando em questões técnicas de armazenamento de dados (sendo esta uma das funções do SGBD).

![[Pasted image 20240330135145.png]]

O SGBD é projetado para gerenciar grandes volumes de informações, chegando a 1.152.921.504.606.846.976 bytes ou exabyte. SGBD pode ser distribuído por diversos computadores, no mesmo local ou até em locais diferentes (espaços, cidades, países). <span style="color:#00b0f0">Caso o SGBD esteja em locais físicos diferentes, cada um passa a receber o nome de nó</span>, e uma operação realizada no banco de dados pode ser executada em um ou em mais nós.

Outras funções que podemos destacar do SGBD são a proteção e a recuperação dos dados quando houver problemas de hardware ou software, a segurança a acessos indevidamente autorizados, a possibilidade de compartilhar dados, a administração da redundância e a restrição de integridade dos componentes do banco.

-> O conjunto de requisitos de um SGBD recebe o nome de ACID dos termos em inglês:
				**A**_tomicity_, **C**_onsistency_, **I**_solation_, **D**_urability_ 
				
ou, respectivamente: **A**tomicidade, **C**onsistência, **I**solamento e **D**urabilidade.

<span style="color:#ffc000">O SGBD deve garantir várias propriedades durante uma transação.</span> 

<span style="color:#ffc000">Transação</span> é um processo ou um determinado programa que pode incluir vários bancos de dados ou somente uma parte do banco de dados, realizando atividades como consultas, alterações e até exclusão de informações da base de dados.

A transação é o resultado da execução de um programa de usuário escrito em uma linguagem de manipulação de alto nível ou em uma linguagem de programação, como Java, C# ou SQL, entre outras.

## <span style="color:#7030a0">Requisitos de um SGBD</span> 

1. **Atomicidade (Atomicity):** Significa que uma transação é considerada como uma unidade atômica de trabalho. Isso implica que todas as operações dentro da transação são realizadas com sucesso ou nenhuma delas é realizada de forma alguma. Se uma parte da transação falhar, todas as operações devem ser revertidas, deixando o banco de dados em um estado consistente.
    
2. **Consistência (Consistency):** Refere-se ao fato de que o banco de dados deve passar de um estado válido para outro estado válido após a conclusão de uma transação. Em outras palavras, qualquer alteração no banco de dados deve seguir todas as restrições e regras definidas, mantendo a integridade dos dados.
    
3. **Isolamento (Isolation):** Esse princípio garante que transações concorrentes sejam executadas de forma isolada umas das outras, como se estivessem sendo executadas sequencialmente. Isso evita problemas como "leitura suja", "leitura não repetível", "escrita fantasma", entre outros, que podem ocorrer quando múltiplas transações acessam os mesmos dados simultaneamente.
    
4. **Durabilidade (Durability):** Implica que, uma vez que uma transação foi confirmada, as mudanças feitas por essa transação permanecem no banco de dados, mesmo em caso de falha do sistema. Em outras palavras, os dados persistem e não são perdidos, seja devido a um desligamento inesperado do sistema, falhas de hardware ou qualquer outro tipo de erro.

## <span style="color:#7030a0">Tipos de SGBD</span> 

Podemos citar alguns SGBDs que mais se destacam atualmente: Oracle, SQL Server, MySQL, Postgree, entre outras opções existentes no mercado.

1. **Oracle** é um SGBD proprietário e sua licença precisa ser adquirida, portanto, não é freeware. É utilizado em médias e grandes empresas e foi projetado para sistemas que requerem alto desempenho e segurança. As versões atuais possuem recursos para computação em nuvem, _big data_, multiplataformas e também muitas ferramentas de administração e de desenvolvimento de aplicações que servem como _interface_, possibilitando mais facilidades no acesso ao banco de dados.

2. O **SQL** Server pertence à empresa Microsoft e possui versões gratuitas e pagas. As novas versões permitem que o SGBD funcione no LINUX e em Container Docker. Atualmente, o SQL Server, é um dos SGBDs mais utilizados no mercado, porém está perdendo espaço para outros que têm código aberto. 

3. O **MySQL** é _Open Source_ ou código aberto e possui licenças GNU/GPL (Licença Pública Geral – _General Public License_) permitindo que qualquer usuário edite o seu código fonte de forma que atenda aos requisitos de uma determinada aplicação que está sendo implementada. Atualmente, pertence ao Oracle, cujo objetivo, com a disponibilização _freeware_, é a fomentação do uso desta tecnologia. Sua capacidade de processamento de transações é muito grande e pode ser utilizado por grandes empresas. Um fator a ser considerado é o quesito segurança. Por ser código aberto, o cuidado com falhas de segurança deve ser redobrado. O MySQL possui uma versão bem mais robusta, porém paga, com diversos recursos avançados, como auditoria, _firewalls_, monitoramento e backups avançados.

4. **Postgree** é um SGBD muito utilizado por rodar em várias plataformas de desenvolvimento como código aberto (_Open Source_) e de desenvolvimento livre. É usado em sistemas mais robustos, em que a base de dados é muito grande, em empresas corporativas. Possui funcionalidades de controle de concorrência mais elaboradas e sofisticadas. 

Existem muitos outros SGBDs, como o **Access** da Microsoft, que está integrado no pacote do Office, ideal para pequenas aplicações no ambiente Windows. Outro exemplo é o **Firebird**, gratuito e capaz de gerenciar desde bases pequenas até extensos volumes de dados, disponível para vários sistemas operacionais. Há, ainda, o DB2 da IBM, que perdeu muito mercado para os concorrentes, mas ainda é utilizado em sistemas que vão de celulares a _mainframes_.

## <span style="color:#7030a0">Modelagem de uma base de dados</span> 

### Modelo de dados relacional:

O modelo relacional não é algo estático, ele evolui e se expande, assim como a própria matemática. A proposta do modelo relacional baseia-se na ideia de que as informações em uma base de dados podem ser representadas em tabelas cujas linhas apresentam as informações cadastradas. A teoria dos conjuntos se aplica no modelo relacional, pois as operações realizadas nas tabelas são baseadas na álgebra relacional, como seleção, união, junção, subtração, produto cartesiano e projeção.

![[Pasted image 20240330154030.png]]

<span style="color:#ffc000">Um modelo relacional é composto de muitas tabelas. O modelo relacional tem três aspectos básicos:</span> 

- **Estrutural**: os dados inseridos no banco de dados são reconhecidos pelos usuários como tabelas. 

- **De integridade**: as tabelas precisam satisfazer as restrições de integridades (será abordado na próxima unidade). 

- **Manipulador**: são as operações que poderemos realizar com as tabelas, com a intenção de juntar, selecionar, excluir, entre outras operações.

### Criação de um modelo de banco de dados:

A fase inicial do projeto de banco de dados, segundo Korth, Silberschatz e Sudarshan (2003), é caracterizar completamente as necessidades de dados dos prováveis usuários do banco de dados. As etapas da modelagem possuem algumas funções que podem ser classificadas como:

- **Concepção**: é um entendimento da necessidade do cliente com relação ao software e é quando serão estabelecidos os objetivos principais da solução desejada. 
- **Elicitação**: são as conversas com os usuários do software com o objetivo de colher mais informações sobre os procedimentos realizados e que deverão estar presentes no software. 
- **Elaboração**: criação de modelos para a formalização dos requisitos (aqui entra a nossa disciplina). Com o modelo é possível encontrar falhas ou esquecimentos dos clientes ou do próprio analista de sistemas. 
- **Negociação**: com o modelo apresentado, os clientes podem querer mais itens, é necessário verificar as viabilidades das sugestões.
### OLAP e OLTP:

1. **OLAP (Processamento Analítico Online):** OLAP é uma abordagem para responder a consultas complexas sobre dados, focada na análise de informações multidimensionais a partir de diferentes perspectivas. Principais características do OLAP incluem:
    
    - **Modelagem multidimensional:** Os dados são organizados em estruturas multidimensionais, como cubos, que permitem análise rápida e flexível de várias dimensões (por exemplo, tempo, produto, região).
    - **Consultas analíticas:** Os usuários podem realizar análises complexas, como drill-down (detalhamento), roll-up (resumo), slice (filtragem) e dice (seleção), para explorar os dados de maneira eficiente.
    - **Desempenho otimizado para análise:** Os sistemas OLAP são projetados para lidar com grandes volumes de dados e retornar resultados rapidamente, garantindo uma experiência de usuário eficiente.
    
    Exemplos de aplicativos OLAP incluem sistemas de Business Intelligence (BI), painéis de controle e ferramentas de análise de dados, que são amplamente utilizados para apoiar processos de tomada de decisão e descoberta de insights.
    
2. **OLTP (Processamento de Transações Online):** OLTP é uma abordagem de processamento de dados voltada para a execução eficiente de transações individuais em tempo real. Principais características do OLTP incluem:
    
    - **Processamento rápido de transações:** Os sistemas OLTP são otimizados para suportar a execução rápida e eficiente de transações, como inserções, atualizações e exclusões de registros.
    - **Suporte à concorrência:** Deve permitir que várias transações sejam processadas simultaneamente, mantendo a consistência e a integridade dos dados.
    - **Garantia de durabilidade:** As transações concluídas devem ser permanentemente registradas e armazenadas para garantir que não sejam perdidas, mesmo em caso de falha do sistema.

![[Pasted image 20240330155006.png]]

# <span style="color:#7030a0"> Modelagem de dados através do modelo entidade-relacionamento</span>

### MER:

Um <span style="color:#ffc000">Modelo de Entidade-Relacionamento (MER)</span> é uma técnica usada para modelar dados em um sistema de banco de dados. Ele descreve as entidades (objetos ou conceitos sobre os quais os dados são armazenados) e os relacionamentos entre essas entidades. O MER é uma <span style="color:#00b0f0">representação gráfica e visual </span>da estrutura de dados de um sistema, que pode ser usada como base para o design e implementação de um banco de dados.

Aqui estão os principais componentes de um modelo de entidade-relacionamento:

1. **Entidade:** Uma entidade é um objeto ou conceito do mundo real que pode ser diferenciado de outros objetos. No contexto de um banco de dados, uma entidade geralmente corresponde a uma tabela. Por exemplo, em um sistema de gestão de biblioteca, as entidades podem incluir Livro, Autor e Editora.
    
2. **Atributo:** Um atributo é uma característica ou propriedade que descreve uma entidade. Em termos de banco de dados, um atributo corresponde a uma coluna em uma tabela. Por exemplo, os atributos de uma entidade Livro podem incluir Título, ISBN e Ano de Publicação.
    
3. **Relacionamento:** Um relacionamento é uma associação entre duas ou mais entidades. Ele descreve como as entidades estão conectadas ou interagem entre si. Os relacionamentos podem ser de vários tipos, como um-para-um, um-para-muitos e muitos-para-muitos. Por exemplo, em um sistema de gestão de biblioteca, pode haver um relacionamento "Autor escreve Livro", onde um autor pode escrever vários livros e um livro pode ser escrito por um ou mais autores.
    
4. **Chave Primária:** A chave primária é um atributo (ou conjunto de atributos) que identifica exclusivamente cada instância de uma entidade em uma tabela. Ela garante a unicidade das linhas em uma tabela. Por exemplo, o ISBN de um livro pode ser usado como chave primária na entidade Livro.
    
5. **Chave Estrangeira:** Uma chave estrangeira é um atributo em uma tabela que estabelece uma relação com a chave primária de outra tabela. Ela é usada para vincular as tabelas em um relacionamento. Por exemplo, em uma tabela de empréstimos de livros, a chave estrangeira pode ser o ISBN do livro, referenciando a tabela de Livros.

![[Pasted image 20240330165753.png]]

### Tipos de Entidades:

- **Entidades Fortes**: são uma tabela autônoma que não depende de outra para sua existência. Alguns exemplos: Aluno, Curso, Cliente, Empresa, Paciente. Na análise de requisitos, são facilmente encontradas pois são substantivos fortes e significativos. 

- **Entidades Fracas ou Dependentes**: são uma tabela que necessita de outra para realmente existir e somente existe por causa da Entidade Forte. Entidades fracas podem ser representadas por meio de retângulos com bordas duplas (na maioria dos modelos atuais ela é representada somente com o retângulo). Por exemplo: a tabela Dependente só existe por que existe a tabela Funcionário, pois, para que exista um dependente cadastrado, tem que existir um funcionário que “possui” esse dependente. Se não existisse a tabela Funcionário, certamente não existiria a tabela Dependente.

- **Entidades Agregadas**: são criadas quando temos um conjunto de campos que se repetem em mais de uma entidade, por exemplo: Aluno e Professor têm dados de endereço; para evitar repetições, podemos criar uma nova entidade agregada chamada Endereço para guardar esse tipo de dado.

- **Entidades Subordinadas**: representam uma especialização em que uma entidade supertipo possui várias entidades subordinadas que são especializadas com atributos específicos. Por exemplo, podemos ter dois tipos de clientes: Pessoa Física e Pessoa Jurídica. Os dois têm campos em comum que ficariam na entidade supertipo Cliente, e nas entidades Pessoa Física e Pessoa Jurídica somente estariam os campos específicos de cada tipo de cliente.

- **Entidades Associativas**: somente existem em razão do tipo de relacionamento que existe entre as tabelas. O nome desse tipo de tabela deve ser algo significativo, como Contrato ou Histórico, e é comum podermos nomeá-la com a mistura de nomes entre duas tabelas (como veremos mais adiante). Nos requisitos de um bancode dados, esse tipo de tabela denota a um verbo ou tempo verbal, por exemplo: atender, contratar, prescrever, entre outras.

### Grau de relacionamento ou cardinalidade:

Quando temos um relacionamento entre duas entidades, o número de ocorrências de uma entidade que está associada a ocorrências de outra entidade determina o **grau de relacionamento** ou de **cardinalidade** entre as tabelas (ABREU; MACHADO, 2009). O grau de relacionamento é a quantidade de entidades que estão ligadas ao relacionamento, podendo ser:

- **Relacionamento unário (grau 1)**: uma entidade se relaciona com ela mesma. 

- **Relacionamento binário (grau 2)**: é um relacionamento que liga dois tipos diferentes de entidades. É o evento mais comum dos tipos de relacionamentos. 

- **Relacionamento ternário (grau 3)**: é um relacionamento em que três entidades estão conectadas. 

- **Relacionamento quaternário (grau 4)**: é um relacionamento em que quatro tabelas estão conectadas. 

- **Relacionamento n-ário**: é um relacionamento com mais de quatro tabelas envolvidas. Esse tipo de relacionamento é o menos aconselhável, visto que a possibilidade de redundâncias no banco pode ser maior.

# <span style="color:#7030a0"> Diagrama entidade-relacionamento</span>

Há duas abordagens clássicas tradicionais que podem ser adotadas como estratégia de modelagem em um diagrama de entidade-relacionamentos:

-   **Estratégia** **_top-down_**: <span style="color:#00b0f0">inicializa-se identificando os conjuntos de dados</span> e, em seguida, são definidos os elementos de cada um desses conjuntos. O processo envolve a identificação de diferentes tipos de entidades e a definição de cada atributo. Esta técnica é utilizada em banco de dados maiores.

-   **Estratégia** **_bottom-up_**: <span style="color:#00b0f0">primeiramente são identificados os elementos de dados</span>, ou seja, os itens, e então eles são agrupados em conjuntos de dados. Neste caso, os atributos são identificados primeiro e, ao agrupá-los, teremos as tabelas. Geralmente, esta técnica é utilizada em banco de dados pequenos.

> As abordagens _top-down_ e _bottom-up_ acabam se complementando, pois muitas vezes um analista ou projetista aplica as duas técnicas no mesmo banco de dados a ser modelado, surgindo então uma abordagem mista, denominada _middle-up-down_.

### Modelagem conceitual x Modelagem lógica

![[Pasted image 20240331140628.png]]

A <span style="color:#00b0f0">modelagem conceitua</span>l em um projeto de banco de dados   é considerada de alto nível, pois possui como finalidade a fácil compreensão entre os usuários envolvidos na modelagem,  como ressaltam Korth, Silberschatz e Sudarshan (2012). O foco da modelagem conceitual é detalhar e discutir o funcionamento do negócio do cliente e não o uso de determinada tecnologia, descartando dados de como as informações serão armazenadas e depois recuperadas em banco de dados.

Assim que o<span style="color:#00b0f0"> modelo lógico</span> começar a ser implementado, o modelo conceitual servirá de apoio à construção do esquema do banco de dados. Navathe e Ramez (2005) afirmam que durante ou mesmo ao término do esquema conceitual, as operações básicas do modelo de dados podem ser usadas para especificar as operações de alto nível do usuário e servem para verificar se o modelo possui todos os requisitos listados pelo cliente.

Para criar um modelo lógico e mais coeso do banco de dados, são necessárias várias revisões na descrição do modelo conceitual (de alto nível) e, desta forma, encontrar:

- **Tabelas**: em substantivos, objetos reais e objetos que podem armazenar informações.
- **Campos**: em características específicas de algum objeto  ou adjetivos.
- **Relacionamentos**: em verbos que “ligam” uma tabela a outra.
- **Cardinalidades**: a quantidade de vezes que cada tabela pode estar relacionada com outra.