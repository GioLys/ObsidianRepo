Passo 1: Instale o Git

- Se você ainda não tem o Git instalado, faça o download e instale a versão apropriada para o seu sistema operacional a partir do site oficial: [Git Downloads](https://git-scm.com/downloads)

Passo 2: Configure o Git

- Abra o terminal ou prompt de comando e configure seu nome de usuário e endereço de e-mail usando os seguintes comandos (substitua "seu_nome_de_usuario" pelo seu nome de usuário do GitHub e "seu_email@example.com" pelo seu e-mail associado à sua conta do GitHub):

```
git config --global user.name "seu_nome_de_usuario"
git config --global user.email "seu_email@example.com"
```

Passo 3: Inicialize um Repositório Git

- Navegue até o diretório onde está o arquivo que você deseja enviar para o GitHub usando o terminal ou prompt de comando.
- Inicialize um repositório Git executando o seguinte comando:

```
git init
```

Passo 4: Adicione o Arquivo ao Repositório

- Adicione o arquivo que você deseja enviar para o GitHub ao repositório Git usando o seguinte comando:

```
git add nome_do_arquivo
```

Se você quiser adicionar todos os arquivos no diretório, use:

```
git add .
```

Passo 5: Faça um Commit das Mudanças

- Faça um commit das mudanças no arquivo usando o seguinte comando: