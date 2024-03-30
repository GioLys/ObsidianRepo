
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

### MER:

