**Passo 1:  Fazer Alterações no Código**

- Faça as alterações necessárias nos arquivos do seu projeto localmente.

**Passo 2: Adicionar e Comitar Alterações

- Adicione as alterações ao stage usando o comando `git add` seguido do nome dos arquivos ou `.` para adicionar todos os arquivos modificados:

```
git add nome-do-arquivo ou git add .
```

**Passo 3: Faça o Commit das Alterações**

- Faça o commit das alterações utilizando o comando `git commit -m` seguido de uma mensagem que descreva as alterações feitas:

```
git commit -m "Descrição das alterações"
```

**Passo 4: Enviar as Alterações para o Repositório Remoto**

- Envie as alterações locais para o repositório remoto usando o comando `git push`:

```
git push origin nome-do-branch
```

**Passo 5: Atualizar o Repositório Local (Opcional)**

- 1. Se outras pessoas estiverem contribuindo para o mesmo projeto, pode ser útil atualizar seu repositório local com as últimas alterações do repositório remoto.
2. Para sincronizar o repositório local com as alterações do repositório remoto, utilize o comando `git pull`:

```
git pull origin nome-do-branch
```

Acessar a guia de [[Principais Comandos Git]], [[Simbologia Git]] ou [[Opções de configurações Git]]