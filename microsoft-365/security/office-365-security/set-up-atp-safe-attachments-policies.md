---
title: Configurar políticas de anexos seguros no Microsoft defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Saiba como definir políticas de anexos seguros para proteger sua organização contra arquivos mal-intencionados no email.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca0bfb7ba91f86fee187cfe3445c0dd6c8d4ad56
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845487"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="29b4e-103">Configurar políticas de anexos seguros no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="29b4e-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="29b4e-104">Este artigo destina-se a clientes comerciais que têm [o Microsoft defender para Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="29b4e-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="29b4e-105">Se você for um usuário doméstico que está procurando por informações sobre a verificação de anexos no Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="29b4e-105">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="29b4e-106">Anexos seguros é um recurso do [Microsoft defender para Office 365](office-365-atp.md) que usa um ambiente virtual para verificar anexos em mensagens de email de entrada depois de terem sido verificados pela [proteção Antimalware no Exchange Online Protection (EOP)](anti-malware-protection.md), mas antes da entrega aos destinatários.</span><span class="sxs-lookup"><span data-stu-id="29b4e-106">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="29b4e-107">Para obter mais informações, consulte [Safe Attachments in Microsoft defender for Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="29b4e-107">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="29b4e-108">Não há nenhuma política de anexos confiáveis interna ou padrão.</span><span class="sxs-lookup"><span data-stu-id="29b4e-108">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="29b4e-109">Para obter a verificação de anexos seguros de anexos de mensagens de email, você precisa criar uma ou mais políticas de anexos seguros, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="29b4e-109">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="29b4e-110">Você pode configurar políticas de anexos seguros no centro de conformidade do & de segurança ou no PowerShell (Exchange Online PowerShell para organizações qualificadas da Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomos para organizações sem caixas de correio do Exchange Online, mas com o defender for Office 365 Add-on subscriptions).</span><span class="sxs-lookup"><span data-stu-id="29b4e-110">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="29b4e-111">Os elementos básicos de uma política de anexos seguros são:</span><span class="sxs-lookup"><span data-stu-id="29b4e-111">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="29b4e-112">**A política de anexo seguro** : especifica as ações para detecções de malware desconhecidas, se enviar mensagens com anexos de malware para um endereço de email especificado e se deseja entregar mensagens caso a verificação de anexos seguros não possa ser concluída.</span><span class="sxs-lookup"><span data-stu-id="29b4e-112">**The safe attachment policy** : Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="29b4e-113">**A regra de anexo seguro** : especifica a prioridade e os filtros de destinatário (a qual a política se aplica).</span><span class="sxs-lookup"><span data-stu-id="29b4e-113">**The safe attachment rule** : Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="29b4e-114">A diferença entre esses dois elementos não é óbvia quando você gerencia políticas de anexos seguros no centro de conformidade de & de segurança:</span><span class="sxs-lookup"><span data-stu-id="29b4e-114">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="29b4e-115">Ao criar uma política de anexos seguros, você realmente está criando uma regra de anexo seguro e a política de anexo seguro associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="29b4e-115">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="29b4e-116">Quando você modifica uma política de anexos seguros, as configurações relacionadas ao nome, prioridade, habilitado ou desabilitado e filtros de destinatário modificam a regra de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="29b4e-116">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="29b4e-117">Todas as outras configurações modificam a política de anexo seguro associada.</span><span class="sxs-lookup"><span data-stu-id="29b4e-117">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="29b4e-118">Quando você remove uma política de anexos seguros, a regra de anexo seguro e a política de anexo seguro associada são removidos.</span><span class="sxs-lookup"><span data-stu-id="29b4e-118">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="29b4e-119">No PowerShell do Exchange Online ou no PowerShell do EOP autônomo, a política e a regra são gerenciadas separadamente.</span><span class="sxs-lookup"><span data-stu-id="29b4e-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="29b4e-120">Para obter mais informações, consulte a seção [usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar políticas de anexos seguros](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) , posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="29b4e-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="29b4e-121">Na área configurações globais das configurações de anexos seguros, você configura recursos que não são dependentes de políticas de anexos seguros.</span><span class="sxs-lookup"><span data-stu-id="29b4e-121">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="29b4e-122">Para obter instruções, confira [Ativar ATP para SharePoint, onedrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) e [documentos seguros no Microsoft 365 E5](safe-docs.md).</span><span class="sxs-lookup"><span data-stu-id="29b4e-122">For instructions see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="29b4e-123">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="29b4e-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="29b4e-124">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="29b4e-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="29b4e-125">Para ir diretamente para a página de **anexos seguros** , use <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="29b4e-125">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="29b4e-126">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="29b4e-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="29b4e-127">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="29b4e-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="29b4e-128">Para exibir, criar, modificar e excluir políticas de anexos seguros, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="29b4e-128">To view, create, modify, and delete Safe Attachments policies, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="29b4e-129">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="29b4e-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="29b4e-130">**Gerenciamento de organização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="29b4e-130">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="29b4e-131">Para obter as configurações recomendadas para políticas de anexos seguros, consulte [configurações de anexos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="29b4e-131">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="29b4e-132">Aguarde até 30 minutos para que uma política nova ou atualizada seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="29b4e-132">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="29b4e-133">Usar o centro de conformidade de & de segurança para criar políticas de anexos seguros</span><span class="sxs-lookup"><span data-stu-id="29b4e-133">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="29b4e-134">A criação de uma política de anexos seguros personalizada no centro de conformidade de & de segurança cria a regra de anexo seguro e a política de anexo seguro associada ao mesmo tempo usando o mesmo nome para ambos.</span><span class="sxs-lookup"><span data-stu-id="29b4e-134">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="29b4e-135">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="29b4e-136">Na página **anexos seguros** , clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-136">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="29b4e-137">O assistente de **nova política de anexos seguros** é aberto.</span><span class="sxs-lookup"><span data-stu-id="29b4e-137">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="29b4e-138">Na página **nomear sua política** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="29b4e-138">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="29b4e-139">**Nome** : insira um nome exclusivo e descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="29b4e-139">**Name** : Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="29b4e-140">**Descrição** : digite uma descrição opcional para a política.</span><span class="sxs-lookup"><span data-stu-id="29b4e-140">**Description** : Enter an optional description for the policy.</span></span>

   <span data-ttu-id="29b4e-141">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="29b4e-142">Na página **configurações** que aparece, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="29b4e-142">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="29b4e-143">**Resposta de malware desconhecido de anexos seguros** : selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="29b4e-143">**Safe Attachments unknown malware response** : Select one of the following values:</span></span>

     - <span data-ttu-id="29b4e-144">**Off** : normalmente não é recomendável esse valor.</span><span class="sxs-lookup"><span data-stu-id="29b4e-144">**Off** : Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="29b4e-145">**Monitorar**</span><span class="sxs-lookup"><span data-stu-id="29b4e-145">**Monitor**</span></span>
     - <span data-ttu-id="29b4e-146">**Bloquear** : Este é o valor padrão e o valor recomendado em políticas de segurança padrão e estritas [predefinidas](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="29b4e-146">**Block** : This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="29b4e-147">**Replace**</span><span class="sxs-lookup"><span data-stu-id="29b4e-147">**Replace**</span></span>
     - <span data-ttu-id="29b4e-148">**Entrega dinâmica (recurso de visualização)**</span><span class="sxs-lookup"><span data-stu-id="29b4e-148">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="29b4e-149">Esses valores são explicados em [configurações de política de anexos seguros](atp-safe-attachments.md#safe-attachments-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="29b4e-149">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="29b4e-150">**Envie o anexo para o seguinte endereço de email** : para os valores de ação **Bloquear** , **monitorar** ou **substituir** , você pode selecionar **habilitar redirecionamento** para enviar mensagens que contenham anexos de malware para o endereço de email interno ou externo especificado para análise e investigação.</span><span class="sxs-lookup"><span data-stu-id="29b4e-150">**Send the attachment to the following email address** : For the action values **Block** , **Monitor** , or **Replace** , you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="29b4e-151">A recomendação para as configurações de política padrão e estrita é habilitar o redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="29b4e-151">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="29b4e-152">Para obter mais informações, consulte [configurações de anexos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="29b4e-152">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="29b4e-153">**Aplicar a seleção acima se a verificação de malware para anexos expirar ou ocorrer erro** : a ação especificada por **anexos seguros a resposta desconhecida** é tomada em mensagens, mesmo quando a verificação de anexos seguros não pode ser concluída.</span><span class="sxs-lookup"><span data-stu-id="29b4e-153">**Apply the above selection if malware scanning for attachments times out or error occurs** : The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="29b4e-154">Sempre Selecione esta opção se você selecionar **redirecionamento habilitado**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-154">Always select this option if you select **Enabled redirect**.</span></span> <span data-ttu-id="29b4e-155">Caso contrário, as mensagens poderão ser perdidas.</span><span class="sxs-lookup"><span data-stu-id="29b4e-155">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="29b4e-156">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-156">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="29b4e-157">Na página **aplicado a** que aparece, identifique os destinatários internos aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="29b4e-157">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="29b4e-158">Só é possível usar uma condição ou exceção uma vez; contudo, você pode especificar vários valores para a condição ou exceção.</span><span class="sxs-lookup"><span data-stu-id="29b4e-158">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="29b4e-159">Vários valores da mesma condição ou exceção usam a lógica OU (por exemplo, _\<recipient1\>_ ou _\<recipient2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="29b4e-159">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_ ).</span></span> <span data-ttu-id="29b4e-160">Para diferentes condições ou exceções, use a lógica E (por exemplo, _\<recipient1\>_ e _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="29b4e-160">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_ ).</span></span>

   <span data-ttu-id="29b4e-161">Clique em **Adicionar uma condição**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-161">Click **Add a condition**.</span></span> <span data-ttu-id="29b4e-162">Na lista suspensa exibida, selecione uma condição em **aplicado se** :</span><span class="sxs-lookup"><span data-stu-id="29b4e-162">In the dropdown that appears, select a condition under **Applied if** :</span></span>

   - <span data-ttu-id="29b4e-163">**O destinatário é** : especifica uma ou mais caixas de correio, usuários de email ou contatos de email em sua organização.</span><span class="sxs-lookup"><span data-stu-id="29b4e-163">**The recipient is** : Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="29b4e-164">**O destinatário é um membro de** : especifica um ou mais grupos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="29b4e-164">**The recipient is a member of** : Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="29b4e-165">**O domínio do destinatário é** : Especifica os destinatários em um ou mais domínios aceitos configurados na sua organização. </span><span class="sxs-lookup"><span data-stu-id="29b4e-165">**The recipient domain is** : Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="29b4e-166">Após selecionar a condição, uma lista suspensa correspondente aparecerá com uma **destas** caixas.</span><span class="sxs-lookup"><span data-stu-id="29b4e-166">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="29b4e-167">Clique na caixa e role pela lista de valores para selecionar.</span><span class="sxs-lookup"><span data-stu-id="29b4e-167">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="29b4e-168">Clique na caixa e comece a digitar para filtrar a lista e selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="29b4e-168">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="29b4e-169">Para adicionar valores adicionais, clique em uma área vazia na caixa.</span><span class="sxs-lookup"><span data-stu-id="29b4e-169">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="29b4e-170">Para remover entradas individuais, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) no valor.</span><span class="sxs-lookup"><span data-stu-id="29b4e-170">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="29b4e-171">Para remover toda a condição, clique em **remover** ![ ícone de remoção ](../../media/scc-remove-icon.png) na condição.</span><span class="sxs-lookup"><span data-stu-id="29b4e-171">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="29b4e-172">Para adicionar uma condição adicional, clique em **Adicionar uma condição** e selecione um valor restante em **aplica If**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-172">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="29b4e-173">Para adicionar exceções, clique em **Adicionar uma condição** e selecione uma exceção em **exceto se**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-173">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="29b4e-174">As configurações e o comportamento são exatamente como as condições.</span><span class="sxs-lookup"><span data-stu-id="29b4e-174">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="29b4e-175">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-175">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="29b4e-176">Na página **revise suas configurações** exibidas, revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="29b4e-176">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="29b4e-177">Você pode clicar em **Editar** em cada configuração para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="29b4e-177">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="29b4e-178">Quando tiver concluído, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-178">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="29b4e-179">Usar o centro de conformidade de & de segurança para exibir políticas de anexos seguros</span><span class="sxs-lookup"><span data-stu-id="29b4e-179">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="29b4e-180">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-180">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="29b4e-181">Na página **anexos seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="29b4e-181">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="29b4e-182">Os detalhes da política aparecem em saída</span><span class="sxs-lookup"><span data-stu-id="29b4e-182">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="29b4e-183">Usar o centro de conformidade de & de segurança para modificar políticas de anexos seguros</span><span class="sxs-lookup"><span data-stu-id="29b4e-183">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="29b4e-184">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-184">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="29b4e-185">Na página **anexos seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="29b4e-185">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="29b4e-186">Nos detalhes da política que aparecem, clique em **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-186">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="29b4e-187">As configurações disponíveis na saída que aparecem são idênticas àquelas descritas na seção [usar o centro de conformidade de segurança & para criar políticas de anexos seguros](#use-the-security--compliance-center-to-create-safe-attachments-policies) .</span><span class="sxs-lookup"><span data-stu-id="29b4e-187">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="29b4e-188">Para habilitar ou desabilitar uma política ou definir a ordem de prioridade da política, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="29b4e-188">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="29b4e-189">Habilitar ou desabilitar políticas de anexos seguros</span><span class="sxs-lookup"><span data-stu-id="29b4e-189">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="29b4e-190">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-190">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="29b4e-191">Observe o valor na coluna **status** :</span><span class="sxs-lookup"><span data-stu-id="29b4e-191">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="29b4e-192">Mover a alternância para a esquerda</span><span class="sxs-lookup"><span data-stu-id="29b4e-192">Move the toggle to the left</span></span> ![Desativar política](../../media/scc-toggle-off.png) <span data-ttu-id="29b4e-194">para desabilitar a política.</span><span class="sxs-lookup"><span data-stu-id="29b4e-194">to disable the policy.</span></span>

   - <span data-ttu-id="29b4e-195">Mover a alternância para a direita</span><span class="sxs-lookup"><span data-stu-id="29b4e-195">Move the toggle to the right</span></span> ![Ativar política](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) <span data-ttu-id="29b4e-197">para habilitar a política.</span><span class="sxs-lookup"><span data-stu-id="29b4e-197">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="29b4e-198">Definir a prioridade de políticas de anexos seguros</span><span class="sxs-lookup"><span data-stu-id="29b4e-198">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="29b4e-199">Por padrão, as políticas de anexos seguros recebem uma prioridade com base na ordem em que foram criadas (as políticas mais recentes são de prioridade mais baixa do que as diretivas mais antigas).</span><span class="sxs-lookup"><span data-stu-id="29b4e-199">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="29b4e-200">Um número de prioridade menor indica uma maior prioridade para a política (0 é a maior), e as políticas são processadas por ordem de prioridade (políticas com maior prioridade são processadas antes das políticas com menor prioridade).</span><span class="sxs-lookup"><span data-stu-id="29b4e-200">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="29b4e-201">Duas políticas não podem ter a mesma prioridade, e o processamento da política será interrompido após a primeira política ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="29b4e-201">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="29b4e-202">Para obter mais informações sobre a ordem de precedência e como várias políticas são avaliadas e aplicadas, confira [Ordem e precedência da proteção de email](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="29b4e-202">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="29b4e-203">As políticas de anexos seguros são exibidas na ordem em que são processadas (a primeira política tem o valor de **prioridade** 0).</span><span class="sxs-lookup"><span data-stu-id="29b4e-203">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="29b4e-204">**Observação** : no centro de conformidade & segurança, você só pode alterar a prioridade da política de anexos seguros após criá-la.</span><span class="sxs-lookup"><span data-stu-id="29b4e-204">**Note** : In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="29b4e-205">No PowerShell, você pode substituir a prioridade padrão ao criar a regra de anexo seguro (que pode afetar a prioridade das regras existentes).</span><span class="sxs-lookup"><span data-stu-id="29b4e-205">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="29b4e-206">Para alterar a prioridade de uma política, mova a política para cima ou para baixo na lista (não é possível modificar diretamente o número de **Prioridade** no Centro de Conformidade e Segurança).</span><span class="sxs-lookup"><span data-stu-id="29b4e-206">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="29b4e-207">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="29b4e-208">Na página **anexos seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="29b4e-208">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="29b4e-209">Na saída detalhes da política que aparece, clique no botão prioridade disponível.</span><span class="sxs-lookup"><span data-stu-id="29b4e-209">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="29b4e-210">A política de anexos seguros com o valor de **prioridade** **0** tem apenas o botão **diminuir prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="29b4e-210">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="29b4e-211">A política de anexos seguros com o menor valor de **prioridade** (por exemplo, **3** ) tem apenas o botão **aumentar prioridade** disponível.</span><span class="sxs-lookup"><span data-stu-id="29b4e-211">The Safe Attachments policy with the lowest **Priority** value (for example, **3** ) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="29b4e-212">Se você tiver três ou mais políticas de anexos confiáveis, as políticas entre os valores de prioridade mais alta e mais baixa terão os botões **aumentar prioridade** e **diminuir prioridade** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="29b4e-212">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="29b4e-213">Clique em **aumentar prioridade** ou **diminuir prioridade** para alterar o valor de **prioridade** .</span><span class="sxs-lookup"><span data-stu-id="29b4e-213">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="29b4e-214">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-214">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="29b4e-215">Usar o centro de conformidade de & de segurança para remover políticas de anexos seguros</span><span class="sxs-lookup"><span data-stu-id="29b4e-215">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="29b4e-216">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-216">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="29b4e-217">Na página **anexos seguros** , selecione uma política na lista e clique nela (não marque a caixa de seleção).</span><span class="sxs-lookup"><span data-stu-id="29b4e-217">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="29b4e-218">Nos detalhes da política de saída, clique em **excluir política** e clique em **Sim** na caixa de diálogo de aviso que aparece.</span><span class="sxs-lookup"><span data-stu-id="29b4e-218">In the policy details fly out that appears, click **Delete policy** , and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="29b4e-219">Usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar políticas de anexos seguros</span><span class="sxs-lookup"><span data-stu-id="29b4e-219">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="29b4e-220">Como descrito anteriormente, uma política de anexos seguros consiste em uma política de anexo seguro e uma regra de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="29b4e-220">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="29b4e-221">No PowerShell, a diferença entre políticas de anexo seguro e regras de anexo seguro é aparente.</span><span class="sxs-lookup"><span data-stu-id="29b4e-221">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="29b4e-222">Você gerencia políticas de anexo seguro usando os cmdlets **\* -SafeAttachmentPolicy** e gerencia regras de anexo seguro usando os cmdlets **\* -SafeAttachmentRule** .</span><span class="sxs-lookup"><span data-stu-id="29b4e-222">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="29b4e-223">No PowerShell, você cria a política de anexo seguro primeiro e, em seguida, cria a regra de anexo seguro que identifica a política à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="29b4e-223">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="29b4e-224">No PowerShell, modifique as configurações na política de anexo seguro e a regra de anexo seguro separadamente.</span><span class="sxs-lookup"><span data-stu-id="29b4e-224">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="29b4e-225">Quando você remove uma política de anexo seguro do PowerShell, a regra de anexo seguro correspondente não é removida automaticamente e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="29b4e-225">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="29b4e-226">Usar o PowerShell para criar políticas de anexos seguros</span><span class="sxs-lookup"><span data-stu-id="29b4e-226">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="29b4e-227">A criação de uma política de anexos seguros no PowerShell é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="29b4e-227">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="29b4e-228">Criar a política de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="29b4e-228">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="29b4e-229">Crie a regra de anexo seguro que especifica a política de anexo seguro à qual a regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="29b4e-229">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="29b4e-230">**Observações** :</span><span class="sxs-lookup"><span data-stu-id="29b4e-230">**Notes** :</span></span>

- <span data-ttu-id="29b4e-231">Você pode criar uma nova regra de anexo seguro e atribuir uma política de anexo segura existente e não associada a ela.</span><span class="sxs-lookup"><span data-stu-id="29b4e-231">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="29b4e-232">Uma regra de anexo seguro não pode ser associada a mais de uma política de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="29b4e-232">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="29b4e-233">Você pode definir as seguintes configurações em novas políticas de anexo seguro no PowerShell que não estão disponíveis no centro de conformidade & de segurança até que a política seja criada:</span><span class="sxs-lookup"><span data-stu-id="29b4e-233">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="29b4e-234">Crie a nova política como desabilitada ( _habilitada_ `$false` no cmdlet **New-SafeAttachmentRule** ).</span><span class="sxs-lookup"><span data-stu-id="29b4e-234">Create the new policy as disabled ( _Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="29b4e-235">Definir a prioridade da política durante a criação ( _prioridade_ _\<Number\>_ ) no cmdlet **New-SafeAttachmentRule** ).</span><span class="sxs-lookup"><span data-stu-id="29b4e-235">Set the priority of the policy during creation ( _Priority_ _\<Number\>_ ) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="29b4e-236">Uma nova política de anexo segura que você cria no PowerShell não fica visível no centro de conformidade & segurança até que você atribua a política a uma regra de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="29b4e-236">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="29b4e-237">Etapa 1: usar o PowerShell para criar uma política de anexo segura</span><span class="sxs-lookup"><span data-stu-id="29b4e-237">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="29b4e-238">Para criar uma política de anexo segura, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="29b4e-238">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="29b4e-239">Este exemplo cria uma política de anexo segura chamada contoso todos com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="29b4e-239">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="29b4e-240">Bloquear mensagens que são encontradas para conter malware por verificação de documentos seguros (não estamos usando o parâmetro _Action_ , e o valor padrão é `Block` ).</span><span class="sxs-lookup"><span data-stu-id="29b4e-240">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="29b4e-241">O redirecionamento é habilitado, e as mensagens que são encontradas para conter malware são enviadas para o sec-ops@contoso.com para análise e investigação.</span><span class="sxs-lookup"><span data-stu-id="29b4e-241">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="29b4e-242">Se a verificação de anexos seguros não estiver disponível ou encontrar erros, não entregue a mensagem (não estamos usando o parâmetro _ActionOnError_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="29b4e-242">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="29b4e-243">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="29b4e-243">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="29b4e-244">Etapa 2: usar o PowerShell para criar uma regra de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="29b4e-244">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="29b4e-245">Para criar uma regra de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="29b4e-245">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="29b4e-246">Este exemplo cria uma regra de anexo seguro chamada contoso todos com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="29b4e-246">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="29b4e-247">A regra é associada à política de anexo seguro chamada contoso ALL.</span><span class="sxs-lookup"><span data-stu-id="29b4e-247">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="29b4e-248">A regra se aplica a todos os destinatários no domínio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="29b4e-248">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="29b4e-249">Como não estamos usando o parâmetro _Priority_ , a prioridade padrão é usada.</span><span class="sxs-lookup"><span data-stu-id="29b4e-249">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="29b4e-250">A regra está habilitada (não estamos usando o parâmetro _Enabled_ e o valor padrão é `$true` ).</span><span class="sxs-lookup"><span data-stu-id="29b4e-250">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="29b4e-251">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="29b4e-251">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="29b4e-252">Usar o PowerShell para exibir políticas de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="29b4e-252">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="29b4e-253">Para exibir as políticas de anexo seguro existentes, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="29b4e-253">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="29b4e-254">Este exemplo retorna uma lista resumida de todas as políticas de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="29b4e-254">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="29b4e-255">Este exemplo retorna informações detalhadas sobre a política de anexo seguro chamada executivos da contoso.</span><span class="sxs-lookup"><span data-stu-id="29b4e-255">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="29b4e-256">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="29b4e-256">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="29b4e-257">Usar o PowerShell para exibir regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="29b4e-257">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="29b4e-258">Para exibir as regras de anexo seguro existentes, use a sintaxe a seguir:</span><span class="sxs-lookup"><span data-stu-id="29b4e-258">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="29b4e-259">Este exemplo retorna uma lista resumida de todas as regras de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="29b4e-259">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="29b4e-260">Para filtrar a lista por regras habilitadas ou desabilitadas, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="29b4e-260">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="29b4e-261">Este exemplo retorna informações detalhadas sobre a regra de anexo seguro chamada executivos da contoso.</span><span class="sxs-lookup"><span data-stu-id="29b4e-261">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="29b4e-262">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="29b4e-262">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="29b4e-263">Usar o PowerShell para modificar políticas de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="29b4e-263">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="29b4e-264">Não é possível renomear uma política de anexo seguro no PowerShell (o cmdlet **set-SafeAttachmentPolicy** não tem nenhum parâmetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="29b4e-264">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="29b4e-265">Ao renomear uma política de anexos seguros no centro de conformidade e segurança &, você estará apenas renomeando a _regra_ de anexo seguro.</span><span class="sxs-lookup"><span data-stu-id="29b4e-265">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="29b4e-266">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma política de anexo seguro, conforme descrito na seção [etapa 1: usar o PowerShell para criar uma política de anexo seguro](#step-1-use-powershell-to-create-a-safe-attachment-policy) , anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="29b4e-266">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="29b4e-267">Para modificar uma política de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="29b4e-267">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="29b4e-268">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="29b4e-268">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="29b4e-269">Usar o PowerShell para modificar regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="29b4e-269">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="29b4e-270">A única configuração que não está disponível quando você modifica uma regra de anexo seguro no PowerShell é o parâmetro _habilitado_ que permite criar uma regra desabilitada.</span><span class="sxs-lookup"><span data-stu-id="29b4e-270">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="29b4e-271">Para habilitar ou desabilitar regras de anexo seguro existentes, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="29b4e-271">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="29b4e-272">Caso contrário, as mesmas configurações estarão disponíveis quando você criar uma regra, conforme descrito na seção [etapa 2: usar o PowerShell para criar uma regra de anexo seguro](#step-2-use-powershell-to-create-a-safe-attachment-rule) , anteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="29b4e-272">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="29b4e-273">Para modificar uma regra de anexo seguro, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="29b4e-273">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="29b4e-274">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="29b4e-274">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="29b4e-275">Usar o PowerShell para habilitar ou desabilitar regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="29b4e-275">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="29b4e-276">Habilitar ou desabilitar uma regra de anexo seguro no PowerShell habilita ou desabilita toda a política de anexos seguros (a regra de anexo seguro e a política de anexo seguro atribuída).</span><span class="sxs-lookup"><span data-stu-id="29b4e-276">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="29b4e-277">Para habilitar ou desabilitar uma regra de anexo seguro no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="29b4e-277">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="29b4e-278">Este exemplo desabilita a regra de anexo seguro chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="29b4e-278">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="29b4e-279">Este exemplo habilita a mesma regra.</span><span class="sxs-lookup"><span data-stu-id="29b4e-279">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="29b4e-280">Para informações detalhadas de sintaxes e de parâmetros, consulte [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) e [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="29b4e-280">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="29b4e-281">Usar o PowerShell para definir a prioridade das regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="29b4e-281">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="29b4e-282">O valor mais alto de prioridade que pode ser definido em uma regra é 0.</span><span class="sxs-lookup"><span data-stu-id="29b4e-282">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="29b4e-283">O valor mais baixo que pode ser definido depende do número de regras.</span><span class="sxs-lookup"><span data-stu-id="29b4e-283">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="29b4e-284">Por exemplo, se você tiver cinco regras, use os valores de prioridade de 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="29b4e-284">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="29b4e-285">Alterar a prioridade de uma regra existente pode ter um efeito cascata em outras regras.</span><span class="sxs-lookup"><span data-stu-id="29b4e-285">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="29b4e-286">Por exemplo, se você tiver cinco regras personalizadas (prioridades de 0 a 4) e alterar a prioridade de uma regra para 2, a regra existente com prioridade 2 será alterada para a prioridade 3, e a regra com prioridade 3 será alterada para prioridade 4.</span><span class="sxs-lookup"><span data-stu-id="29b4e-286">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="29b4e-287">Para definir a prioridade de uma regra de anexo seguro no PowerShell, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="29b4e-287">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="29b4e-288">Este exemplo define a prioridade da regra chamada Marketing Department como 2.</span><span class="sxs-lookup"><span data-stu-id="29b4e-288">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="29b4e-289">Todas as regras existentes com prioridade inferior ou igual a 2 são reduzidas por 1 (seus números de prioridade são aumentados por 1).</span><span class="sxs-lookup"><span data-stu-id="29b4e-289">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="29b4e-290">**Observação** : para definir a prioridade de uma nova regra ao criá-la, use o parâmetro _Priority_ no cmdlet **New-SafeAttachmentRule** .</span><span class="sxs-lookup"><span data-stu-id="29b4e-290">**Note** : To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="29b4e-291">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="29b4e-291">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="29b4e-292">Usar o PowerShell para remover políticas de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="29b4e-292">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="29b4e-293">Quando você usa o PowerShell para remover uma política de anexo seguro, a regra de anexo seguro correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="29b4e-293">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="29b4e-294">Para remover uma política de anexo seguro no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="29b4e-294">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="29b4e-295">Este exemplo remove a política de anexo seguro chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="29b4e-295">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="29b4e-296">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="29b4e-296">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="29b4e-297">Usar o PowerShell para remover regras de anexo seguro</span><span class="sxs-lookup"><span data-stu-id="29b4e-297">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="29b4e-298">Quando você usa o PowerShell para remover uma regra de anexo seguro, a política de anexo seguro correspondente não é removida.</span><span class="sxs-lookup"><span data-stu-id="29b4e-298">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="29b4e-299">Para remover uma regra de anexo seguro no PowerShell, use esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="29b4e-299">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="29b4e-300">Este exemplo remove a regra de anexo seguro chamada departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="29b4e-300">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="29b4e-301">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="29b4e-301">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="29b4e-302">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="29b4e-302">How do you know these procedures worked?</span></span>

<span data-ttu-id="29b4e-303">Para verificar se você criou, modificou ou removeu com êxito as políticas de anexos confiáveis, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="29b4e-303">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="29b4e-304">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**.</span><span class="sxs-lookup"><span data-stu-id="29b4e-304">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="29b4e-305">Verifique a lista de políticas, seus valores de **status** e seus valores de **prioridade** .</span><span class="sxs-lookup"><span data-stu-id="29b4e-305">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="29b4e-306">Para exibir mais detalhes, selecione a política na lista e exiba os detalhes na saída.</span><span class="sxs-lookup"><span data-stu-id="29b4e-306">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="29b4e-307">No PowerShell do Exchange Online ou do Exchange Online Protection, substitua o \<Name\> nome da política ou regra, execute o seguinte comando e verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="29b4e-307">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="29b4e-308">Para verificar se os anexos seguros estão verificando mensagens, confira os relatórios do defender for Office 365 disponíveis.</span><span class="sxs-lookup"><span data-stu-id="29b4e-308">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="29b4e-309">Para obter mais informações, consulte [View Reports for defender for Office 365](view-reports-for-atp.md) e [Use Explorer no centro de conformidade de & de segurança](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="29b4e-309">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
