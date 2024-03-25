A escrita em git é composta por comandos, opções de configuração desses comandos e simbologias de apoio a essas configurações. É sempre necessário ler a documentação do Git para acessar todos os conteúdos disponíveis, mas estes são os principais e mais usados:

1. **Traço Único (' - '):**

	- Usado para opções curtas em comandos.
	- Exemplo: `-m` para especificar uma mensagem de commit: `git commit -m "Mensagem do commit"`

2. **Dois traços (' -- '):**

	- Usado para opções longas em comandos.
	- Exemplo: `--message` para especificar uma mensagem de commit: `git commit --message "Mensagem do commit"`

3. **Colchetes Quadrados ('[ ]'):**

	- Usado para indicar que um argumento é opcional.
	- Exemplo: `[nome-do-arquivo]` em `git add [nome-do-arquivo]`.

4. **Chaves ('{ }'):**

	- Usado para indicar que você deve escolher um valor de uma lista de opções.
	- Exemplo: `{branch}` em `git checkout {branch}`.

5. **Barra Vertical (' | '):**

	- Usado para separar opções mutuamente exclusivas.
	- Exemplo: `git diff [--cached | HEAD]`.

6. **Ponto Final (' . '):**

	- Usado para representar o diretório atual.
	- Exemplo: `git add .` adiciona todos os arquivos no diretório atual ao stage.

7. **Circunflexo (' ^ '):**

	- Usado para referenciar commits específicos em relações de parentesco.
	- Exemplo: `HEAD^` para se referir ao commit pai do HEAD.

8. **Til (' ~ '):**

	- Usado para referenciar commits anteriores em uma linha de tempo linear.
	- Exemplo: `HEAD~2` para se referir ao segundo commit anterior ao HEAD.