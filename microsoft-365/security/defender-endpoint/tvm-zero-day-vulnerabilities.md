---
title: Mitigar vulnerabilidades de dia zero - Gerenciamento de Ameaças e Vulnerabilidades
description: Saiba como encontrar e reduzir vulnerabilidades de dia zero em seu ambiente por meio Gerenciamento de Ameaças e Vulnerabilidades.
keywords: Microsoft Defender para Endpoint tvm zero day vulnerabilities, tvm, threat & Gerenciamento de Vulnerabilidades, zero day, 0-day, mitigar vulnerabilidades de 0 dia, CVE vulnerável
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2c746a74899a34827e089f4c9c2f6ecc396bb69c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538766"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="c90e7-104">Mitigar vulnerabilidades de dia zero - Gerenciamento de Ameaças e Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="c90e7-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c90e7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c90e7-105">**Applies to:**</span></span>

- [<span data-ttu-id="c90e7-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c90e7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="c90e7-107">Ameaça e Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="c90e7-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="c90e7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c90e7-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="c90e7-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c90e7-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c90e7-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c90e7-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="c90e7-111">Uma vulnerabilidade de dia zero é uma vulnerabilidade publicamente divulgada para a qual nenhum patch oficial ou atualizações de segurança foram lançados.</span><span class="sxs-lookup"><span data-stu-id="c90e7-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="c90e7-112">As vulnerabilidades de dia zero geralmente têm níveis de alta gravidade e são exploradas ativamente.</span><span class="sxs-lookup"><span data-stu-id="c90e7-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="c90e7-113">A ameaça e Gerenciamento de Vulnerabilidades exibirão apenas vulnerabilidades de dia zero sobre as que ela tem informações.</span><span class="sxs-lookup"><span data-stu-id="c90e7-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="c90e7-114">Encontre informações sobre vulnerabilidades de dia zero</span><span class="sxs-lookup"><span data-stu-id="c90e7-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="c90e7-115">Depois que uma vulnerabilidade de dia zero tiver sido encontrada, as informações sobre ela serão transmitidas através das experiências a seguir no Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c90e7-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

>[!NOTE]
> <span data-ttu-id="c90e7-116">A funcionalidade de 0 dia não está disponível atualmente para produtos que não Windows (Mac, Linux); no entanto, ele será adicionado no futuro.</span><span class="sxs-lookup"><span data-stu-id="c90e7-116">0-day capability is not currently available for non-Windows products (Mac, Linux); it will, however, be added in the future.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="c90e7-117">Painel de ameaças e Gerenciamento de Vulnerabilidades de segurança</span><span class="sxs-lookup"><span data-stu-id="c90e7-117">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="c90e7-118">Procure recomendações com uma marca de dia zero no cartão "Principais recomendações de segurança".</span><span class="sxs-lookup"><span data-stu-id="c90e7-118">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![Principais recomendações com uma marca de dia zero.](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="c90e7-120">Encontre o software superior com a marca de dia zero no cartão "Software vulnerável superior".</span><span class="sxs-lookup"><span data-stu-id="c90e7-120">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![Principais softwares vulneráveis com uma marca de dia zero.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="c90e7-122">Página Pontos Fracos</span><span class="sxs-lookup"><span data-stu-id="c90e7-122">Weaknesses page</span></span>

<span data-ttu-id="c90e7-123">Procure a vulnerabilidade nomeada de dia zero juntamente com uma descrição e detalhes.</span><span class="sxs-lookup"><span data-stu-id="c90e7-123">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="c90e7-124">Se essa vulnerabilidade tiver uma CVE-ID atribuída, você verá o rótulo de dia zero ao lado do nome CVE.</span><span class="sxs-lookup"><span data-stu-id="c90e7-124">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="c90e7-125">Se essa vulnerabilidade não tiver CVE-ID atribuída, você a encontrará em um nome interno e temporário que se parece com "TVM-XXXX-XXXX".</span><span class="sxs-lookup"><span data-stu-id="c90e7-125">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="c90e7-126">O nome será atualizado depois que um CVE-ID oficial tiver sido atribuído, mas o nome interno anterior ainda será pesquisável e encontrado no painel lateral.</span><span class="sxs-lookup"><span data-stu-id="c90e7-126">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![Exemplo de dia zero para CVE-2020-17087 na página pontos fracos.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="c90e7-128">Página de inventário de software</span><span class="sxs-lookup"><span data-stu-id="c90e7-128">Software inventory page</span></span>

<span data-ttu-id="c90e7-129">Procure software com a marca de dia zero.</span><span class="sxs-lookup"><span data-stu-id="c90e7-129">Look for software with the zero-day tag.</span></span> <span data-ttu-id="c90e7-130">Filtre pela marca "zero day" para ver apenas software com vulnerabilidades de dia zero.</span><span class="sxs-lookup"><span data-stu-id="c90e7-130">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![Exemplo de dia zero de Windows Server 2016 na página de inventário de software.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="c90e7-132">Página de software</span><span class="sxs-lookup"><span data-stu-id="c90e7-132">Software page</span></span>

<span data-ttu-id="c90e7-133">Procure uma marca de dia zero para cada software afetado pela vulnerabilidade de dia zero.</span><span class="sxs-lookup"><span data-stu-id="c90e7-133">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![Exemplo de dia zero para Windows Server 2016 de software.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="c90e7-135">Página recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="c90e7-135">Security recommendations page</span></span>

<span data-ttu-id="c90e7-136">Exibir sugestões claras sobre opções de correção e mitigação, incluindo soluções alternativas se elas existirem.</span><span class="sxs-lookup"><span data-stu-id="c90e7-136">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="c90e7-137">Filtre pela marca "zero dia" para ver apenas as recomendações de segurança que abordam vulnerabilidades de dia zero.</span><span class="sxs-lookup"><span data-stu-id="c90e7-137">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="c90e7-138">Se houver software com uma vulnerabilidade de dia zero e vulnerabilidades adicionais para resolver, você terá uma recomendação sobre todas as vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="c90e7-138">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![Exemplo de dia zero Windows Server 2016 na página de recomendações de segurança.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="c90e7-140">Endereçando vulnerabilidades de dia zero</span><span class="sxs-lookup"><span data-stu-id="c90e7-140">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="c90e7-141">Vá para a página de recomendação de segurança e selecione uma recomendação com um dia zero.</span><span class="sxs-lookup"><span data-stu-id="c90e7-141">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="c90e7-142">Um sub-sub-código abrirá com informações sobre o dia zero e outras vulnerabilidades para esse software.</span><span class="sxs-lookup"><span data-stu-id="c90e7-142">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="c90e7-143">Haverá um link para opções de mitigação e soluções alternativas se elas estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c90e7-143">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="c90e7-144">As soluções alternativas podem ajudar a reduzir o risco imposto por essa vulnerabilidade de dia zero até que um patch ou atualização de segurança possa ser implantado.</span><span class="sxs-lookup"><span data-stu-id="c90e7-144">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="c90e7-145">Abra opções de correção e escolha o tipo de atenção.</span><span class="sxs-lookup"><span data-stu-id="c90e7-145">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="c90e7-146">Uma opção de correção "atenção necessária" é recomendada para as vulnerabilidades de dia zero, já que uma atualização ainda não foi lançada.</span><span class="sxs-lookup"><span data-stu-id="c90e7-146">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="c90e7-147">Você não poderá selecionar uma data de vencimento, já que não há nenhuma ação específica para executar.</span><span class="sxs-lookup"><span data-stu-id="c90e7-147">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="c90e7-148">Se houver vulnerabilidades mais antigas para esse software que você deseja remediar, você pode substituir a opção de correção "atenção necessária" e escolher "atualizar".</span><span class="sxs-lookup"><span data-stu-id="c90e7-148">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![Exemplo de flyout de dia zero Windows Server 2016 na página de recomendações de segurança.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="c90e7-150">Acompanhar atividades de correção de dia zero</span><span class="sxs-lookup"><span data-stu-id="c90e7-150">Track zero-day remediation activities</span></span>

<span data-ttu-id="c90e7-151">Vá para a página Gerenciamento de Ameaças e Vulnerabilidades [Correção para](tvm-remediation.md) exibir o item de atividade de correção.</span><span class="sxs-lookup"><span data-stu-id="c90e7-151">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="c90e7-152">Se você escolher a opção de correção "atenção necessária", não haverá barra de progresso, status de tíquete ou data de vencimento, já que não há nenhuma ação real que possamos monitorar.</span><span class="sxs-lookup"><span data-stu-id="c90e7-152">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="c90e7-153">Você pode filtrar por tipo de correção, como "atualização de software" ou "atenção necessária", para ver todos os itens de atividade na mesma categoria.</span><span class="sxs-lookup"><span data-stu-id="c90e7-153">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="c90e7-154">Corrigir vulnerabilidades de dia zero</span><span class="sxs-lookup"><span data-stu-id="c90e7-154">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="c90e7-155">Quando um patch é lançado para o dia zero, a recomendação será alterada para "Atualização" e um rótulo azul ao lado dele que diz "Nova atualização de segurança para dia zero".</span><span class="sxs-lookup"><span data-stu-id="c90e7-155">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="c90e7-156">Ela não será mais considerada como um dia zero, a marca de dia zero será removida de todas as páginas.</span><span class="sxs-lookup"><span data-stu-id="c90e7-156">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![Recomendação para "Atualizar o Microsoft Windows 10" com novo rótulo de patch.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="c90e7-158">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="c90e7-158">Related articles</span></span>

- [<span data-ttu-id="c90e7-159">Visão geral Gerenciamento de Vulnerabilidades ameaça</span><span class="sxs-lookup"><span data-stu-id="c90e7-159">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="c90e7-160">Painel</span><span class="sxs-lookup"><span data-stu-id="c90e7-160">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="c90e7-161">Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="c90e7-161">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="c90e7-162">Inventário de software</span><span class="sxs-lookup"><span data-stu-id="c90e7-162">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="c90e7-163">Vulnerabilidades na minha organização</span><span class="sxs-lookup"><span data-stu-id="c90e7-163">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)
