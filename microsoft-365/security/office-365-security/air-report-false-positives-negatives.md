---
title: Como relatar falsos positivos ou falsos negativos em investigação e resposta automatizadas do Office 365
description: Algo estava perdido ou foi detectado incorretamente pela proteção avançada contra ameaças do Office 365? Saiba como enviar falsos positivos ou falsos negativos para a Microsoft para análise.
keywords: automatizado, investigação, alerta, gatilho, ação, correção, falso positivo, falso negativo
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 2dd67af62a400f3e217f146e6d0ee213d74ad99a
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262402"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="5fcb2-105">Como relatar falsos positivos/negativos em recursos de investigação e resposta automatizados</span><span class="sxs-lookup"><span data-stu-id="5fcb2-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="5fcb2-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5fcb2-106">**Applies to:**</span></span>
- <span data-ttu-id="5fcb2-107">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="5fcb2-107">Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="5fcb2-108">Os [recursos de investigação e resposta automatizados (Air) do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) perdem ou detectou erroneamente algo?</span><span class="sxs-lookup"><span data-stu-id="5fcb2-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="5fcb2-109">Há etapas que você pode executar para corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="5fcb2-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="5fcb2-110">Você pode:</span><span class="sxs-lookup"><span data-stu-id="5fcb2-110">You can:</span></span>
- <span data-ttu-id="5fcb2-111">[Relatar um falso positivo/negativo para a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="5fcb2-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="5fcb2-112">[Ajustar seus alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessário); e</span><span class="sxs-lookup"><span data-stu-id="5fcb2-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="5fcb2-113">[Desfazer ações de correção que foram tomadas nos dispositivos](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="5fcb2-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="5fcb2-114">Use este artigo como uma guia.</span><span class="sxs-lookup"><span data-stu-id="5fcb2-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="5fcb2-115">Relatar um falso positivo/negativo para a Microsoft para análise</span><span class="sxs-lookup"><span data-stu-id="5fcb2-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="5fcb2-116">Se o Office 365 AIR perdeu uma mensagem de email, um anexo de email, uma URL em uma mensagem de email ou uma URL em um arquivo do Office, você pode [enviar spam, Phish, URLs e arquivos suspeitos para a Microsoft para a verificação do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span><span class="sxs-lookup"><span data-stu-id="5fcb2-116">If Office 365 AIR missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="5fcb2-117">Você também pode [enviar um arquivo para a Microsoft para análise de malware](https://www.microsoft.com/wdsi/filesubmission).</span><span class="sxs-lookup"><span data-stu-id="5fcb2-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="5fcb2-118">Ajustar um alerta para impedir que falsos positivos sejam recorrentes</span><span class="sxs-lookup"><span data-stu-id="5fcb2-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="5fcb2-119">Se um alerta for disparado por uso legítimo ou se o alerta for impreciso, você poderá [Gerenciar alertas no portal do Cloud app Security](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span><span class="sxs-lookup"><span data-stu-id="5fcb2-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="5fcb2-120">Se sua organização estiver usando a [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection) , além do Office 365, e um arquivo, endereço IP, URL ou domínio for tratado como malware em um dispositivo, mesmo que seja seguro, você poderá [criar um indicador personalizado com uma ação "permitir" para o dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="5fcb2-120">If your organization is using [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="5fcb2-121">Desfazer uma ação de correção</span><span class="sxs-lookup"><span data-stu-id="5fcb2-121">Undo a remediation action</span></span>

<span data-ttu-id="5fcb2-122">Na maioria dos casos, se uma ação de correção foi realizada em uma mensagem de email, anexo de email ou URL, e o item não é uma ameaça, a equipe de operações de segurança pode desfazer a ação de correção e realizar etapas para evitar o falso positivo de recorrência.</span><span class="sxs-lookup"><span data-stu-id="5fcb2-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="5fcb2-123">Você pode usar o [Gerenciador de ameaças](#undo-an-action-using-threat-explorer) ou a [guia ações para uma investigação](#undo-an-action-using-the-actions-tab-for-an-investigation) para desfazer uma ação.</span><span class="sxs-lookup"><span data-stu-id="5fcb2-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="5fcb2-124">Verifique se você tem as permissões necessárias antes de tentar executar as tarefas a seguir.</span><span class="sxs-lookup"><span data-stu-id="5fcb2-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="5fcb2-125">Desfazer uma ação usando o explorador de ameaças</span><span class="sxs-lookup"><span data-stu-id="5fcb2-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="5fcb2-126">Com o Gerenciador de ameaças, a equipe de operações de segurança pode encontrar um email afetado por uma ação e possivelmente desfazer a ação.</span><span class="sxs-lookup"><span data-stu-id="5fcb2-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="5fcb2-127">Cenário</span><span class="sxs-lookup"><span data-stu-id="5fcb2-127">Scenario</span></span>  |<span data-ttu-id="5fcb2-128">Opções de desfazer</span><span class="sxs-lookup"><span data-stu-id="5fcb2-128">Undo Options</span></span>  |<span data-ttu-id="5fcb2-129">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="5fcb2-129">Learn more</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5fcb2-130">Uma mensagem de email foi encaminhada para a pasta lixo eletrônico de um usuário</span><span class="sxs-lookup"><span data-stu-id="5fcb2-130">An email message was routed to a user's Junk Email folder</span></span>     |<span data-ttu-id="5fcb2-131">-Mover a mensagem para a pasta itens excluídos do usuário</span><span class="sxs-lookup"><span data-stu-id="5fcb2-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="5fcb2-132">-Mover a mensagem para a caixa de entrada do usuário</span><span class="sxs-lookup"><span data-stu-id="5fcb2-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="5fcb2-133">-Excluir a mensagem</span><span class="sxs-lookup"><span data-stu-id="5fcb2-133">- Delete the message</span></span>          |[<span data-ttu-id="5fcb2-134">Encontre e investigue emails mal-intencionados que foram entregues no Office 365</span><span class="sxs-lookup"><span data-stu-id="5fcb2-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|<span data-ttu-id="5fcb2-135">Uma mensagem de email ou um arquivo foi colocado em quarentena</span><span class="sxs-lookup"><span data-stu-id="5fcb2-135">An email message or a file was quarantined</span></span>     |<span data-ttu-id="5fcb2-136">– Libera o email ou o arquivo</span><span class="sxs-lookup"><span data-stu-id="5fcb2-136">- Release the email or file</span></span> <br/><span data-ttu-id="5fcb2-137">-Excluir o email ou o arquivo</span><span class="sxs-lookup"><span data-stu-id="5fcb2-137">- Delete the email or file</span></span>         |[<span data-ttu-id="5fcb2-138">Gerenciar arquivos e mensagens em quarentena como um administrador no Office 365</span><span class="sxs-lookup"><span data-stu-id="5fcb2-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="5fcb2-139">Desfazer uma ação usando a guia ações para uma investigação</span><span class="sxs-lookup"><span data-stu-id="5fcb2-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="5fcb2-140">Na central de ações, você pode ver ações de correção que foram tomadas e possivelmente desfazer a ação.</span><span class="sxs-lookup"><span data-stu-id="5fcb2-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="5fcb2-141">Vá para [https://protection.office.com](https://protection.office.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="5fcb2-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="5fcb2-142">Isso leva você para o centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="5fcb2-142">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="5fcb2-143">Vá para investigações de **Gerenciamento de ameaças**  >  **Investigations**.</span><span class="sxs-lookup"><span data-stu-id="5fcb2-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="5fcb2-144">Na lista de investigações, selecione o ícone **abrir na nova janela** ao lado da ID de um item.</span><span class="sxs-lookup"><span data-stu-id="5fcb2-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="5fcb2-145">Selecione a guia **ações** .</span><span class="sxs-lookup"><span data-stu-id="5fcb2-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="5fcb2-146">Selecione um item com status **concluído**e procure um link, como **aprovado**, na coluna **decisão** .</span><span class="sxs-lookup"><span data-stu-id="5fcb2-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="5fcb2-147">Isso abre um submenu com mais detalhes sobre a ação.</span><span class="sxs-lookup"><span data-stu-id="5fcb2-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="5fcb2-148">Para desfazer a ação, selecione **excluir correção**.</span><span class="sxs-lookup"><span data-stu-id="5fcb2-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5fcb2-149">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="5fcb2-149">Related articles</span></span>

[<span data-ttu-id="5fcb2-150">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="5fcb2-150">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="5fcb2-151">Introdução ao uso de investigação e resposta automatizadas (AIR) no Office 365</span><span class="sxs-lookup"><span data-stu-id="5fcb2-151">Get started using Automated investigation and response (AIR) in Office 365</span></span>](office-365-air.md)