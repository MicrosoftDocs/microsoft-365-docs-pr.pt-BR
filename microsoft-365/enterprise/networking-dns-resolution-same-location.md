---
title: 'Etapa 2: Configurar conexões locais com a Internet para cada escritório'
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
description: Entender e configurar a resolução de DNS para obter um melhor desempenho.
ms.openlocfilehash: 9ccd5c477b4aeda8e7dcf482cc09c8a357f19f40
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864696"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a><span data-ttu-id="f4962-103">Etapa 2: Configurar conexões locais com a Internet para cada escritório</span><span class="sxs-lookup"><span data-stu-id="f4962-103">Step 2: Configure local Internet connections for each office</span></span>

<span data-ttu-id="f4962-104">*Esta etapa é obrigatória e aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="f4962-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="f4962-p101">Na Etapa 2, você verifica se cada um dos escritórios tem conexões de Internet locais e usa servidores DNS locais. Esses dois elementos são necessários para reduzir a latência da conexão e garantir que os computadores clientes locais façam conexões com o ponto de entrada mais próximo dos serviços baseados em nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4962-p101">In Step 2, you ensure that each of your offices have local Internet connections and use local DNS servers. Both of these elements are required to reduce connection latency and ensure that on-premises client computers make connections to the nearest point of entry to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="f4962-p102">Em redes tradicionais para grandes organizações, o tráfego da Internet percorre o backbone da rede até uma conexão central com a Internet. Isso não funciona bem para otimizar o desempenho para uma infraestrutura de software como serviço (SaaS) globalmente distribuída, que inclui os produtos Office 365 e Enterprise Mobility + Security (EMS) no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4962-p102">In traditional networks for large organizations, Internet traffic travels across the network backbone to a central Internet connection. This does not work well for optimizing performance to a globally distributed Software-as-a-Service (SaaS) infrastructure, which includes the Office 365 and Enterprise Mobility + Security (EMS) products in Microsoft 365.</span></span>

<span data-ttu-id="f4962-p103">A Rede Global da Microsoft inclui servidores de front-end para o conjunto de serviços em nuvem do Microsoft 365 em todo o mundo. Para obter o melhor desempenho, os clientes locais devem acessar um servidor de front-end que esteja geograficamente mais próximo deles, em vez de enviar o tráfego por um backbone de rede e ao servidor de front-end mais próximo da conexão central com a Internet da organização.</span><span class="sxs-lookup"><span data-stu-id="f4962-p103">The Microsoft Global Network includes front end servers to the set of cloud services for Microsoft 365 all over the world. For the best performance, on-premises clients should access a front-end server that is geographically closest to them, rather than sending the traffic over a network backbone and to the front-end server that is closest to the organization’s central Internet connection.</span></span>

<span data-ttu-id="f4962-p104">Para direcionar uma solicitação de cliente ao servidor de front-end geograficamente mais próximo, os servidores DNS da Microsoft usam as consultas DNS correspondentes à solicitação de conexão inicial do cliente. Portanto, para a menor latência de rede mais baixa:</span><span class="sxs-lookup"><span data-stu-id="f4962-p104">To direct a client request to the geographically nearest front-end server, Microsoft’s DNS servers use the DNS queries corresponding the client’s initial connection request. Therefore, for the lowest network latency:</span></span>

- <span data-ttu-id="f4962-113">Todos os escritórios da organização devem ter conexões de Internet locais para o tráfego de rede da categoria [Otimizar](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="f4962-113">All offices of your organization should have local Internet connections for [Optimize](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories) category network traffic.</span></span>
- <span data-ttu-id="f4962-114">Cada conexão de Internet local deve estar usando um servidor DNS local regionalmente para o tráfego de saída da Internet desse local.</span><span class="sxs-lookup"><span data-stu-id="f4962-114">Each local Internet connection should be using a regionally local DNS server for outbound Internet traffic from that location.</span></span>

<span data-ttu-id="f4962-115">Para saber mais, confira [Enviar conexões de rede de saída localmente](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span><span class="sxs-lookup"><span data-stu-id="f4962-115">For more information, see [Egress network connections locally](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally).</span></span> 

<span data-ttu-id="f4962-116">Como um ponto de verificação provisório, é possível ver os [critérios de saída](networking-exit-criteria.md#crit-networking-step2) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f4962-116">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step2) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f4962-117">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="f4962-117">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="f4962-118">Evitar hairpins de rede</span><span class="sxs-lookup"><span data-stu-id="f4962-118">Avoid network hairpins</span></span>](networking-avoid-network-hairpins.md)|
