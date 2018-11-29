---
title: 'Fase 1: Critérios de saída para infraestrutura de rede'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Garanta que a sua configuração atenda aos critérios do Microsoft 365 Enterprise para a infraestrutura de rede.
ms.openlocfilehash: 8161fa2b92ffb4c7c4713e9356c0bc1bfec39d07
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864668"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a><span data-ttu-id="f834b-103">Fase 1: Critérios de saída para infraestrutura de rede</span><span class="sxs-lookup"><span data-stu-id="f834b-103">Phase 1: Networking infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="f834b-104">Se a sua infraestrutura de rede atender às condições a seguir, você estará pronto para passar para a Fase 2.</span><span class="sxs-lookup"><span data-stu-id="f834b-104">If your networking infrastructure meets the following conditions, you’re ready to move to Phase 2.</span></span>

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a><span data-ttu-id="f834b-105">Obrigatório: rede preparada para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f834b-105">Required: Your network is ready for Microsoft 365 Enterprise</span></span>

- <span data-ttu-id="f834b-106">Seus escritórios têm largura de banda de Internet adequada para o tráfego do Microsoft 365, incluindo a instalação e atualizações do Office 365, do Microsoft Intune e do Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f834b-106">Your offices have adequate Internet bandwidth for Microsoft 365 traffic, including Office 365, Microsoft Intune, Windows 10 Enterprise installation and updates</span></span>
- <span data-ttu-id="f834b-107">Escritórios centrais para todo o tráfego de Internet geral</span><span class="sxs-lookup"><span data-stu-id="f834b-107">Central offices for all general Internet traffic</span></span>
- <span data-ttu-id="f834b-108">Filiais para otimizar o tráfego de ponto de extremidade da categoria</span><span class="sxs-lookup"><span data-stu-id="f834b-108">Branch offices for Optimize category endpoint traffic</span></span>
- <span data-ttu-id="f834b-109">Sua rede geral mapeia para uma arquitetura de referência do Office 365</span><span class="sxs-lookup"><span data-stu-id="f834b-109">Your overall network maps to an Office 365 reference architecture</span></span>

<span data-ttu-id="f834b-110">Se necessário, a [Etapa 1](networking-provide-bandwidth-cloud-services.md) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="f834b-110">If needed, [Step 1](networking-provide-bandwidth-cloud-services.md) can help you with this requirement.</span></span>

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a><span data-ttu-id="f834b-111">Obrigatório: seus escritórios locais terem uma resolução de nome e conexões da Internet local</span><span class="sxs-lookup"><span data-stu-id="f834b-111">Required: Your local offices have local Internet connections and name resolution</span></span>

<span data-ttu-id="f834b-p101">Você deve configurar cada escritório local com acesso à Internet por meio de um ISP local cujos servidores DNS usem um endereço IP público local que identifique sua localização na Internet. Isso garante o melhor desempenho possível para os usuários que acessarem o Office 365 e o Intune.</span><span class="sxs-lookup"><span data-stu-id="f834b-p101">You configured each local office with Internet access with a local ISP whose DNS servers use a local public IP address that identifies their location on the Internet. This ensures the best possible performance for users who access Office 365 and Intune.</span></span>

<span data-ttu-id="f834b-114">Se você não usar um ISP local para cada filial, o desempenho sofrer, pois o tráfego de rede deverá percorrer o backbone da organização ou as solicitações de dados serão atendidas por servidores remotos de front-end.</span><span class="sxs-lookup"><span data-stu-id="f834b-114">If you don’t use a local ISP for each branch office, performance can suffer because network traffic must traverse an organization’s backbone or data requests are serviced by remote front-end servers.</span></span>

