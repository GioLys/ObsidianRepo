
## <span style="color:#ffc000">Container x Máquina Virtual</span>

### Isolamento:

- **Contêineres**: Os contêineres compartilham o mesmo kernel do sistema operacional hospedeiro, mas são isolados uns dos outros através de namespaces e cgroups do kernel. Isso os torna mais leves em termos de recursos e mais rápidos para iniciar e parar.
- **Máquinas Virtuais**: Cada VM opera com seu próprio sistema operacional e kernel, fornecendo um nível mais alto de isolamento. Isso pode resultar em um pouco mais de sobrecarga de recursos e tempos de inicialização mais longos em comparação com contêineres.

### Overhead:

- **Contêineres**: Têm menos overhead em comparação com as VMs, pois não precisam de um sistema operacional completo para cada instância. Eles compartilham o kernel do host, o que significa que são mais eficientes em termos de recursos.
- **Máquinas Virtuais**: Têm um overhead mais significativo, pois cada VM precisa de seu próprio sistema operacional, incluindo kernel. Isso pode consumir mais memória e CPU do host.

### Portabilidade:

- **Contêineres**: São altamente portáteis. As imagens de contêineres geralmente incluem todas as dependências necessárias para a aplicação, o que facilita a execução da mesma aplicação em diferentes ambientes.
- **Máquinas Virtuais**: Também são portáteis, mas devido ao seu tamanho e complexidade, a portabilidade pode ser um pouco mais complicada em comparação com os contêineres.

### Segurança:

- **Contêineres**: Por compartilharem o kernel do host, se um contêiner for comprometido, há potencial para que outros contêineres no mesmo host sejam afetados. No entanto, as tecnologias de contêineres têm se desenvolvido para mitigar esses riscos com recursos como namespaces e capacidades de segurança adicionais.
- **Máquinas Virtuais**: Oferecem um nível mais alto de isolamento entre as VMs. Se uma VM for comprometida, as outras VMs no mesmo host normalmente não são afetadas.

### Flexibilidade:

- **Contêineres**: São mais adequados para aplicações distribuídas e escaláveis, especialmente em ambientes de microserviços. Eles são mais leves e podem ser mais facilmente dimensionados horizontalmente.
- **Máquinas Virtuais**: Podem ser mais adequadas para aplicações que exigem diferentes sistemas operacionais ou que têm requisitos específicos de hardware, como em ambientes de teste e desenvolvimento.

## <span style="color:#ffc000">Sobre o Docker</span>

 Docker é uma plataforma que implementa virtualização de software e utiliza a tecnologia de contêineres para facilitar a implantação e execução de aplicações. Podemos entender _contêiner_ como uma <span style="color:#92d050">unidade leve e portátil que irá conter todo o necessário para executar um pedaço de software, incluindo o código, runtime, bibliotecas e dependências.</span> Neste modelo de virtualização temos diversos benefícios,com destaque para: isolamento de contextos e o versionamento de aplicações.

#### Isolamento de Contextos

Como cada contêiner possui seu próprio sistema de arquivos, processo, espaço de rede e recursos, garantindo que a aplicação dentro do contêiner não interfira em outras aplicações ou no sistema hospedeiro, isso proporciorna um alto grau de independência e isolamento.

#### Versionamento de Aplicações

No docker as aplicações são encapsuladas em imagens, que são versões imutáveis e autossuficientes. Uma imagem docker é composta por camadas, permitindo versionamento eficiente e a reutilização de partes comuns entre diferentes aplicações. Utilizando um arquivo conhecido como Dockerfile, o versionamento é facilitado , um arquivo de configuração que descreve os passos para criar uma imagem. As alterações no Dockerfile resultam em novas versões da imagem, garantindo consistência na implantação.

O Docker proporciona uma abordagem eficiente para o desenvolvimento, empacotamento e execução de aplicações, trazendo benefícios como isolamento de contextos, consistência entre ambientes e versionamento controlado. Essas características tornam o Docker uma ferramenta poderosa para equipes de desenvolvimento e operações que buscam eficiência e confiabilidade em todo o ciclo de vida de uma aplicação.

