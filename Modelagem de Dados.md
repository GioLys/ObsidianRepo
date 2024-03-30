
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

