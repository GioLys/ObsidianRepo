
### Banco de dados:

Podemos afirmar que banco de dados é um conjunto de dados ou informações relacionadas entre si. Os bancos de dados podem ser simples ou extremamente complexos. O analista de sistemas deverá propor soluções, levando em consideração o volume de informações que deverá ser armazenado.

**SGBD:** Um SGBD é um software cuja finalidade é gerenciar as informações de um banco de dados, e que também devem organizar, acessar, controlar e proteger as informações contidas no banco de dados. O SGBD tem por objetivo facilitar a vida do programador ou analista, deixando livre para pensar na modelagem e não ficar pensando em questões técnicas de armazenamento de dados (sendo esta uma das funções do SGBD).

![[Pasted image 20240330135145.png]]

O SGBD é projetado para gerenciar grandes volumes de informações, chegando a 1.152.921.504.606.846.976 bytes ou exabyte. SGBD pode ser distribuído por diversos computadores, no mesmo local ou até em locais diferentes (espaços, cidades, países). <span style="color:#00b0f0">Caso o SGBD esteja em locais físicos diferentes, cada um passa a receber o nome de nó</span>, e uma operação realizada no banco de dados pode ser executada em um ou em mais nós.

Outras funções que podemos destacar do SGBD são a proteção e a recuperação dos dados quando houver problemas de hardware ou software, a segurança a acessos indevidamente autorizados, a possibilidade de compartilhar dados, a administração da redundância e a restrição de integridade dos componentes do banco.

-> O conjunto de requisitos de um SGBD recebe o nome de ACID dos termos em inglês:
				**A**_tomicity_, **C**_onsistency_, **I**_solation_, **D**_urability_ 
				
ou, respectivamente: **A**tomicidade, **C**onsistência, **I**solamento e **D**urabilidade.