## <span style="color:#ffc000">Princiapis comandos no Docker</span>

1. **docker run**:
    
    - Este comando é usado para criar e iniciar um contêiner a partir de uma imagem Docker. Se a imagem não estiver presente localmente, o Docker a baixará do registro de contêineres padrão (normalmente o Docker Hub). Exemplo: `docker run nome_da_imagem`
2. **docker build**:
    
    - Utilizado para construir uma imagem Docker a partir de um Dockerfile, que é um arquivo de texto que contém todas as instruções necessárias para construir a imagem. Exemplo: `docker build -t nome_da_imagem:tag .`
3. **docker pull**:
    
    - Baixa uma imagem Docker do registro de contêineres especificado (por padrão, o Docker Hub). Exemplo: `docker pull nome_da_imagem`
4. **docker push**:
    
    - Envio de uma imagem Docker para um registro de contêineres, permitindo que ela seja acessada por outros usuários ou máquinas. Exemplo: `docker push nome_da_imagem`
5. **docker ps**:
    
    - Lista todos os contêineres em execução no host. Exemplo: `docker ps`
6. **docker images**:
    
    - Lista todas as imagens Docker presentes localmente no host. Exemplo: `docker images`
7. **docker stop**:
    
    - Para a execução de um ou mais contêineres em execução. Exemplo: `docker stop ID_do_contêiner`
8. **docker rm**:
    
    - Remove um ou mais contêineres parados. Exemplo: `docker rm ID_do_contêiner`
9. **docker rmi**:
    
    - Remove uma ou mais imagens Docker do host. Exemplo: `docker rmi nome_da_imagem`
10. **docker exec**:
    
    - Executa um comando dentro de um contêiner em execução. Exemplo: `docker exec ID_do_contêiner comando`
11. **docker-compose**:
    
    - É usado para definir e executar aplicativos Docker compostos por vários contêineres. Ele usa um arquivo YAML para definir os serviços, redes e volumes necessários para o aplicativo. Exemplo: `docker-compose up`

## <span style="color:#ffc000">O que são imagens?</span>

Uma imagem nada mais é que um <span style="color:#92d050">conjunto de camadas</span>, que ao serem unidas formam imagens. E essas camadas são independentes, cada uma tem o seu respectivo ID (identificador).

As imagens são essenciais para o funcionamento do Docker. Elas fornecem um modelo para a criação de contêineres. <span style="color:#92d050">Uma imagem é um pacote leve e independente que inclui tudo o necessário para executar uma aplicação: o código, o tempo de execução, as bibliotecas, as variáveis de ambiente e as configurações</span>. Em resumo, uma imagem Docker é como uma receita que contém todos os ingredientes necessários para criar um contêiner específico.


> Quando criamos um container, criamos uma camada temporária em cima da imagem, onde conseguimos escrever informações. E, no momento em que esse container é deletado, essa camada extra também é deletada.


## <span style="color:#ffc000">Por que os containers são tão leves?</span> 

Como a imagem é apenas de leitura, podemos ter vários containers baseados na mesma imagem. A diferença é que cada um desses containers terá apenas uma camada diferente de _read-write_, e como essa camada é extremamente leve, a fim de manter essa performance, temos uma **reutilização da imagem para múltiplos containers**.


> O container é leve e otimizado, porque consegue reaproveitar as camadas das imagens prévias que já temos. E, quando criamos novos containers, ele simplesmente reutiliza as mesmas imagens e, consequentemente, as camadas.

## <span style="color:#ffc000">Docker tutorial</span> 

### Criando a imagem:

1. Criar o arquivo "Dockerfile" dentro da pasta a ser conteinizada
2. Adicionar as dependências e instruções de start dentro do Dockerfile
3. No prompt de comando: docker build -t "nome do usuario ou organização"/"nome do aplicativo" (opcional versão ex: ":1.0")