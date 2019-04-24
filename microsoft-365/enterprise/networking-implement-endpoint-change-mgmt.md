---
title: 'Etapa 4: Planejar alterações de endereço IP e URL'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: 626d0e242c549fb16880710bbca31db0bdee9029
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291320"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a><span data-ttu-id="17df4-102">Etapa 4: Planejar alterações de endereço IP e URL</span><span class="sxs-lookup"><span data-stu-id="17df4-102">Step 4: Plan for URL and IP address changes</span></span>

<span data-ttu-id="17df4-103">*Esta etapa é opcional e aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="17df4-103">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
><span data-ttu-id="17df4-p101">Esta etapa requer a [Etapa 3](networking-configure-proxies-firewalls.md). Se você não realizou a etapa 3, prossiga para a [Etapa 5](networking-optimize-tcp-performance.md).</span><span class="sxs-lookup"><span data-stu-id="17df4-p101">This step requires [Step 3](networking-configure-proxies-firewalls.md). If you have not done Step 3, you can skip to [Step 5](networking-optimize-tcp-performance.md).</span></span>
>

<span data-ttu-id="17df4-p102">As URLs e endereços IP usados pela rede global do Microsoft 365 mudam com o passar do tempo, portanto, é importante planejar as atualizações desses pontos de extremidade. Por exemplo, talvez seja necessário reconfigurar os dispositivos de perímetro de segurança com:</span><span class="sxs-lookup"><span data-stu-id="17df4-p102">The URLs and IP addresses used by the global Microsoft 365 network change over time, so it’s important to plan for updates to these endpoints. For example, you may need to reconfigure your security perimeter devices with:</span></span>

- <span data-ttu-id="17df4-108">novas URLs para novos serviços que precisarão de um processamento livre;</span><span class="sxs-lookup"><span data-stu-id="17df4-108">New URLs for new services that will need unhindered processing</span></span>
- <span data-ttu-id="17df4-109">URLs removidas para serviços que não estão mais em uso;</span><span class="sxs-lookup"><span data-stu-id="17df4-109">Removed URLs for discontinued services</span></span>
- <span data-ttu-id="17df4-110">novos intervalos de endereços IP para novos locais e servidores da rede Microsoft na Internet;</span><span class="sxs-lookup"><span data-stu-id="17df4-110">New IP address ranges for new Microsoft network locations and servers on the Internet</span></span> 
- <span data-ttu-id="17df4-111">alterações nos intervalos de endereços IP para diferentes serviços.</span><span class="sxs-lookup"><span data-stu-id="17df4-111">Changes in IP address ranges for the different services</span></span>

<span data-ttu-id="17df4-112">Para saber mais sobre a criação de um plano de implementação para alterações nos pontos de extremidade, que inclui o recebimento de notificações de alterações, consulte as informações sobre como [ gerenciar a integração de pontos de extremidade do Office 365](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) e [gerenciar os proxies de ponto de extremidade do Office 365](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span><span class="sxs-lookup"><span data-stu-id="17df4-112">For more information about establishing an implementation plan for changes in endpoints, which includes being notified of changes, see [Managing Office 365 endpoints-Integration](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) and [Managing Office 365 endpoints-Proxies](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span></span>

<span data-ttu-id="17df4-113">Como ponto de verificação provisório, você pode consultar os [critérios de saída](networking-exit-criteria.md#crit-networking-step4) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="17df4-113">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="17df4-114">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="17df4-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="17df4-115">Otimizar o desempenho do serviço entre o cliente e o Office 365</span><span class="sxs-lookup"><span data-stu-id="17df4-115">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|
