<a name="crit-networking-step1"></a>
### <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a>Obrigatório: rede preparada para o Microsoft 365 Enterprise

- Seus escritórios têm largura de banda de Internet adequada para o tráfego do Microsoft 365, incluindo a instalação e atualizações do Office 365, do Microsoft Intune e do Windows 10 Enterprise
- Escritórios centrais para todo o tráfego de Internet geral
- Filiais para otimizar o tráfego de ponto de extremidade da categoria
- Sua rede geral mapeia para uma arquitetura de referência do Office 365

Se necessário, a [Etapa 1](../networking-provide-bandwidth-cloud-services.md) pode ajudá-lo com esse requisito.

<a name="crit-networking-step2"></a>
### <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a>Obrigatório: seus escritórios locais terem uma resolução de nome e conexões da Internet local

Você deve configurar cada escritório local com acesso à Internet por meio de um ISP local cujos servidores DNS usem um endereço IP público local que identifique sua localização na Internet. Isso garante o melhor desempenho possível para os usuários que acessarem o Office 365 e o Intune.

Se você não usar um ISP local para cada filial, o desempenho sofrer, pois o tráfego de rede deverá percorrer o backbone da organização ou as solicitações de dados serão atendidas por servidores remotos de front-end.

#### <a name="how-to-test"></a>Como testar
Use uma ferramenta ou site em um dispositivo do escritório em questão para determinar o endereço IP público que o servidor proxy está utilizando. Por exemplo, use a página [What Is My IP Address](https://www.whatismypublicip.com/). Esse endereço IP público atribuído por seu ISP deve ser geograficamente local. Ele não deve ser um intervalo de endereços IP públicos para uma matriz ou de um fornecedor de segurança de rede baseado na nuvem.

Se necessário, a [Etapa 2](../networking-dns-resolution-same-location.md) pode ajudá-lo com esse requisito.

<a name="crit-networking-step3"></a>
### <a name="optional-unneeded-network-hairpins-are-removed"></a>Opcional: os hairpins de rede desnecessários serão removidos

Você examinou os hairpins da rede e determinou o impacto deles no desempenho de todos os escritórios. Você removeu hairpins da rede sempre que possível ou trabalhou com sua rede de terceiros ou provedor de segurança para implementar o emparelhamento ideal do Microsoft 365 para a rede deles.

Se necessário, a [Etapa 3](../networking-avoid-network-hairpins.md) pode ajudá-lo com essa opção.


<a name="crit-networking-step4"></a>
### <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a>Opcional: você configurou o bypass de tráfego em seus navegadores da Internet e dispositivos periféricos

Você implantou os arquivos PAC mais recentes em seus navegadores da Internet locais para que o tráfego para nomes de domínio DNS do Microsoft 365 ignorassem os servidores proxy.

Você configurou seus dispositivos de perímetro de rede, como firewalls e dispositivos de interrupção e inspeção de SSL e dispositivos de inspeção empacotados, para usar o bypass de tráfego ou para executar um processamento mínimo do tráfego para os pontos de extremidade Otimizar e Permitir categorias do Microsoft 365.


#### <a name="how-to-test"></a>Como testar

Use ferramentas de registro em log nos seus dispositivos de perímetro de rede para garantir que o tráfego para destinos do Microsoft 365 não esteja sendo inspecionado, descriptografado ou prejudicado de outras formas.

Se necessário, a [Etapa 4](../networking-configure-proxies-firewalls.md) pode ajudá-lo com essa opção.


<a name="crit-networking-step5"></a>
### <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a>Opcional: Seus clientes e aplicativos do Office 365 serem configurados para um desempenho ideal

Você deve otimizar as configurações de TCP em seus dispositivos cliente e para os serviços do Exchange Online, do Skype for Business Online, do SharePoint Online e do Project Online.

Se necessário, a [Etapa 5](../networking-optimize-tcp-performance.md) pode ajudá-lo com essa opção.
