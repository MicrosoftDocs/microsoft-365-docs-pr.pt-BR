---
title: 'Fase 1: Critérios de saída para infraestrutura de rede'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Garanta que a sua configuração atenda aos critérios do Microsoft 365 Enterprise para a infraestrutura de rede.
ms.openlocfilehash: f3d2861af90e9a6f8a9b0b64b307dac6b1b76eb1
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831942"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a><span data-ttu-id="83455-103">Fase 1: Critérios de saída para infraestrutura de rede</span><span class="sxs-lookup"><span data-stu-id="83455-103">Phase 1: Networking infrastructure exit criteria</span></span>

![Fase 1 – Rede](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="83455-105">Verifique se sua infraestrutura de rede atende aos seguintes critérios necessários e que você considerou os que são opcionais.</span><span class="sxs-lookup"><span data-stu-id="83455-105">Make sure your networking infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="83455-106">Obrigatório: rede preparada para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="83455-106">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="83455-107">Seus escritórios têm largura de banda de Internet adequada para o tráfego do Microsoft 365, incluindo a instalação e atualizações do Office 365, do Microsoft Intune e do Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="83455-107">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, and Windows 10 Enterprise installation and updates.</span></span>
- <span data-ttu-id="83455-108">Sua rede geral mapeia para uma [Arquitetura de referência do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span><span class="sxs-lookup"><span data-stu-id="83455-108">Your overall network maps to an [Office 365 reference architecture](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span></span>
- <span data-ttu-id="83455-109">As alterações de rede foram testadas e atendem aos requisitos de latência de tráfego.</span><span class="sxs-lookup"><span data-stu-id="83455-109">Your network changes have been piloted and tested and meet with your traffic latency requirements.</span></span>

<span data-ttu-id="83455-110">Se necessário, a [Etapa 1](networking-provide-bandwidth-cloud-services.md) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="83455-110">If needed, [Step 1](networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="83455-111">Obrigatório: seus escritórios locais terem uma resolução de nome e conexões da Internet local</span><span class="sxs-lookup"><span data-stu-id="83455-111">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="83455-112">Você configurou cada escritório local com acesso à Internet por meio de um ISP local cujos servidores DNS usam um endereço IP público local que identifica sua localização na Internet.</span><span class="sxs-lookup"><span data-stu-id="83455-112">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet.</span></span> <span data-ttu-id="83455-113">Isso garante o melhor desempenho possível para os usuários que acessarem os serviços de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83455-113">This ensures the best possible performance for users who access Microsoft 365 cloud services.</span></span>

<span data-ttu-id="83455-114">Se você não usar um ISP local para cada filial, o desempenho sofrer, pois o tráfego de rede deverá percorrer o backbone da organização ou as solicitações de dados serão atendidas por servidores remotos de front-end.</span><span class="sxs-lookup"><span data-stu-id="83455-114">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="83455-115">Como testar</span><span class="sxs-lookup"><span data-stu-id="83455-115">How to test</span></span>
<span data-ttu-id="83455-p102">Use uma ferramenta ou site em um dispositivo do escritório em questão para determinar o endereço IP público que o servidor proxy está utilizando. Por exemplo, use a página [What Is My IP Address](https://www.whatismypublicip.com/). Esse endereço IP público atribuído por seu ISP deve ser geograficamente local. Ele não deve ser um intervalo de endereços IP públicos para uma matriz ou de um fornecedor de segurança de rede baseado na nuvem.</span><span class="sxs-lookup"><span data-stu-id="83455-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="83455-120">Se necessário, a [Etapa 2](networking-dns-resolution-same-location.md) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="83455-120">If needed, [Step 2](networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
## <a name="optional-unnecessary-network-hairpins-are-removed"></a><span data-ttu-id="83455-121">Opcional: os hairpins de rede desnecessários são removidos</span><span class="sxs-lookup"><span data-stu-id="83455-121">Optional: Unneccessary network hairpins are removed</span></span>

<span data-ttu-id="83455-p103">Você examinou os hairpins da rede e determinou o impacto deles no desempenho de todos os escritórios. Você removeu hairpins da rede sempre que possível ou trabalhou com sua rede de terceiros ou provedor de segurança para implementar o emparelhamento ideal do Microsoft 365 para a rede deles.</span><span class="sxs-lookup"><span data-stu-id="83455-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="83455-124">Se necessário, a [Etapa 3](networking-avoid-network-hairpins.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="83455-124">If needed, [Step 3](networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="83455-125">Opcional: você configurou o bypass de tráfego em seus navegadores da Internet e dispositivos periféricos</span><span class="sxs-lookup"><span data-stu-id="83455-125">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="83455-126">Você implantou os arquivos PAC mais recentes em seus navegadores da Internet locais para que o tráfego para nomes de domínio DNS do Microsoft 365 ignorassem os servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="83455-126">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="83455-127">Você configurou seus dispositivos de perímetro de rede, como firewalls e dispositivos de interrupção e inspeção de SSL e dispositivos de inspeção empacotados, para usar o bypass de tráfego ou para executar um processamento mínimo do tráfego para os pontos de extremidade Otimizar e Permitir categorias do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83455-127">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="83455-128">Como testar</span><span class="sxs-lookup"><span data-stu-id="83455-128">How to test</span></span>

<span data-ttu-id="83455-129">Use ferramentas de registro em log nos seus dispositivos de perímetro de rede para garantir que o tráfego para destinos do Microsoft 365 não esteja sendo inspecionado, descriptografado ou prejudicado de outras formas.</span><span class="sxs-lookup"><span data-stu-id="83455-129">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="83455-130">Se necessário, a [Etapa 4](networking-configure-proxies-firewalls.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="83455-130">If needed, [Step 4](networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="83455-131">Opcional: Seus clientes e aplicativos do Office 365 serem configurados para um desempenho ideal</span><span class="sxs-lookup"><span data-stu-id="83455-131">Optional: Your clients and Office 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="83455-132">Você deve otimizar as configurações de Protocolo de Controle de Transmissão (TCP) em seus dispositivos cliente e para os serviços do Exchange Online, do Skype for Business Online, do SharePoint Online e do Project Online.</span><span class="sxs-lookup"><span data-stu-id="83455-132">You have optimized the Transmission Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="83455-133">Se necessário, a [Etapa 5](networking-optimize-tcp-performance.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="83455-133">If needed, [Step 5](networking-optimize-tcp-performance.md) can help you with this option.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="83455-134">Resultados e próximas etapas</span><span class="sxs-lookup"><span data-stu-id="83455-134">Results and next steps</span></span>

<span data-ttu-id="83455-135">Seus usuários de intranet já estão prontos para consumir os serviços de nuvem da Microsoft 365 usando um caminho de rede eficiente para a Internet e através dela.</span><span class="sxs-lookup"><span data-stu-id="83455-135">Your intranet users are now ready to consume Microsoft 365 cloud services over an efficient networking path to and across the Internet.</span></span>

|||
|:-------|:-----|
|![Fase 2 – Identidade](./media/deploy-foundation-infrastructure/identity_icon-small.png)| <span data-ttu-id="83455-137">Se você estiver seguindo as fases para a implantação de ponta a ponta do Microsoft 365 Enterprise, sua próxima fase será [identidade](identity-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="83455-137">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [identity](identity-infrastructure.md).</span></span> |
