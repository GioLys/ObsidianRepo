**Passo 1:  Fazer Alterações no Código**

- Faça as alterações necessárias nos arquivos do seu projeto localmente.

**Passo 2: Configure o Git**

- Abra o terminal ou prompt de comando e configure seu nome de usuário e endereço de e-mail usando os seguintes comandos (substitua "seu_nome_de_usuario" pelo seu nome de usuário do GitHub e "seu_email@example.com" pelo seu e-mail associado à sua conta do GitHub):

```
git config --global user.name "seu_nome_de_usuario"
git config --global user.email "seu_email@example.com"
```

**Passo 3: Crie um repositório remoto no GitHub**

- Crie o repositório e salve a URL do repositório, lembre-se que ela deve terminar com o sufixo .git

```
https://github.com/UserName/YourRepo.git
```

**Passo 4: Inicialize um Repositório Git**

- Navegue até o diretório onde está o arquivo que você deseja enviar para o GitHub usando o terminal ou prompt de comando.
- Inicialize um repositório Git executando o seguinte comando:

```
git init
```

**Passo 5: Adicione o Arquivo ao Repositório**

- Adicione o arquivo que você deseja enviar para o GitHub ao repositório Git usando o seguinte comando:

```
git add nome_do_arquivo
```

Se você quiser adicionar todos os arquivos no diretório, use:

```
git add .
```

**Passo 6: Faça um Commit das Mudanças**

- Faça um commit das mudanças no arquivo usando o seguinte comando:

```
git commit -m "Mensagem de commit descritiva"
```

Substitua "Mensagem de commit descritiva" por uma mensagem que descreva as mudanças que você fez no arquivo.

**Passo 7: Conecte-se ao GitHub**

- Conecte-se ao repositório GitHub onde você deseja enviar o arquivo usando o seguinte comando:

```
git remote add origin URL_do_repositorio
```

Substitua "URL_do_repositorio" pelo URL do repositório GitHub.

**Passo 8: Envie as Mudanças para o GitHub**

- Envie as mudanças para o GitHub usando o seguinte comando:

```
git push -u origin branch_principal
```

Substitua "branch_principal" pelo nome da sua branch principal, geralmente é "main" ou "master".

**Passo 9: Autenticação**

- Você será solicitado a fornecer suas credenciais do GitHub (nome de usuário e senha ou token de acesso pessoal) para autenticar e enviar as mudanças para o repositório remoto.

Acessar a guia de [[Principais Comandos Git]], [[Simbologia Git]] ou [[Opções de configurações Git]]