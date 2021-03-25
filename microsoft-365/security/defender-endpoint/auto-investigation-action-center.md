---
title: Visite o Centro de Ações para ver ações de correção
description: Use o centro de ações para exibir detalhes e resultados após uma investigação automatizada
keywords: action, center, autoir, automated, investigation, response, remediation
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: 6caa1cfe08a20aa824d85966c104a25988b8be53
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165352"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a><span data-ttu-id="65672-104">Visite o Centro de Ações para ver ações de correção</span><span class="sxs-lookup"><span data-stu-id="65672-104">Visit the Action center to see remediation actions</span></span>

<span data-ttu-id="65672-105">Durante e após uma investigação automatizada, as ações de correção para detecções de ameaças são identificadas.</span><span class="sxs-lookup"><span data-stu-id="65672-105">During and after an automated investigation, remediation actions for threat detections are identified.</span></span> <span data-ttu-id="65672-106">Dependendo da ameaça específica e de como o [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) está configurado para sua organização, algumas ações de correção são tomadas automaticamente e outras exigem aprovação.</span><span class="sxs-lookup"><span data-stu-id="65672-106">Depending on the particular threat and how [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) is configured for your organization, some remediation actions are taken automatically, and others require approval.</span></span> <span data-ttu-id="65672-107">Se você faz parte da equipe de operações de segurança da [](manage-auto-investigation.md#remediation-actions) sua organização, pode exibir ações pendentes e concluídas de correção no **Centro de Ações.**</span><span class="sxs-lookup"><span data-stu-id="65672-107">If you're part of your organization's security operations team, you can view pending and completed [remediation actions](manage-auto-investigation.md#remediation-actions) in the **Action center**.</span></span> 


<span data-ttu-id="65672-108">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="65672-108">**Applies to:**</span></span>
- [<span data-ttu-id="65672-109">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="65672-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="65672-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65672-110">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a><span data-ttu-id="65672-111">(NEW!) Um centro de ação unificado</span><span class="sxs-lookup"><span data-stu-id="65672-111">(NEW!) A unified Action center</span></span>


<span data-ttu-id="65672-112">Temos o prazer de anunciar um novo Centro de Ações unificado ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )!</span><span class="sxs-lookup"><span data-stu-id="65672-112">We are pleased to announce a new, unified Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center))!</span></span>

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Centro de ações no Centro de segurança do Microsoft 365":::

<span data-ttu-id="65672-114">A tabela a seguir compara o novo centro de ações unificado com o centro de ações anterior.</span><span class="sxs-lookup"><span data-stu-id="65672-114">The following table compares the new, unified Action center to the previous Action center.</span></span>

|<span data-ttu-id="65672-115">O novo centro de ações unificado</span><span class="sxs-lookup"><span data-stu-id="65672-115">The new, unified Action center</span></span>  |<span data-ttu-id="65672-116">O centro de ações anterior</span><span class="sxs-lookup"><span data-stu-id="65672-116">The previous Action center</span></span>  |
|---------|---------|
|<span data-ttu-id="65672-117">Lista ações pendentes e concluídas para dispositivos e emails em um único local</span><span class="sxs-lookup"><span data-stu-id="65672-117">Lists pending and completed actions for devices and email in one location</span></span> <br/><span data-ttu-id="65672-118">([Microsoft Defender para Ponto de Extremidade mais](microsoft-defender-advanced-threat-protection.md) Microsoft Defender para Office [365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp))</span><span class="sxs-lookup"><span data-stu-id="65672-118">([Microsoft Defender for Endpoint](microsoft-defender-advanced-threat-protection.md) plus [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp))</span></span>|<span data-ttu-id="65672-119">Lista ações pendentes e concluídas para dispositivos</span><span class="sxs-lookup"><span data-stu-id="65672-119">Lists pending and completed actions for devices</span></span> <br/> <span data-ttu-id="65672-120">([Microsoft Defender somente para Ponto de](microsoft-defender-advanced-threat-protection.md) Extremidade)</span><span class="sxs-lookup"><span data-stu-id="65672-120">([Microsoft Defender for Endpoint](microsoft-defender-advanced-threat-protection.md) only)</span></span>   |
|<span data-ttu-id="65672-121">Está localizado em:</span><span class="sxs-lookup"><span data-stu-id="65672-121">Is located at:</span></span><br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |<span data-ttu-id="65672-122">Está localizado em:</span><span class="sxs-lookup"><span data-stu-id="65672-122">Is located at:</span></span><br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| <span data-ttu-id="65672-123">No centro de segurança do Microsoft 365, escolha **Centro de ações**.</span><span class="sxs-lookup"><span data-stu-id="65672-123">In the Microsoft 365 security center, choose **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Navegando até o Centro de Ações no centro de segurança do Microsoft 365"::: | <span data-ttu-id="65672-125">No Centro de Segurança do Microsoft Defender, escolha **Centro de ações** de  >  **investigações automatizadas.**</span><span class="sxs-lookup"><span data-stu-id="65672-125">In the Microsoft Defender Security Center, choose **Automated investigations** > **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Navegando até o Centro de Ações do Centro de Segurança do Microsoft Defender":::  |

