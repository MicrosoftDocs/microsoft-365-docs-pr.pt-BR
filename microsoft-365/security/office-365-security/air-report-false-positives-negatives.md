---
title: Como relatar falsos positivos ou falsos negativos após investigação automatizada no Microsoft Defender para Office 365
description: Algo foi perdido ou detectado incorretamente pelo AIR no Microsoft Defender para Office 365? Saiba como enviar falsos positivos ou falsos negativos à Microsoft para análise.
keywords: automatizado, investigação, alerta, gatilho, ação, correção, falso positivo, falso negativo
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 451a6b19139502a3765795694860e884a7a469bf
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175746"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="963de-105">Como relatar falsos positivos/negativos em recursos automatizados de investigação e resposta</span><span class="sxs-lookup"><span data-stu-id="963de-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="963de-106">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="963de-106">**Applies to**</span></span>
- [<span data-ttu-id="963de-107">Microsoft Defender para Office 365 plano 2</span><span class="sxs-lookup"><span data-stu-id="963de-107">Microsoft Defender for Office 365 plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="963de-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="963de-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="963de-109">Se os recursos de investigação e resposta [automatizadas (AIR) no Office 365](automated-investigation-response-office.md) perderam ou detectaram incorretamente algo, há etapas que sua equipe de operações de segurança pode seguir para corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="963de-109">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="963de-110">Essas ações incluem:</span><span class="sxs-lookup"><span data-stu-id="963de-110">Such actions include:</span></span>

- <span data-ttu-id="963de-111">[Relatar um falso positivo/negativo para a Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="963de-111">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="963de-112">[Ajustando alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessário); e</span><span class="sxs-lookup"><span data-stu-id="963de-112">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="963de-113">[Desfazer ações de correção que foram tomadas.](#undo-a-remediation-action)</span><span class="sxs-lookup"><span data-stu-id="963de-113">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="963de-114">Use este artigo como guia.</span><span class="sxs-lookup"><span data-stu-id="963de-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="963de-115">Relatar um falso positivo/negativo à Microsoft para análise</span><span class="sxs-lookup"><span data-stu-id="963de-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="963de-116">Se o AIR no Microsoft Defender para Office 365 perdeu uma mensagem de email, um anexo de email, uma URL em uma mensagem de email ou uma URL em um arquivo do Office, você pode enviar [spam, phishing, URLs](admin-submission.md)e arquivos suspeitos para a verificação do Microsoft para Office 365.</span><span class="sxs-lookup"><span data-stu-id="963de-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="963de-117">Você também pode [enviar um arquivo à Microsoft para análise de malware.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="963de-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="963de-118">Ajustar um alerta para evitar que falsos positivos se repitam</span><span class="sxs-lookup"><span data-stu-id="963de-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="963de-119">Se um alerta for disparado por uso legítimo ou se o alerta for impreciso, você poderá gerenciar alertas no portal do [Cloud App Security.](https://docs.microsoft.com/cloud-app-security/managing-alerts)</span><span class="sxs-lookup"><span data-stu-id="963de-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="963de-120">Se sua organização estiver usando o [Microsoft Defender para](https://docs.microsoft.com/windows/security/threat-protection) Ponto de Extremidade, além do Office 365, e um arquivo, endereço IP, URL ou domínio for tratado como malware em um dispositivo, mesmo que seja seguro, você pode criar um indicador personalizado com uma ação ["Permitir"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)para seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="963de-120">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="963de-121">Desfazer uma ação de correção</span><span class="sxs-lookup"><span data-stu-id="963de-121">Undo a remediation action</span></span>

<span data-ttu-id="963de-122">Na maioria dos casos, se uma ação de correção tiver sido realizada em uma mensagem de email, um anexo de email ou uma URL, e o item não for realmente uma ameaça, sua equipe de operações de segurança poderá desfazer a ação de correção e tomar medidas para evitar que o falso positivo se repita.</span><span class="sxs-lookup"><span data-stu-id="963de-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="963de-123">Você pode usar o [Explorador de Ameaças](#undo-an-action-using-threat-explorer) ou a guia Ações para uma investigação [desfazer](#undo-an-action-in-the-action-center) uma ação.</span><span class="sxs-lookup"><span data-stu-id="963de-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="963de-124">Certifique-se de que você tenha as permissões necessárias antes de tentar executar as tarefas a seguir.</span><span class="sxs-lookup"><span data-stu-id="963de-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="963de-125">Desfazer uma ação usando o Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="963de-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="963de-126">Com o Explorador de Ameaças, sua equipe de operações de segurança pode encontrar um email afetado por uma ação e potencialmente desfazer a ação.</span><span class="sxs-lookup"><span data-stu-id="963de-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="963de-127">Cenário</span><span class="sxs-lookup"><span data-stu-id="963de-127">Scenario</span></span>|<span data-ttu-id="963de-128">Opções de desfazer</span><span class="sxs-lookup"><span data-stu-id="963de-128">Undo Options</span></span>|<span data-ttu-id="963de-129">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="963de-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="963de-130">Uma mensagem de email foi roteada para a pasta Lixo Eletrônico de um usuário</span><span class="sxs-lookup"><span data-stu-id="963de-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="963de-131">- Mover a mensagem para a pasta Itens Excluídos do usuário</span><span class="sxs-lookup"><span data-stu-id="963de-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="963de-132">- Mover a mensagem para a Caixa de Entrada do usuário</span><span class="sxs-lookup"><span data-stu-id="963de-132">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="963de-133">- Excluir a mensagem</span><span class="sxs-lookup"><span data-stu-id="963de-133">- Delete the message</span></span>|[<span data-ttu-id="963de-134">Encontrar e investigar emails mal-intencionados que foram entregues no Office 365</span><span class="sxs-lookup"><span data-stu-id="963de-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="963de-135">Uma mensagem de email ou um arquivo foi colocado em quarentena</span><span class="sxs-lookup"><span data-stu-id="963de-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="963de-136">- Liberar o email ou arquivo</span><span class="sxs-lookup"><span data-stu-id="963de-136">- Release the email or file</span></span><br/><span data-ttu-id="963de-137">- Excluir o email ou o arquivo</span><span class="sxs-lookup"><span data-stu-id="963de-137">- Delete the email or file</span></span>|[<span data-ttu-id="963de-138">Gerenciar mensagens em quarentena como administrador</span><span class="sxs-lookup"><span data-stu-id="963de-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="963de-139">Desfazer uma ação na Central de ações</span><span class="sxs-lookup"><span data-stu-id="963de-139">Undo an action in the Action center</span></span>

<span data-ttu-id="963de-140">Na Central de ações, você pode ver as ações de correção que foram tomadas e potencialmente desfazer a ação.</span><span class="sxs-lookup"><span data-stu-id="963de-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="963de-141">Vá para a central de segurança do Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ).</span><span class="sxs-lookup"><span data-stu-id="963de-141">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span>
2. <span data-ttu-id="963de-142">No painel de navegação, selecione Central **de ações.**</span><span class="sxs-lookup"><span data-stu-id="963de-142">In the navigation pane, select **Action center**.</span></span> 
3. <span data-ttu-id="963de-143">Selecione a **guia Histórico** para exibir a lista de ações concluídas.</span><span class="sxs-lookup"><span data-stu-id="963de-143">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="963de-144">Selecione um item.</span><span class="sxs-lookup"><span data-stu-id="963de-144">Select an item.</span></span> <span data-ttu-id="963de-145">Seu painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="963de-145">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="963de-146">No painel do flyout, selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="963de-146">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="963de-147">(Somente ações que podem ser desfeitas terão um **botão Desfazer.)**</span><span class="sxs-lookup"><span data-stu-id="963de-147">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="963de-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="963de-148">See also</span></span>

- [<span data-ttu-id="963de-149">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="963de-149">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="963de-150">Investigações automatizadas no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="963de-150">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
