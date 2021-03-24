---
title: Pré-requisitos & permissões - gerenciamento de ameaças e vulnerabilidades
description: Antes de começar a usar o gerenciamento de ameaças e vulnerabilidades, certifique-se de ter as configurações e permissões relevantes.
keywords: pré-& permissões de gerenciamento de vulnerabilidade, permissões de gerenciamento de ameaças e vulnerabilidades pré-requisitos, pré-requisitos de permissões de TVM MDATP, gerenciamento de vulnerabilidades
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ca095a7a65a114182d736176840fdd4e651a8646
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054046"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="2495e-104">Pré-requisitos & permissões - gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="2495e-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2495e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2495e-105">**Applies to:**</span></span>

- [<span data-ttu-id="2495e-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2495e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="2495e-107">Gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="2495e-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="2495e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2495e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2495e-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="2495e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2495e-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="2495e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="2495e-111">Certifique-se de que seus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="2495e-111">Ensure that your devices:</span></span>

- <span data-ttu-id="2495e-112">Estão integradas ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2495e-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="2495e-113">Executar [sistemas operacionais e plataformas com suporte](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="2495e-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="2495e-114">Tenha as seguintes atualizações obrigatórias instaladas e implantadas em sua rede para aumentar suas taxas de detecção de avaliação de vulnerabilidade:</span><span class="sxs-lookup"><span data-stu-id="2495e-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="2495e-115">Liberar</span><span class="sxs-lookup"><span data-stu-id="2495e-115">Release</span></span> | <span data-ttu-id="2495e-116">Número e link do KB de atualização de segurança</span><span class="sxs-lookup"><span data-stu-id="2495e-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="2495e-117">Windows 10 Versão 1709</span><span class="sxs-lookup"><span data-stu-id="2495e-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="2495e-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) e [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="2495e-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="2495e-119">Windows 10 Versão 1803</span><span class="sxs-lookup"><span data-stu-id="2495e-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="2495e-120">[KB4493464](https://support.microsoft.com/help/4493464) e [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="2495e-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="2495e-121">Windows 10 Versão 1809</span><span class="sxs-lookup"><span data-stu-id="2495e-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="2495e-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="2495e-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="2495e-123">Windows 10 Versão 1903</span><span class="sxs-lookup"><span data-stu-id="2495e-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="2495e-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="2495e-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="2495e-125">Estão integradas ao [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) e ao  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) para ajudar a correção de ameaças encontradas pelo gerenciamento de ameaças e vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="2495e-125">Are onboarded to [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="2495e-126">Se você estiver usando o Configuration Manager, atualize seu console para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="2495e-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="2495e-127">**Observação**: se você tiver a conexão do Intune habilitada, você terá uma opção para criar uma tarefa de segurança do Intune ao criar uma solicitação de correção.</span><span class="sxs-lookup"><span data-stu-id="2495e-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="2495e-128">Essa opção não será exibida se a conexão não estiver definida.</span><span class="sxs-lookup"><span data-stu-id="2495e-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="2495e-129">Ter pelo menos uma recomendação de segurança que pode ser exibida na página do dispositivo</span><span class="sxs-lookup"><span data-stu-id="2495e-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="2495e-130">São marcados ou marcados como co-gerenciados</span><span class="sxs-lookup"><span data-stu-id="2495e-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="2495e-131">Opções de permissão relevantes</span><span class="sxs-lookup"><span data-stu-id="2495e-131">Relevant permission options</span></span>

1. <span data-ttu-id="2495e-132">Faça logoff no Centro de Segurança do Microsoft Defender usando conta com um administrador de segurança ou função de administrador global atribuída.</span><span class="sxs-lookup"><span data-stu-id="2495e-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="2495e-133">No painel de navegação, selecione **Configurações > Funções**.</span><span class="sxs-lookup"><span data-stu-id="2495e-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="2495e-134">Para obter mais informações, [consulte Create and manage roles for role-based access control](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="2495e-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="2495e-135">Exibir dados</span><span class="sxs-lookup"><span data-stu-id="2495e-135">View data</span></span>

- <span data-ttu-id="2495e-136">**Operações de segurança** - Exibir todos os dados de operações de segurança no portal</span><span class="sxs-lookup"><span data-stu-id="2495e-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="2495e-137">**Gerenciamento de ameaças e vulnerabilidades** - Exibir dados de gerenciamento de ameaças e vulnerabilidades no portal</span><span class="sxs-lookup"><span data-stu-id="2495e-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="2495e-138">Ações de correção ativas</span><span class="sxs-lookup"><span data-stu-id="2495e-138">Active remediation actions</span></span>

- <span data-ttu-id="2495e-139">**Operações de segurança** - Realizar ações de resposta, aprovar ou descartar ações pendentes de correção, gerenciar listas permitidas/bloqueadas para automação e indicadores</span><span class="sxs-lookup"><span data-stu-id="2495e-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="2495e-140">**Gerenciamento de ameaças e vulnerabilidades - Tratamento de exceções** - Criar novas exceções e gerenciar exceções ativas</span><span class="sxs-lookup"><span data-stu-id="2495e-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="2495e-141">**Gerenciamento de ameaças e vulnerabilidades - Tratamento** de correção - Enviar novas solicitações de correção, criar tíquetes e gerenciar atividades de correção existentes</span><span class="sxs-lookup"><span data-stu-id="2495e-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="2495e-142">Para obter mais informações, consulte [opções de permissão RBAC](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="2495e-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="2495e-143">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="2495e-143">Related articles</span></span>

- [<span data-ttu-id="2495e-144">Visão geral do gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="2495e-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="2495e-145">Sistemas operacionais e plataformas com suporte</span><span class="sxs-lookup"><span data-stu-id="2495e-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="2495e-146">Atribuir valor de dispositivo</span><span class="sxs-lookup"><span data-stu-id="2495e-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="2495e-147">Painel de gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="2495e-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

