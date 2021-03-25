---
title: Mitigar vulnerabilidades de dia zero - gerenciamento de ameaças e vulnerabilidades
description: Saiba como encontrar e reduzir vulnerabilidades de dia zero em seu ambiente por meio do gerenciamento de ameaças e vulnerabilidades.
keywords: Mdatp tvm zero day vulnerabilities, tvm, threat & vulnerability management, zero day, 0-day, mitigar vulnerabilidades de 0 dia, CVE vulnerável
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b2092f24e4ee3e35918fbdc54b68570ef29fd08e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054447"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="88a52-104">Mitigar vulnerabilidades de dia zero - gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="88a52-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="88a52-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="88a52-105">**Applies to:**</span></span>

- [<span data-ttu-id="88a52-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="88a52-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="88a52-107">Gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="88a52-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="88a52-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88a52-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="88a52-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="88a52-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="88a52-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="88a52-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="88a52-111">Uma vulnerabilidade de dia zero é uma vulnerabilidade publicamente divulgada para a qual nenhum patch oficial ou atualizações de segurança foram lançados.</span><span class="sxs-lookup"><span data-stu-id="88a52-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="88a52-112">As vulnerabilidades de dia zero geralmente têm níveis de alta gravidade e são exploradas ativamente.</span><span class="sxs-lookup"><span data-stu-id="88a52-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="88a52-113">O gerenciamento de ameaças e vulnerabilidades exibirá apenas vulnerabilidades de dia zero sobre as que ele tem informações.</span><span class="sxs-lookup"><span data-stu-id="88a52-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="88a52-114">Encontre informações sobre vulnerabilidades de dia zero</span><span class="sxs-lookup"><span data-stu-id="88a52-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="88a52-115">Depois que uma vulnerabilidade de dia zero tiver sido encontrada, as informações sobre ela serão transmitidas através das experiências a seguir no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="88a52-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="88a52-116">Painel de gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="88a52-116">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="88a52-117">Procure recomendações com uma marca de dia zero no cartão "Principais recomendações de segurança".</span><span class="sxs-lookup"><span data-stu-id="88a52-117">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![Principais recomendações com uma marca de dia zero.](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="88a52-119">Encontre o software superior com a marca de dia zero no cartão "Software vulnerável superior".</span><span class="sxs-lookup"><span data-stu-id="88a52-119">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![Principais softwares vulneráveis com uma marca de dia zero.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="88a52-121">Página Pontos Fracos</span><span class="sxs-lookup"><span data-stu-id="88a52-121">Weaknesses page</span></span>

<span data-ttu-id="88a52-122">Procure a vulnerabilidade nomeada de dia zero juntamente com uma descrição e detalhes.</span><span class="sxs-lookup"><span data-stu-id="88a52-122">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="88a52-123">Se essa vulnerabilidade tiver uma CVE-ID atribuída, você verá o rótulo de dia zero ao lado do nome CVE.</span><span class="sxs-lookup"><span data-stu-id="88a52-123">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="88a52-124">Se essa vulnerabilidade não tiver CVE-ID atribuída, você a encontrará em um nome interno e temporário que se parece com "TVM-XXXX-XXXX".</span><span class="sxs-lookup"><span data-stu-id="88a52-124">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="88a52-125">O nome será atualizado depois que um CVE-ID oficial tiver sido atribuído, mas o nome interno anterior ainda será pesquisável e encontrado no painel lateral.</span><span class="sxs-lookup"><span data-stu-id="88a52-125">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![Exemplo de dia zero para CVE-2020-17087 na página pontos fracos.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="88a52-127">Página de inventário de software</span><span class="sxs-lookup"><span data-stu-id="88a52-127">Software inventory page</span></span>

<span data-ttu-id="88a52-128">Procure software com a marca de dia zero.</span><span class="sxs-lookup"><span data-stu-id="88a52-128">Look for software with the zero-day tag.</span></span> <span data-ttu-id="88a52-129">Filtre pela marca "zero day" para ver apenas software com vulnerabilidades de dia zero.</span><span class="sxs-lookup"><span data-stu-id="88a52-129">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![Exemplo de dia zero do Windows Server 2016 na página de inventário de software.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="88a52-131">Página de software</span><span class="sxs-lookup"><span data-stu-id="88a52-131">Software page</span></span>

<span data-ttu-id="88a52-132">Procure uma marca de dia zero para cada software afetado pela vulnerabilidade de dia zero.</span><span class="sxs-lookup"><span data-stu-id="88a52-132">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![Exemplo de dia zero para a página de software do Windows Server 2016.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="88a52-134">Página recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="88a52-134">Security recommendations page</span></span>

<span data-ttu-id="88a52-135">Exibir sugestões claras sobre opções de correção e mitigação, incluindo soluções alternativas se elas existirem.</span><span class="sxs-lookup"><span data-stu-id="88a52-135">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="88a52-136">Filtre pela marca "zero dia" para ver apenas as recomendações de segurança que abordam vulnerabilidades de dia zero.</span><span class="sxs-lookup"><span data-stu-id="88a52-136">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="88a52-137">Se houver software com uma vulnerabilidade de dia zero e vulnerabilidades adicionais para resolver, você terá uma recomendação sobre todas as vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="88a52-137">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![Exemplo de dia zero do Windows Server 2016 na página de recomendações de segurança.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="88a52-139">Endereçando vulnerabilidades de dia zero</span><span class="sxs-lookup"><span data-stu-id="88a52-139">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="88a52-140">Vá para a página de recomendação de segurança e selecione uma recomendação com um dia zero.</span><span class="sxs-lookup"><span data-stu-id="88a52-140">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="88a52-141">Um sub-sub-código abrirá com informações sobre o dia zero e outras vulnerabilidades para esse software.</span><span class="sxs-lookup"><span data-stu-id="88a52-141">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="88a52-142">Haverá um link para opções de mitigação e soluções alternativas se elas estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="88a52-142">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="88a52-143">As soluções alternativas podem ajudar a reduzir o risco imposto por essa vulnerabilidade de dia zero até que um patch ou atualização de segurança possa ser implantado.</span><span class="sxs-lookup"><span data-stu-id="88a52-143">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="88a52-144">Abra opções de correção e escolha o tipo de atenção.</span><span class="sxs-lookup"><span data-stu-id="88a52-144">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="88a52-145">Uma opção de correção "atenção necessária" é recomendada para as vulnerabilidades de dia zero, já que uma atualização ainda não foi lançada.</span><span class="sxs-lookup"><span data-stu-id="88a52-145">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="88a52-146">Você não poderá selecionar uma data de vencimento, já que não há nenhuma ação específica para executar.</span><span class="sxs-lookup"><span data-stu-id="88a52-146">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="88a52-147">Se houver vulnerabilidades mais antigas para esse software que você deseja remediar, você pode substituir a opção de correção "atenção necessária" e escolher "atualizar".</span><span class="sxs-lookup"><span data-stu-id="88a52-147">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![Exemplo de flyout de dia zero do Windows Server 2016 na página de recomendações de segurança.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="88a52-149">Acompanhar atividades de correção de dia zero</span><span class="sxs-lookup"><span data-stu-id="88a52-149">Track zero-day remediation activities</span></span>

<span data-ttu-id="88a52-150">Vá para a página Gerenciamento de ameaças e [vulnerabilidades Correção](tvm-remediation.md) para exibir o item de atividade de correção.</span><span class="sxs-lookup"><span data-stu-id="88a52-150">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="88a52-151">Se você escolher a opção de correção "atenção necessária", não haverá barra de progresso, status de tíquete ou data de vencimento, já que não há nenhuma ação real que possamos monitorar.</span><span class="sxs-lookup"><span data-stu-id="88a52-151">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="88a52-152">Você pode filtrar por tipo de correção, como "atualização de software" ou "atenção necessária", para ver todos os itens de atividade na mesma categoria.</span><span class="sxs-lookup"><span data-stu-id="88a52-152">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="88a52-153">Corrigir vulnerabilidades de dia zero</span><span class="sxs-lookup"><span data-stu-id="88a52-153">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="88a52-154">Quando um patch é lançado para o dia zero, a recomendação será alterada para "Atualização" e um rótulo azul ao lado dele que diz "Nova atualização de segurança para dia zero".</span><span class="sxs-lookup"><span data-stu-id="88a52-154">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="88a52-155">Ela não será mais considerada como um dia zero, a marca de dia zero será removida de todas as páginas.</span><span class="sxs-lookup"><span data-stu-id="88a52-155">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![Recomendação para "Atualizar o Microsoft Windows 10" com novo rótulo de patch.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="88a52-157">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="88a52-157">Related articles</span></span>

- [<span data-ttu-id="88a52-158">Visão geral do gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="88a52-158">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="88a52-159">Painel</span><span class="sxs-lookup"><span data-stu-id="88a52-159">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="88a52-160">Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="88a52-160">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="88a52-161">Inventário de software</span><span class="sxs-lookup"><span data-stu-id="88a52-161">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="88a52-162">Vulnerabilidades na minha organização</span><span class="sxs-lookup"><span data-stu-id="88a52-162">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)