<span data-ttu-id="65672-127">O centro de ações unificado reúne ações de correção no Defender para Ponto de Extremidade e no Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="65672-127">The unified Action center brings together remediation actions across Defender for Endpoint and Defender for Office 365.</span></span> <span data-ttu-id="65672-128">Ele define um idioma comum para todas as ações de correção e fornece uma experiência de investigação unificada.</span><span class="sxs-lookup"><span data-stu-id="65672-128">It defines a common language for all remediation actions, and provides a unified investigation experience.</span></span> 

<span data-ttu-id="65672-129">Você pode usar o Centro de Ações unificado se tiver permissões apropriadas e uma ou mais das seguintes assinaturas:</span><span class="sxs-lookup"><span data-stu-id="65672-129">You can use the unified Action center if you have appropriate permissions and one or more of the following subscriptions:</span></span>
- [<span data-ttu-id="65672-130">Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="65672-130">Defender for Endpoint</span></span>](microsoft-defender-advanced-threat-protection.md)
- [<span data-ttu-id="65672-131">O que é o Defender para Office 365?</span><span class="sxs-lookup"><span data-stu-id="65672-131">Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp)
- [<span data-ttu-id="65672-132">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65672-132">Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> <span data-ttu-id="65672-133">Para saber mais, confira [Requisitos](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).</span><span class="sxs-lookup"><span data-stu-id="65672-133">To learn more, see [Requirements](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).</span></span>

## <a name="using-the-action-center"></a><span data-ttu-id="65672-134">Usando o Centro de Ações</span><span class="sxs-lookup"><span data-stu-id="65672-134">Using the Action center</span></span>

<span data-ttu-id="65672-135">Para chegar ao Centro de Ações unificado no centro de segurança do Microsoft 365 aprimorado:</span><span class="sxs-lookup"><span data-stu-id="65672-135">To get to the unified Action center in the improved Microsoft 365 security center:</span></span>
1. <span data-ttu-id="65672-136">Vá para o Centro de Segurança do Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="65672-136">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="65672-137">No painel de navegação, selecione **Centro de ações**.</span><span class="sxs-lookup"><span data-stu-id="65672-137">In the navigation pane, select **Action center**.</span></span> 

<span data-ttu-id="65672-138">Ao visitar a Central de Ações, você verá duas guias: **Ações pendentes** e **Histórico**.</span><span class="sxs-lookup"><span data-stu-id="65672-138">When you visit the Action center, you see two tabs: **Pending actions** and **History**.</span></span> <span data-ttu-id="65672-139">A tabela a seguir resume o que você verá em cada guia:</span><span class="sxs-lookup"><span data-stu-id="65672-139">The following table summarizes what you'll see on each tab:</span></span>

|<span data-ttu-id="65672-140">Guia</span><span class="sxs-lookup"><span data-stu-id="65672-140">Tab</span></span>  |<span data-ttu-id="65672-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="65672-141">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="65672-142">**Pending**</span><span class="sxs-lookup"><span data-stu-id="65672-142">**Pending**</span></span>     | <span data-ttu-id="65672-143">Exibe uma lista de ações que exigem atenção.</span><span class="sxs-lookup"><span data-stu-id="65672-143">Displays a list of actions that require attention.</span></span> <span data-ttu-id="65672-144">Você pode aprovar ou rejeitar ações uma de cada vez ou selecionar várias ações se elas têm o mesmo tipo de ação (como arquivo **de quarentena).**</span><span class="sxs-lookup"><span data-stu-id="65672-144">You can approve or reject actions one at a time, or select multiple actions if they have the same type of action (such as **Quarantine file**).</span></span> <br/><span data-ttu-id="65672-145">**DICA**: Certifique-se de revisar e aprovar [(ou rejeitar)](manage-auto-investigation.md) ações pendentes assim que possível para que suas investigações automatizadas possam ser concluídas em tempo hábil.</span><span class="sxs-lookup"><span data-stu-id="65672-145">**TIP**: Make sure to [review and approve (or reject) pending actions](manage-auto-investigation.md) as soon as possible so that your automated investigations can complete in a timely manner.</span></span> |
|<span data-ttu-id="65672-146">**Histórico**</span><span class="sxs-lookup"><span data-stu-id="65672-146">**History**</span></span>     | <span data-ttu-id="65672-147">Serve como um log de auditoria para ações que foram realizadas, como:</span><span class="sxs-lookup"><span data-stu-id="65672-147">Serves as an audit log for actions that were taken, such as:</span></span> <br/><span data-ttu-id="65672-148">- Ações de correção que foram tomadas como resultado de investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="65672-148">- Remediation actions that were taken as a result of automated investigations</span></span> <br><span data-ttu-id="65672-149">- Ações de correção aprovadas pela sua equipe de operações de segurança</span><span class="sxs-lookup"><span data-stu-id="65672-149">- Remediation actions that were approved by your security operations team</span></span>  <br/><span data-ttu-id="65672-150">- Comandos executados e ações de correção que foram aplicadas durante as sessões de Resposta ao Vivo</span><span class="sxs-lookup"><span data-stu-id="65672-150">- Commands that were run and remediation actions that were applied during Live Response sessions</span></span>  <br/><span data-ttu-id="65672-151">- Ações de correção que foram tomadas pelos recursos de proteção contra ameaças no Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="65672-151">- Remediation actions that were taken by threat protection features in Microsoft Defender Antivirus</span></span>  <p><span data-ttu-id="65672-152">Fornece uma maneira de desfazer determinadas ações (consulte [Desfazer ações concluídas](manage-auto-investigation.md#undo-completed-actions)).</span><span class="sxs-lookup"><span data-stu-id="65672-152">Provides a way to undo certain actions (see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions)).</span></span>       |

<span data-ttu-id="65672-153">Você pode personalizar, classificar, filtrar e exportar dados no Centro de Ações.</span><span class="sxs-lookup"><span data-stu-id="65672-153">You can customize, sort, filter, and export data in the Action center.</span></span>

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Colunas e filtros no Centro de Ações":::

- <span data-ttu-id="65672-155">Selecione um título de coluna para classificar itens em ordem crescente ou decrescente.</span><span class="sxs-lookup"><span data-stu-id="65672-155">Select a column heading to sort items in ascending or descending order.</span></span>
- <span data-ttu-id="65672-156">Use o filtro de período de tempo para exibir dados do último dia, semana, 30 dias ou 6 meses.</span><span class="sxs-lookup"><span data-stu-id="65672-156">Use the time period filter to view data for the past day, week, 30 days, or 6 months.</span></span>
- <span data-ttu-id="65672-157">Escolha as colunas que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="65672-157">Choose the columns that you want to view.</span></span>
- <span data-ttu-id="65672-158">Especifique quantos itens devem ser incluídos em cada página de dados.</span><span class="sxs-lookup"><span data-stu-id="65672-158">Specify how many items to include on each page of data.</span></span>
- <span data-ttu-id="65672-159">Use filtros para exibir apenas os itens que você deseja ver.</span><span class="sxs-lookup"><span data-stu-id="65672-159">Use filters to view just the items you want to see.</span></span>
- <span data-ttu-id="65672-160">Selecione **Exportar** para exportar resultados para um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="65672-160">Select **Export** to export results to a .csv file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="65672-161">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="65672-161">Next steps</span></span>

- [<span data-ttu-id="65672-162">Exibir e aprovar ações de correção</span><span class="sxs-lookup"><span data-stu-id="65672-162">View and approve remediation actions</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="65672-163">Consulte o guia interativo: Investigar e correção de ameaças com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="65672-163">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a><span data-ttu-id="65672-164">Confira também</span><span class="sxs-lookup"><span data-stu-id="65672-164">See also</span></span>

- [<span data-ttu-id="65672-165">Resolver falsos positivos/negativos no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="65672-165">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
