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
ms.openlocfilehash: 4ccc023a72ca450b1f0a433410206ccce59cb5f1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142969"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="f4e01-105">Como relatar falsos positivos/negativos em recursos automatizados de investigação e resposta</span><span class="sxs-lookup"><span data-stu-id="f4e01-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="f4e01-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f4e01-106">**Applies to:**</span></span>
- <span data-ttu-id="f4e01-107">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f4e01-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="f4e01-108">Se os recursos de investigação e resposta [automatizadas (AIR) no Office 365](automated-investigation-response-office.md) perderam ou detectaram incorretamente algo, há etapas que sua equipe de operações de segurança pode seguir para corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="f4e01-108">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="f4e01-109">Essas ações incluem:</span><span class="sxs-lookup"><span data-stu-id="f4e01-109">Such actions include:</span></span>

- <span data-ttu-id="f4e01-110">[Relatar um falso positivo/negativo para a Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="f4e01-110">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="f4e01-111">[Ajustando alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessário); e</span><span class="sxs-lookup"><span data-stu-id="f4e01-111">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="f4e01-112">[Desfazer ações de correção que foram tomadas.](#undo-a-remediation-action)</span><span class="sxs-lookup"><span data-stu-id="f4e01-112">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="f4e01-113">Use este artigo como guia.</span><span class="sxs-lookup"><span data-stu-id="f4e01-113">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="f4e01-114">Relatar um falso positivo/negativo à Microsoft para análise</span><span class="sxs-lookup"><span data-stu-id="f4e01-114">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="f4e01-115">Se o AIR no Microsoft Defender para Office 365 perdeu uma mensagem de email, um anexo de email, uma URL em uma mensagem de email ou uma URL em um arquivo do Office, você pode enviar [spam, phishing, URLs](admin-submission.md)e arquivos suspeitos para a verificação do Microsoft para Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4e01-115">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="f4e01-116">Você também pode [enviar um arquivo à Microsoft para análise de malware.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="f4e01-116">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="f4e01-117">Ajustar um alerta para evitar que falsos positivos se repitam</span><span class="sxs-lookup"><span data-stu-id="f4e01-117">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="f4e01-118">Se um alerta for disparado por uso legítimo ou se o alerta for impreciso, você poderá gerenciar alertas no portal do [Cloud App Security.](https://docs.microsoft.com/cloud-app-security/managing-alerts)</span><span class="sxs-lookup"><span data-stu-id="f4e01-118">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="f4e01-119">Se sua organização estiver usando o [Microsoft Defender para](https://docs.microsoft.com/windows/security/threat-protection) Ponto de Extremidade, além do Office 365, e um arquivo, endereço IP, URL ou domínio for tratado como malware em um dispositivo, mesmo que seja seguro, você pode criar um indicador personalizado com uma ação ["Permitir"](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)para seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f4e01-119">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="f4e01-120">Desfazer uma ação de correção</span><span class="sxs-lookup"><span data-stu-id="f4e01-120">Undo a remediation action</span></span>

<span data-ttu-id="f4e01-121">Na maioria dos casos, se uma ação de correção tiver sido realizada em uma mensagem de email, um anexo de email ou uma URL, e o item não for realmente uma ameaça, sua equipe de operações de segurança poderá desfazer a ação de correção e tomar medidas para evitar que o falso positivo se repita.</span><span class="sxs-lookup"><span data-stu-id="f4e01-121">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="f4e01-122">Você pode usar o [Explorador de Ameaças](#undo-an-action-using-threat-explorer) ou a guia Ações para uma investigação [desfazer](#undo-an-action-in-the-action-center) uma ação.</span><span class="sxs-lookup"><span data-stu-id="f4e01-122">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4e01-123">Certifique-se de que você tenha as permissões necessárias antes de tentar executar as tarefas a seguir.</span><span class="sxs-lookup"><span data-stu-id="f4e01-123">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="f4e01-124">Desfazer uma ação usando o Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="f4e01-124">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="f4e01-125">Com o Explorador de Ameaças, sua equipe de operações de segurança pode encontrar um email afetado por uma ação e potencialmente desfazer a ação.</span><span class="sxs-lookup"><span data-stu-id="f4e01-125">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="f4e01-126">Cenário</span><span class="sxs-lookup"><span data-stu-id="f4e01-126">Scenario</span></span>|<span data-ttu-id="f4e01-127">Opções de desfazer</span><span class="sxs-lookup"><span data-stu-id="f4e01-127">Undo Options</span></span>|<span data-ttu-id="f4e01-128">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="f4e01-128">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="f4e01-129">Uma mensagem de email foi roteada para a pasta Lixo Eletrônico de um usuário</span><span class="sxs-lookup"><span data-stu-id="f4e01-129">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="f4e01-130">- Mover a mensagem para a pasta Itens Excluídos do usuário</span><span class="sxs-lookup"><span data-stu-id="f4e01-130">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="f4e01-131">- Mover a mensagem para a Caixa de Entrada do usuário</span><span class="sxs-lookup"><span data-stu-id="f4e01-131">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="f4e01-132">- Excluir a mensagem</span><span class="sxs-lookup"><span data-stu-id="f4e01-132">- Delete the message</span></span>|[<span data-ttu-id="f4e01-133">Encontrar e investigar emails mal-intencionados que foram entregues no Office 365</span><span class="sxs-lookup"><span data-stu-id="f4e01-133">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="f4e01-134">Uma mensagem de email ou um arquivo foi colocado em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4e01-134">An email message or a file was quarantined</span></span>|<span data-ttu-id="f4e01-135">- Liberar o email ou arquivo</span><span class="sxs-lookup"><span data-stu-id="f4e01-135">- Release the email or file</span></span><br/><span data-ttu-id="f4e01-136">- Excluir o email ou arquivo</span><span class="sxs-lookup"><span data-stu-id="f4e01-136">- Delete the email or file</span></span>|[<span data-ttu-id="f4e01-137">Gerenciar mensagens em quarentena como administrador</span><span class="sxs-lookup"><span data-stu-id="f4e01-137">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="f4e01-138">Desfazer uma ação na Central de ações</span><span class="sxs-lookup"><span data-stu-id="f4e01-138">Undo an action in the Action center</span></span>

<span data-ttu-id="f4e01-139">Na Central de ações, você pode ver as ações de correção que foram tomadas e potencialmente desfazer a ação.</span><span class="sxs-lookup"><span data-stu-id="f4e01-139">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="f4e01-140">Vá para a central de segurança do Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ).</span><span class="sxs-lookup"><span data-stu-id="f4e01-140">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span>
2. <span data-ttu-id="f4e01-141">No painel de navegação, selecione Central **de ações.**</span><span class="sxs-lookup"><span data-stu-id="f4e01-141">In the navigation pane, select **Action center**.</span></span> 
3. <span data-ttu-id="f4e01-142">Selecione a **guia Histórico** para exibir a lista de ações concluídas.</span><span class="sxs-lookup"><span data-stu-id="f4e01-142">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="f4e01-143">Selecione um item.</span><span class="sxs-lookup"><span data-stu-id="f4e01-143">Select an item.</span></span> <span data-ttu-id="f4e01-144">Seu painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="f4e01-144">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="f4e01-145">No painel do flyout, selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="f4e01-145">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="f4e01-146">(Somente ações que podem ser desfeitas terão um **botão Desfazer.)**</span><span class="sxs-lookup"><span data-stu-id="f4e01-146">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="f4e01-147">Confira também</span><span class="sxs-lookup"><span data-stu-id="f4e01-147">See also</span></span>

- [<span data-ttu-id="f4e01-148">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f4e01-148">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="f4e01-149">Investigações automatizadas no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f4e01-149">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
