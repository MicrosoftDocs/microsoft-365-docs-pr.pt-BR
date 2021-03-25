---
title: Acessar o portal do cliente do Centro de Segurança do Microsoft Defender MSSP
description: Acessar o portal do cliente do Centro de Segurança do Microsoft Defender MSSP
keywords: provedor de serviços de segurança gerenciado, mssp, configurar, integração
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164852"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a><span data-ttu-id="76741-104">Acessar o portal do cliente do Centro de Segurança do Microsoft Defender MSSP</span><span class="sxs-lookup"><span data-stu-id="76741-104">Access the Microsoft Defender Security Center MSSP customer portal</span></span>

<span data-ttu-id="76741-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="76741-105">**Applies to:**</span></span>
- [<span data-ttu-id="76741-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="76741-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="76741-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76741-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="76741-108">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="76741-108">**Applies to:**</span></span>

- [<span data-ttu-id="76741-109">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="76741-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="76741-110">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="76741-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="76741-111">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="76741-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
><span data-ttu-id="76741-112">Esses conjunto de etapas são direcionados para o MSSP.</span><span class="sxs-lookup"><span data-stu-id="76741-112">These set of steps are directed towards the MSSP.</span></span> 

<span data-ttu-id="76741-113">Por padrão, os clientes MSSP acessam seu locatário do Centro de Segurança do Microsoft Defender por meio da seguinte URL: `https://securitycenter.windows.com` .</span><span class="sxs-lookup"><span data-stu-id="76741-113">By default, MSSP customers access their Microsoft Defender Security Center tenant through the following URL: `https://securitycenter.windows.com`.</span></span>
 

<span data-ttu-id="76741-114">No entanto, os MSSPs precisarão usar uma URL específica do locatário no seguinte formato: para acessar  `https://securitycenter.windows.com?tid=customer_tenant_id` o portal do cliente MSSP.</span><span class="sxs-lookup"><span data-stu-id="76741-114">MSSPs however, will need to use a tenant-specific URL in the following format:  `https://securitycenter.windows.com?tid=customer_tenant_id` to access the MSSP customer portal.</span></span> 

<span data-ttu-id="76741-115">Em geral, os MSSPs precisarão ser adicionados a cada um dos Azure AD do cliente MSSP que pretendem gerenciar.</span><span class="sxs-lookup"><span data-stu-id="76741-115">In general, MSSPs will need to be added to each of the MSSP customer's Azure AD that they intend to manage.</span></span>


<span data-ttu-id="76741-116">Use as etapas a seguir para obter a ID do locatário do cliente MSSP e, em seguida, usar a ID para acessar a URL específica do locatário:</span><span class="sxs-lookup"><span data-stu-id="76741-116">Use the following steps to obtain the MSSP customer tenant ID and then use the ID to access the tenant-specific URL:</span></span>

1. <span data-ttu-id="76741-117">Como um MSSP, faça logon no Azure AD com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="76741-117">As an MSSP, login to Azure AD with your credentials.</span></span> 

2. <span data-ttu-id="76741-118">Alternar o diretório para o locatário do cliente MSSP.</span><span class="sxs-lookup"><span data-stu-id="76741-118">Switch directory to the MSSP customer's tenant.</span></span>

3.  <span data-ttu-id="76741-119">Selecione **Propriedades do Azure Active Directory >**.</span><span class="sxs-lookup"><span data-stu-id="76741-119">Select **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="76741-120">Você encontrará a ID do locatário no campo ID do Diretório.</span><span class="sxs-lookup"><span data-stu-id="76741-120">You'll find the tenant ID in the Directory ID field.</span></span> 

4. <span data-ttu-id="76741-121">Acesse o portal do cliente MSSP substituindo `customer_tenant_id` o valor na seguinte URL: `https://securitycenter.windows.com?tid=customer_tenant_id` .</span><span class="sxs-lookup"><span data-stu-id="76741-121">Access the MSSP customer portal by replacing the `customer_tenant_id` value in the following URL: `https://securitycenter.windows.com?tid=customer_tenant_id`.</span></span>


## <a name="related-topics"></a><span data-ttu-id="76741-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="76741-122">Related topics</span></span>
- [<span data-ttu-id="76741-123">Conceder acesso MSSP ao portal</span><span class="sxs-lookup"><span data-stu-id="76741-123">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="76741-124">Configurar notificações de alerta</span><span class="sxs-lookup"><span data-stu-id="76741-124">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="76741-125">Buscar alertas do locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="76741-125">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
