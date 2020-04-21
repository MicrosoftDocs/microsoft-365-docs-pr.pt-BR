---
title: 'Etapa 2: Configurar conexões locais com a Internet para cada escritório'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar a resolução de DNS para obter um melhor desempenho.
ms.openlocfilehash: bc1460ec40cda26d4784c7af5e909e4dca3c1f24
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583432"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="d6249-103">Etapa 2: Configurar conexões locais com a Internet para cada escritório</span><span class="sxs-lookup"><span data-stu-id="d6249-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="d6249-104">*Esta etapa é obrigatória e se aplica para as versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d6249-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1 – Rede](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="d6249-p101">Na Etapa 2, você verifica se cada um dos escritórios tem conexões de Internet locais e usa servidores DNS locais. Esses dois elementos são necessários para reduzir a latência da conexão e garantir que os computadores clientes locais façam conexões com o ponto de entrada mais próximo dos serviços baseados em nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6249-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="d6249-108">Em redes tradicionais para grandes organizações, o tráfego da Internet viaja pelo backbone da rede até uma conexão de Internet central.</span><span class="sxs-lookup"><span data-stu-id="d6249-108">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection.</span></span> <span data-ttu-id="d6249-109">Isso não funciona bem para otimizar o desempenho de uma infraestrutura de Software como Serviço (SaaS) distribuída globalmente, que inclui os produtos do Office 365 e do Intune no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6249-109">This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Intune products in Microsoft 365.</span></span>

<span data-ttu-id="d6249-110">A Rede Global da Microsoft inclui uma infraestrutura de *Porta Frontal de Serviço Distribuído*, uma borda de rede altamente disponível e escalonável com locais distribuídos geograficamente.</span><span class="sxs-lookup"><span data-stu-id="d6249-110">The Microsoft Global Network includes a *Distributed Service Front Door* infrastructure, a highly available and scalable network edge with geographically distributed locations.</span></span> <span data-ttu-id="d6249-111">Ele finaliza as conexões do usuário final em um servidor de front-end e roteia com eficiência o tráfego do usuário final dentro da Rede Global da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6249-111">It terminates end user connections at a front door server and efficiently routes end user traffic within the Microsoft Global Network.</span></span>

![A Rede Global da Microsoft](../media/networking-dns-resolution-same-location/microsoft-global-network.png)

<span data-ttu-id="d6249-113">Para obter o melhor desempenho, os clientes locais devem acessar um servidor de front-end que esteja geograficamente mais próximo deles, em vez de enviar o tráfego por um backbone de rede e ao servidor de front-end mais próximo da conexão central com a Internet da organização.</span><span class="sxs-lookup"><span data-stu-id="d6249-113">For the best performance, on-premises clients should access a front door location that is geographically closest to them, rather than sending the traffic over a network backbone and to the front door that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="d6249-114">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d6249-114">Here’s an example.</span></span>

![Exemplo de como usar a Rede Global da Microsoft](../media/networking-dns-resolution-same-location/microsoft-global-network-example.png)

<span data-ttu-id="d6249-116">Quando um usuário na filial de Paris deseja acessar um site do SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="d6249-116">When a user in the Paris branch office wants to access a SharePoint Online site:</span></span>

1. <span data-ttu-id="d6249-117">Ele envia uma consulta DNS para resolver um nome, como contoso.sharepoint.com.</span><span class="sxs-lookup"><span data-stu-id="d6249-117">It sends a DNS query to resolve a name, such as contoso.sharepoint.com.</span></span> 
2. <span data-ttu-id="d6249-118">O servidor DNS fornecido pelo ISP encaminha essa consulta para um servidor DNS da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d6249-118">The DNS server provided by the ISP forwards that query to a Microsoft DNS server.</span></span>
3. <span data-ttu-id="d6249-119">Os servidores DNS da Microsoft correspondem ao endereço IP de origem da consulta DNS encaminhada à região do mundo atribuída ao endereço.</span><span class="sxs-lookup"><span data-stu-id="d6249-119">Microsoft’s DNS servers match the source IP address of the forwarded DNS query to the region of the world assigned that address.</span></span> <span data-ttu-id="d6249-120">O servidor DNS da Microsoft responde com o endereço IP da front-end de Rede da Microsoft mais próxima na Europa.</span><span class="sxs-lookup"><span data-stu-id="d6249-120">The Microsoft DNS server responds with the IP address of the nearest Microsoft Network front door in Europe.</span></span>
4. <span data-ttu-id="d6249-121">O servidor DNS do ISP envia esse endereço IP para o usuário.</span><span class="sxs-lookup"><span data-stu-id="d6249-121">The ISP DNS server sends that IP address to the user.</span></span>
5. <span data-ttu-id="d6249-122">O usuário inicia uma conexão com o servidor do SharePoint pela front-end da Europa.</span><span class="sxs-lookup"><span data-stu-id="d6249-122">The user initiates a connection to the SharePoint server through the Europe front door.</span></span>

<span data-ttu-id="d6249-123">Para direcionar uma solicitação de cliente ao servidor de front-end geograficamente mais próximo, os servidores DNS da Microsoft usam as consultas DNS correspondentes à solicitação de conexão inicial do cliente. </span><span class="sxs-lookup"><span data-stu-id="d6249-123">To direct a client request to the geographically nearest front door, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request.</span></span> <span data-ttu-id="d6249-124">Portanto, para a menor latência de rede mais baixa:</span><span class="sxs-lookup"><span data-stu-id="d6249-124">Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="d6249-125">Todos os escritórios da organização devem ter conexões de Internet locais para o tráfego de rede da categoria [Otimizar](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="d6249-125">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="d6249-126">Cada conexão de Internet local deve estar usando um servidor DNS local regionalmente para o tráfego de saída da Internet desse local.</span><span class="sxs-lookup"><span data-stu-id="d6249-126">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="d6249-127">Para saber mais, confira [Enviar conexões de rede de saída localmente](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span><span class="sxs-lookup"><span data-stu-id="d6249-127">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="d6249-128">Para testar o quão perto você está de um ponto de entrada da rede global da Microsoft e o quão perto você está do ponto em que a rede da sua organização se conecta ao seu ISP, use a [ferramenta de Integração de Rede do Office 365](https://connectivity.office.com/).</span><span class="sxs-lookup"><span data-stu-id="d6249-128">To test how close you are to an entry point for Microsoft’s global network and how close you are to the point where your organization network connects to your ISP, use the [Office 365 Network Onboarding tool](https://connectivity.office.com/).</span></span>

<span data-ttu-id="d6249-129">Como um ponto de verificação provisório, é possível ver os [critérios de saída](networking-exit-criteria.md#crit-networking-step2) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="d6249-129">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="d6249-130">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="d6249-130">Next step</span></span>

|||
|:-------|:-----|
|![Etapa 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="d6249-132">Evitar hairpins de rede</span><span class="sxs-lookup"><span data-stu-id="d6249-132">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
