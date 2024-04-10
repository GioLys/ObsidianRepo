
## <span style="color:#ffc000">Container x Máquina Virtual</span>

### Isolamento:

- **Contêineres**: Os contêineres compartilham o mesmo kernel do sistema operacional hospedeiro, mas são isolados uns dos outros através de namespaces e cgroups do kernel. Isso os torna mais leves em termos de recursos e mais rápidos para iniciar e parar.
- **Máquinas Virtuais**: Cada VM opera com seu próprio sistema operacional e kernel, fornecendo um nível mais alto de isolamento. Isso pode resultar em um pouco mais de sobrecarga de recursos e tempos de inicialização mais longos em comparação com contêineres.

### Overhead:

- **Contêineres**: Têm menos overhead em comparação com as VMs, pois não precisam de um sistema operacional completo para cada instância. Eles compartilham o kernel do host, o que significa que são mais eficientes em termos de recursos.
- **Máquinas Virtuais**: Têm um overhead mais significativo, pois cada VM precisa de seu próprio sistema operacional, incluindo kernel. Isso pode consumir mais memória e CPU do host.

Portabilidade:

- **Contêineres**: São altamente portáteis. As imagens de contêineres geralmente incluem todas as dependências necessárias para a aplicação, o que facilita a execução da mesma aplicação em diferentes ambientes.
- **Máquinas Virtuais**: Também são portáteis, mas devido ao seu tamanho e complexidade, a portabilidade pode ser um pouco mais complicada em comparação com os contêineres.