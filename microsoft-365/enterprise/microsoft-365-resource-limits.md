---
title: Limites de recursos do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Neste artigo, você pode encontrar informações sobre os limites de recursos para os vários aplicativos no Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6053740d41b02461432243c8527391a4f8ae22ea
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687343"
---
# <a name="resource-limits"></a><span data-ttu-id="39c6c-103">Limites de recurso</span><span class="sxs-lookup"><span data-stu-id="39c6c-103">Resource Limits</span></span>

<span data-ttu-id="39c6c-104">Os limites de recursos são impostos usando cotas (limites) e limitação.</span><span class="sxs-lookup"><span data-stu-id="39c6c-104">Resource limits are enforced using quotas (limits) and throttling.</span></span> <span data-ttu-id="39c6c-105">O Azure Active Directory (Azure AD) e os serviços individuais da Microsoft 365 usam ambos.</span><span class="sxs-lookup"><span data-stu-id="39c6c-105">Azure Active Directory (Azure AD) and the individual Microsoft 365 services use both.</span></span> <span data-ttu-id="39c6c-106">Os limites são específicos de serviço e mudam com o tempo à medida que novos recursos são adicionados.</span><span class="sxs-lookup"><span data-stu-id="39c6c-106">Limits are service-specific and change over time as new capabilities are added.</span></span> <span data-ttu-id="39c6c-107">Para obter detalhes sobre os limites atuais para os vários serviços, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="39c6c-107">For details on the current limits for the various services, see the following topics:</span></span>

- [<span data-ttu-id="39c6c-108">Limites e restrições do serviço do Azure AD</span><span class="sxs-lookup"><span data-stu-id="39c6c-108">Azure AD service limits and restrictions</span></span>](https://docs.microsoft.com/azure/azure-resource-manager/management/azure-subscription-service-limits)
- [<span data-ttu-id="39c6c-109">Limites do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="39c6c-109">Exchange Online Limits</span></span>](https://technet.microsoft.com/library/exchange-online-limits.aspx)
- [<span data-ttu-id="39c6c-110">Limites do Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="39c6c-110">Exchange Online Protection Limits</span></span>](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx)
- [<span data-ttu-id="39c6c-111">Limites e limites de software do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="39c6c-111">SharePoint Online software boundaries and limits</span></span>](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [<span data-ttu-id="39c6c-112">Limites do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="39c6c-112">Skype for Business Limits</span></span>](https://technet.microsoft.com/library/skype-for-business-online-limits.aspx)
- [<span data-ttu-id="39c6c-113">API REST do Yammer e limites de taxa</span><span class="sxs-lookup"><span data-stu-id="39c6c-113">Yammer REST API and Rate Limits</span></span>](https://developer.yammer.com/docs/rest-api-rate-limits)
- [<span data-ttu-id="39c6c-114">Limites de tamanho de arquivo no Sway</span><span class="sxs-lookup"><span data-stu-id="39c6c-114">File Size Limits in Sway</span></span>](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

<span data-ttu-id="39c6c-115">Além desses limites, vários mecanismos de limitação são usados no Azure AD e no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="39c6c-115">In addition to these limits, several throttling mechanisms are used throughout Azure AD and Microsoft 365.</span></span> <span data-ttu-id="39c6c-116">A limitação do serviço é especialmente importante, Considerando que os recursos de rede nos datacenters da Microsoft são otimizados para o amplo conjunto de clientes que usam os serviços.</span><span class="sxs-lookup"><span data-stu-id="39c6c-116">Throttling within the service is especially important, given that network resources in Microsoft's datacenters are optimized for the broad set of customers that use the services.</span></span> <span data-ttu-id="39c6c-117">Os mecanismos de limitação incluem:</span><span class="sxs-lookup"><span data-stu-id="39c6c-117">Throttling mechanisms include:</span></span>

- <span data-ttu-id="39c6c-118">O Azure AD e o Microsoft 365 recurso de limitação de nível de usuário, que limitam o número de transações ou chamadas simultâneas (por script ou código) que podem ser realizadas por um único usuário.</span><span class="sxs-lookup"><span data-stu-id="39c6c-118">Azure AD and Microsoft 365 feature user-level throttling, which limit the number of transactions or concurrent calls (by script or code) that can be performed by a single user.</span></span>
- <span data-ttu-id="39c6c-119">Uma política padrão de limitação do PowerShell é atribuída a cada locatário na criação de locatário.</span><span class="sxs-lookup"><span data-stu-id="39c6c-119">A default PowerShell throttling policy is assigned to each tenant at tenant creation.</span></span> <span data-ttu-id="39c6c-120">Essas configurações afetam outros itens, como o número máximo de sessões simultâneas do PowerShell que podem ser abertas por um único administrador.</span><span class="sxs-lookup"><span data-stu-id="39c6c-120">These settings affect other items, such as the maximum number of simultaneous PowerShell sessions that can be opened by a single administrator.</span></span>
- <span data-ttu-id="39c6c-121">Cada cliente do Exchange Online tem uma política de serviços Web do Exchange (EWS) padrão ajustada para operações do cliente EWS e limitação que se aplica a todos os clientes do Outlook.</span><span class="sxs-lookup"><span data-stu-id="39c6c-121">Each Exchange Online customer has a default Exchange Web Services (EWS) policy that is tuned for EWS client operations, and throttling that applies to all Outlook clients.</span></span>