### <a name="how-to-test"></a><span data-ttu-id="f834b-115">Como testar</span><span class="sxs-lookup"><span data-stu-id="f834b-115">How to test</span></span>
<span data-ttu-id="f834b-p102">Use uma ferramenta ou site em um dispositivo do escritório em questão para determinar o endereço IP público que o servidor proxy está utilizando. Por exemplo, use a página [What Is My IP Address](https://www.whatismypublicip.com/). Esse endereço IP público atribuído por seu ISP deve ser geograficamente local. Ele não deve ser um intervalo de endereços IP públicos para uma matriz ou de um fornecedor de segurança de rede baseado na nuvem.</span><span class="sxs-lookup"><span data-stu-id="f834b-p102">Use a tool or web site from a device in that office to determine the public IP address that the proxy server is using. For example, use the [What Is My IP Address](https://www.whatismypublicip.com/) web page. This public IP address assigned by your ISP should be geographically local. It should not be from a public IP address range for a central office or from a cloud-based network security vendor.</span></span>

<span data-ttu-id="f834b-120">Se necessário, a [Etapa 2](networking-dns-resolution-same-location.md) pode ajudá-lo com esse requisito.</span><span class="sxs-lookup"><span data-stu-id="f834b-120">If needed, [Step 2](networking-dns-resolution-same-location.md) can help you with this requirement.</span></span>

<a name="crit-networking-step3"></a>
## <a name="optional-unneeded-network-hairpins-are-removed"></a><span data-ttu-id="f834b-121">Opcional: os hairpins de rede desnecessários serão removidos</span><span class="sxs-lookup"><span data-stu-id="f834b-121">Optional: Unneeded network hairpins are removed</span></span>

<span data-ttu-id="f834b-p103">Você examinou os hairpins da rede e determinou o impacto deles no desempenho de todos os escritórios. Você removeu hairpins da rede sempre que possível ou trabalhou com sua rede de terceiros ou provedor de segurança para implementar o emparelhamento ideal do Microsoft 365 para a rede deles.</span><span class="sxs-lookup"><span data-stu-id="f834b-p103">You examined your network hairpins and determined their impact on performance for all of your offices. You removed network hairpins where possible or worked with your third-party network or security provider to implement optimal Microsoft 365 peering for their network.</span></span>

<span data-ttu-id="f834b-124">Se necessário, a [Etapa 3](networking-avoid-network-hairpins.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="f834b-124">If needed, [Step 3](networking-avoid-network-hairpins.md) can help you with this option.</span></span>


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a><span data-ttu-id="f834b-125">Opcional: você configurou o bypass de tráfego em seus navegadores da Internet e dispositivos periféricos</span><span class="sxs-lookup"><span data-stu-id="f834b-125">Optional: You have configured traffic bypass on your Internet browsers and edge devices</span></span>

<span data-ttu-id="f834b-126">Você implantou os arquivos PAC mais recentes em seus navegadores da Internet locais para que o tráfego para nomes de domínio DNS do Microsoft 365 ignorassem os servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="f834b-126">You deployed the latest PAC files to your on-premises Internet browsers so that traffic to Microsoft 365 DNS domain names bypass proxy servers.</span></span>

<span data-ttu-id="f834b-127">Você configurou seus dispositivos de perímetro de rede, como firewalls e dispositivos de interrupção e inspeção de SSL e dispositivos de inspeção empacotados, para usar o bypass de tráfego ou para executar um processamento mínimo do tráfego para os pontos de extremidade Otimizar e Permitir categorias do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f834b-127">You configured your network perimeter devices—such as firewalls, and SSL Break and Inspect, and packet inspection devices— to use traffic bypass or to minimally process traffic to the Optimize and Allow categories of Microsoft 365 endpoints.</span></span>


### <a name="how-to-test"></a><span data-ttu-id="f834b-128">Como testar</span><span class="sxs-lookup"><span data-stu-id="f834b-128">How to test</span></span>

<span data-ttu-id="f834b-129">Use ferramentas de registro em log nos seus dispositivos de perímetro de rede para garantir que o tráfego para destinos do Microsoft 365 não esteja sendo inspecionado, descriptografado ou prejudicado de outras formas.</span><span class="sxs-lookup"><span data-stu-id="f834b-129">Use the logging tools on your network perimeter devices to ensure that traffic to Microsoft 365 destinations isn’t being inspected, decrypted, or otherwise hindered.</span></span>

<span data-ttu-id="f834b-130">Se necessário, a [Etapa 4](networking-configure-proxies-firewalls.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="f834b-130">If needed, [Step 4](networking-configure-proxies-firewalls.md) can help you with this option.</span></span>


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a><span data-ttu-id="f834b-131">Opcional: Seus clientes e aplicativos do Office 365 serem configurados para um desempenho ideal</span><span class="sxs-lookup"><span data-stu-id="f834b-131">Optional: Your clients and Office 365 applications are configured for optimal performance</span></span>

<span data-ttu-id="f834b-132">Você deve otimizar as configurações de TCP em seus dispositivos cliente e para os serviços do Exchange Online, do Skype for Business Online, do SharePoint Online e do Project Online.</span><span class="sxs-lookup"><span data-stu-id="f834b-132">You have optimized the Transmssion Control Protocol (TCP) settings on your client devices and for Exchange Online, Skype for Business Online, SharePoint Online, and Project Online services.</span></span>

<span data-ttu-id="f834b-133">Se necessário, a [Etapa 5](networking-optimize-tcp-performance.md) pode ajudá-lo com essa opção.</span><span class="sxs-lookup"><span data-stu-id="f834b-133">If needed, [Step 5](networking-optimize-tcp-performance.md) can help you with this option.</span></span>

## <a name="next-phase"></a><span data-ttu-id="f834b-134">Próxima fase</span><span class="sxs-lookup"><span data-stu-id="f834b-134">Next phase</span></span>

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)| <span data-ttu-id="f834b-135">A sua próxima fase do processo de implantação de ponta a ponta para o Microsoft 365 Enterprise é a [identidade](identity-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="f834b-135">Your next phase in the end-to-end deployment process for Microsoft 365 Enterprise is [identity](identity-infrastructure.md).</span></span> |
