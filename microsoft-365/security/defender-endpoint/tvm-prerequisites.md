---
title: Pré-requisitos & permissões - Gerenciamento de Ameaças e Vulnerabilidades
description: Antes de começar a Gerenciamento de Ameaças e Vulnerabilidades, certifique-se de ter as configurações e permissões relevantes.
keywords: pré-& Gerenciamento de Vulnerabilidades permissões de ameaça, pré-requisitos de permissões Gerenciamento de Ameaças e Vulnerabilidades, pré-requisitos de permissões do Microsoft Defender para TVM de ponto de extremidade, Gerenciamento de Vulnerabilidades
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c0544665ea4e9b1ceafa645a2dcc96a224b0c242
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843945"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="a10f5-104">Pré-requisitos & permissões - Gerenciamento de Ameaças e Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="a10f5-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a10f5-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a10f5-105">**Applies to:**</span></span>

- [<span data-ttu-id="a10f5-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a10f5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a10f5-107">Ameaça e Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="a10f5-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a10f5-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a10f5-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a10f5-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="a10f5-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a10f5-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="a10f5-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="a10f5-111">Certifique-se de que seus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="a10f5-111">Ensure that your devices:</span></span>

- <span data-ttu-id="a10f5-112">Estão integradas ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a10f5-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="a10f5-113">Executar [sistemas operacionais e plataformas com suporte](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="a10f5-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="a10f5-114">Tenha as seguintes atualizações obrigatórias instaladas e implantadas em sua rede para aumentar suas taxas de detecção de avaliação de vulnerabilidade:</span><span class="sxs-lookup"><span data-stu-id="a10f5-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="a10f5-115">Lançar</span><span class="sxs-lookup"><span data-stu-id="a10f5-115">Release</span></span> | <span data-ttu-id="a10f5-116">Número e link do KB de atualização de segurança</span><span class="sxs-lookup"><span data-stu-id="a10f5-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="a10f5-117">Windows 10 Versão 1709</span><span class="sxs-lookup"><span data-stu-id="a10f5-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="a10f5-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) e [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="a10f5-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="a10f5-119">Windows 10 Versão 1803</span><span class="sxs-lookup"><span data-stu-id="a10f5-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="a10f5-120">[KB4493464](https://support.microsoft.com/help/4493464) e [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="a10f5-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="a10f5-121">Windows 10 Versão 1809</span><span class="sxs-lookup"><span data-stu-id="a10f5-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="a10f5-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="a10f5-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="a10f5-123">Windows 10 Versão 1903</span><span class="sxs-lookup"><span data-stu-id="a10f5-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="a10f5-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="a10f5-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="a10f5-125">São integradas [para](/mem/intune/fundamentals/what-is-intune) Microsoft Intune e [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) ajudar a correção de ameaças encontradas por Gerenciamento de Ameaças e Vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="a10f5-125">Are onboarded to [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="a10f5-126">Se você estiver usando o Configuration Manager, atualize seu console para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="a10f5-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="a10f5-127">**Observação**: se você tiver a conexão do Intune habilitada, você terá uma opção para criar uma tarefa de segurança do Intune ao criar uma solicitação de correção.</span><span class="sxs-lookup"><span data-stu-id="a10f5-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="a10f5-128">Essa opção não será exibida se a conexão não estiver definida.</span><span class="sxs-lookup"><span data-stu-id="a10f5-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="a10f5-129">Ter pelo menos uma recomendação de segurança que pode ser exibida na página do dispositivo</span><span class="sxs-lookup"><span data-stu-id="a10f5-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="a10f5-130">São marcados ou marcados como co-gerenciados</span><span class="sxs-lookup"><span data-stu-id="a10f5-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="a10f5-131">Opções de permissão relevantes</span><span class="sxs-lookup"><span data-stu-id="a10f5-131">Relevant permission options</span></span>

1. <span data-ttu-id="a10f5-132">Faça logoff Central de Segurança do Microsoft Defender conta usando com um administrador de segurança ou função de administrador global atribuída.</span><span class="sxs-lookup"><span data-stu-id="a10f5-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="a10f5-133">No painel de navegação, selecione Configurações > **Funções**.</span><span class="sxs-lookup"><span data-stu-id="a10f5-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="a10f5-134">Para obter mais informações, [consulte Create and manage roles for role-based access control](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="a10f5-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="a10f5-135">Exibir dados</span><span class="sxs-lookup"><span data-stu-id="a10f5-135">View data</span></span>

- <span data-ttu-id="a10f5-136">**Operações de segurança** - Exibir todos os dados de operações de segurança no portal</span><span class="sxs-lookup"><span data-stu-id="a10f5-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="a10f5-137">**Ameaça e Gerenciamento de Vulnerabilidades** - Exibir Gerenciamento de Ameaças e Vulnerabilidades dados no portal</span><span class="sxs-lookup"><span data-stu-id="a10f5-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="a10f5-138">Ações de correção ativas</span><span class="sxs-lookup"><span data-stu-id="a10f5-138">Active remediation actions</span></span>

- <span data-ttu-id="a10f5-139">**Operações de segurança** - Realizar ações de resposta, aprovar ou descartar ações pendentes de correção, gerenciar listas permitidas/bloqueadas para automação e indicadores</span><span class="sxs-lookup"><span data-stu-id="a10f5-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="a10f5-140">**Ameaça e Gerenciamento de Vulnerabilidades - Tratamento de exceções** - Criar novas exceções e gerenciar exceções ativas</span><span class="sxs-lookup"><span data-stu-id="a10f5-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="a10f5-141">**Ameaças e Gerenciamento de Vulnerabilidades - Tratamento de** correção - Enviar novas solicitações de correção, criar tíquetes e gerenciar atividades de correção existentes</span><span class="sxs-lookup"><span data-stu-id="a10f5-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="a10f5-142">Para obter mais informações, consulte [opções de permissão RBAC](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="a10f5-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="a10f5-143">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="a10f5-143">Related articles</span></span>

- [<span data-ttu-id="a10f5-144">Visão geral Gerenciamento de Vulnerabilidades ameaça</span><span class="sxs-lookup"><span data-stu-id="a10f5-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a10f5-145">Sistemas operacionais e plataformas com suporte</span><span class="sxs-lookup"><span data-stu-id="a10f5-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="a10f5-146">Atribuir valor ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="a10f5-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="a10f5-147">Painel de ameaças e Gerenciamento de Vulnerabilidades de segurança</span><span class="sxs-lookup"><span data-stu-id="a10f5-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

