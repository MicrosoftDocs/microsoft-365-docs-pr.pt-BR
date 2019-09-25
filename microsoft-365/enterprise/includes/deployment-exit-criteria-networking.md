<a name="crit-networking-step1"></a>
### <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="53dff-101">Obrigatório: rede preparada para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="53dff-101">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="53dff-102">Seus escritórios têm largura de banda de Internet adequada para o tráfego do Microsoft 365, incluindo a instalação e atualizações do Office 365, do Microsoft Intune e do Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="53dff-102">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, and Windows 10 Enterprise installation and updates</span></span>
- <span data-ttu-id="53dff-103">Sua rede geral mapeia para uma [Arquitetura de referência do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span><span class="sxs-lookup"><span data-stu-id="53dff-103">Your overall network maps to an Office 365 reference architecture</span></span>
- <span data-ttu-id="53dff-104">As alterações de rede foram testadas e atendem aos requisitos de latência de tráfego.</span><span class="sxs-lookup"><span data-stu-id="53dff-104">Your network changes have been piloted and tested and meet with your traffic latency requirements</span></span>

<span data-ttu-id="53dff-105">Se necessário, a [Etapa 1](../networking-provide-bandwidth-cloud-services.md) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="53dff-105">If needed, [Step 1](../networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
### <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="53dff-106">Obrigatório: seus escritórios locais terem uma resolução de nome e conexões da Internet local</span><span class="sxs-lookup"><span data-stu-id="53dff-106">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="53dff-p101">Você deve configurar cada escritório local com acesso à Internet por meio de um ISP local cujos servidores DNS usem um endereço IP público local que identifique sua localização na Internet. Isso garante o melhor desempenho possível para os usuários que acessarem os serviços de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="53dff-p101">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet. This ensures the best possible performance for users who access Office 365 and Intune.</span></span>

<span data-ttu-id="53dff-109">Se você não usar um ISP local para cada filial, o desempenho sofrer, pois o tráfego de rede deverá percorrer o backbone da organização ou as solicitações de dados serão atendidas por servidores remotos de front-end.</span><span class="sxs-lookup"><span data-stu-id="53dff-109">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="53dff-110">Como testar</span><span class="sxs-lookup"><span data-stu-id="53dff-110">How to test</span></span>
<span data-ttu-id="53dff-p102">Use uma ferramenta ou site em um dispositivo do escritório em questão para determinar o endereço IP público que o servidor proxy está utilizando. Por exemplo, use a página [What Is My IP Address](https://www.whatismypublicip.com/). Esse endereço IP público atribuído por seu ISP deve ser geograficamente local. Ele não deve ser um intervalo de endereços IP públicos para uma matriz ou de um fornecedor de segurança de rede baseado na nuvem.</span><span class="sxs-lookup"><span data-stu-id="53dff-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="53dff-115">Se necessário, a [Etapa 2](../networking-dns-resolution-same-location.md) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="53dff-115">If needed, [Step 2](../networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
### <a name="optional-unneccessary-network-hairpins-are-removed"></a><span data-ttu-id="53dff-116">Opcional: os hairpins de rede desnecessários serem removidos</span><span class="sxs-lookup"><span data-stu-id="53dff-116">Optional: Unneeded network hairpins are removed</span></span>

<span data-ttu-id="53dff-p103">Você examinou os hairpins da rede e determinou o impacto deles no desempenho de todos os escritórios. Você removeu hairpins da rede sempre que possível ou trabalhou com sua rede de terceiros ou provedor de segurança para implementar o emparelhamento ideal do Microsoft 365 para a rede deles.</span><span class="sxs-lookup"><span data-stu-id="53dff-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="53dff-119">Se necessário, a [Etapa 3](../networking-avoid-network-hairpins.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="53dff-119">If needed, [Step 3](../networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
### <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="53dff-120">Opcional: você configurou o bypass de tráfego em seus navegadores da Internet e dispositivos periféricos</span><span class="sxs-lookup"><span data-stu-id="53dff-120">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="53dff-121">Você implantou os arquivos PAC mais recentes em seus navegadores da Internet locais para que o tráfego para nomes de domínio DNS do Microsoft 365 ignorassem os servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="53dff-121">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="53dff-122">Você configurou seus dispositivos de perímetro de rede, como firewalls e dispositivos de interrupção e inspeção de SSL e dispositivos de inspeção empacotados, para usar o bypass de tráfego ou para executar um processamento mínimo do tráfego para os pontos de extremidade Otimizar e Permitir categorias do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="53dff-122">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


#### <a name="how-to-test"></a><span data-ttu-id="53dff-123">Como testar</span><span class="sxs-lookup"><span data-stu-id="53dff-123">How to test</span></span>

<span data-ttu-id="53dff-124">Use ferramentas de registro em log nos seus dispositivos de perímetro de rede para garantir que o tráfego para destinos do Microsoft 365 não esteja sendo inspecionado, descriptografado ou prejudicado de outras formas.</span><span class="sxs-lookup"><span data-stu-id="53dff-124">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="53dff-125">Se necessário, a [Etapa 4](../networking-configure-proxies-firewalls.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="53dff-125">If needed, [Step 4](../networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
### <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="53dff-126">Opcional: Seus clientes e aplicativos do Office 365 serem configurados para um desempenho ideal</span><span class="sxs-lookup"><span data-stu-id="53dff-126">Optional: Your clients and Office 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="53dff-127">Você deve otimizar as configurações de Protocolo de Controle de Transmissão (TCP) em seus dispositivos cliente e para os serviços do Exchange Online, do Skype for Business Online, do SharePoint Online e do Project Online.</span><span class="sxs-lookup"><span data-stu-id="53dff-127">You have optimized the Transmssion Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="53dff-128">Se necessário, a [Etapa 5](../networking-optimize-tcp-performance.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="53dff-128">If needed, [Step 5](../networking-optimize-tcp-performance.md) can help you with this option.</span></span>
