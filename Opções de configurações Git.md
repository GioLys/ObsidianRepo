<span style="color:#7030a0"><span style="color:#7030a0"><span style="color:#ffc000">A escrita em git é composta por comandos, opções de configuração desses comandos e simbologias de apoio a essas configurações. É sempre necessário ler a documentação do Git para acessar todos os conteúdos disponíveis, mas estes são os principais e mais usados:</span></span></span>

1. **-m, --message**:
    
    - Permite especificar uma mensagem de commit ao realizar um commit.
    - Exemplo: `git commit -m "Mensagem do commit"`.
    
2. **-a, --all**:
    
    - Adiciona automaticamente todos os arquivos modificados ao stage ao executar `git commit`.
    - Exemplo: `git commit -a -m "Mensagem do commit"`.
    
3. **-b, --branch**:
    
    - Especifica o nome do branch ao criar um novo branch ou fazer checkout para um branch específico.
    - Exemplo: `git checkout -b novo-branch`.
    
4. **-f, --force**:
    
    - Força uma operação, ignorando possíveis conflitos ou restrições.
    - Exemplo: `git push --force`.
    
5. **-p, --patch**:
    
    - Interage interativamente durante um commit, permitindo selecionar partes específicas das mudanças para incluir.
    - Exemplo: `git add --patch`.
    
6. **-u, --set-upstream**:
    
    - Configura o upstream (repositório remoto padrão) para um branch local ao fazer push.
    - Exemplo: `git push -u origin main`.
    
7. **-n, --dry-run**:
    
    - Executa uma simulação de um comando sem realizar efetivamente nenhuma alteração.
    - Exemplo: `git clean -n`.
    
8. **-v, --verbose**:
    
    - Fornece uma saída mais detalhada ou verbosa do comando executado.
    - Exemplo: `git status -v`.
    
9. **-d, --delete**:
    
    - Deleta branches ou tags específicas.
    - Exemplo: `git branch -d nome-do-branch`.
    
10. **-s, --short**:
    
    - Fornece uma saída mais curta ou resumida do comando executado.
    - Exemplo: `git status -s`.

https://github.com/GioLys/ObsidianRepo