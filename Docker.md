
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