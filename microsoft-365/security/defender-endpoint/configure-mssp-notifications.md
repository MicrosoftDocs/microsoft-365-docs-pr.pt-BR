---
title: Configurar notificações de alerta enviadas para MSSPs
description: Configurar notificações de alerta enviadas para MSSPs
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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166048"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a><span data-ttu-id="9ee35-104">Configurar notificações de alerta enviadas para MSSPs</span><span class="sxs-lookup"><span data-stu-id="9ee35-104">Configure alert notifications that are sent to MSSPs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9ee35-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9ee35-105">**Applies to:**</span></span>
- [<span data-ttu-id="9ee35-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9ee35-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9ee35-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ee35-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9ee35-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="9ee35-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9ee35-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="9ee35-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
><span data-ttu-id="9ee35-110">Esta etapa pode ser feita pelo cliente MSSP ou pelo MSSP.</span><span class="sxs-lookup"><span data-stu-id="9ee35-110">This step can be done by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="9ee35-111">Os MSSPs devem ter as permissões apropriadas para configurá-lo em nome do cliente MSSP.</span><span class="sxs-lookup"><span data-stu-id="9ee35-111">MSSPs must be granted the appropriate permissions to configure this on behalf of the MSSP customer.</span></span>

<span data-ttu-id="9ee35-112">Depois que o acesso ao portal é concedido, as regras de notificação de alerta podem ser criadas para que os emails sejam enviados aos MSSPs quando os alertas associados ao locatário são criados e as condições definidas são atendidas.</span><span class="sxs-lookup"><span data-stu-id="9ee35-112">After access the portal is granted, alert notification rules can to be created so that emails are sent to MSSPs when alerts associated with the tenant are created and set conditions are met.</span></span>

 
<span data-ttu-id="9ee35-113">Para obter mais informações, [consulte Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).</span><span class="sxs-lookup"><span data-stu-id="9ee35-113">For more information, see [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).</span></span>
 

<span data-ttu-id="9ee35-114">Essas caixas de seleção devem ser verificadas:</span><span class="sxs-lookup"><span data-stu-id="9ee35-114">These check boxes must be checked:</span></span>
- <span data-ttu-id="9ee35-115">**Incluir nome da organização** - O nome do cliente será adicionado às notificações de email</span><span class="sxs-lookup"><span data-stu-id="9ee35-115">**Include organization name** - The customer name will be added to email notifications</span></span>
- <span data-ttu-id="9ee35-116">**Incluir link de portal** específico do locatário - A URL do link de alerta terá parâmetro específico de locatário (tid=target_tenant_id) que permite acesso direto ao portal de locatários de destino</span><span class="sxs-lookup"><span data-stu-id="9ee35-116">**Include tenant-specific portal link** - Alert link URL will have tenant specific parameter (tid=target_tenant_id) that allows direct access to target tenant portal</span></span>


## <a name="related-topics"></a><span data-ttu-id="9ee35-117">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9ee35-117">Related topics</span></span>
- [<span data-ttu-id="9ee35-118">Conceder acesso MSSP ao portal</span><span class="sxs-lookup"><span data-stu-id="9ee35-118">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="9ee35-119">Acessar o portal do cliente MSSP</span><span class="sxs-lookup"><span data-stu-id="9ee35-119">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="9ee35-120">Buscar alertas do locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="9ee35-120">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
