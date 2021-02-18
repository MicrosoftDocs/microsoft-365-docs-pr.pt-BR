---
title: Ative os anexos seguros para SharePoint, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Os administradores podem aprender a ativar anexos seguros para o SharePoint, o OneDrive e o Microsoft Teams, incluindo como definir alertas para arquivos detectados.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9688af82d194b1818d6bd3323d39bde51db20cb2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286364"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="2a111-103">Ative os anexos seguros para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a111-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2a111-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="2a111-104">**Applies to**</span></span>
- [<span data-ttu-id="2a111-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2a111-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="2a111-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a111-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="2a111-107">O Microsoft Defender para Office 365 para SharePoint, OneDrive e Microsoft Teams protege sua organização contra o compartilhamento inadvertido de arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="2a111-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="2a111-108">Para saber mais, confira [Anexos seguros para SharePoint, OneDrive e Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="2a111-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="2a111-109">Este artigo contém as etapas de habilitação e configuração de Anexos Seguros para o SharePoint, o OneDrive e o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2a111-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2a111-110">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="2a111-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2a111-111">Abra o Centro de Conformidade e Segurança em <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="2a111-111">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="2a111-112">Para ir diretamente para a página Anexos Seguros da **ATP,** <https://protection.office.com/safeattachmentv2> abra.</span><span class="sxs-lookup"><span data-stu-id="2a111-112">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="2a111-113">Para ativar anexos seguros para o SharePoint, o OneDrive e o  Microsoft  Teams &, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador de Segurança no Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="2a111-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="2a111-114">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2a111-114">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="2a111-115">Para usar o PowerShell do SharePoint Online para impedir que as pessoas baixem arquivos mal-intencionados, você precisa ser membro das funções Administrador [Global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) ou Administrador do [SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2a111-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="2a111-116">Verifique se o log de auditoria está habilitado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="2a111-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="2a111-117">Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="2a111-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="2a111-118">Permita até 30 minutos para que as configurações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="2a111-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="2a111-119">Etapa 1: Usar o Centro de Conformidade e Segurança & para ativar o Serviço de Anexos Seguros para o SharePoint, o OneDrive e o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a111-119">Step 1: Use the Security & Compliance Center to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="2a111-120">No Centro de Conformidade & Segurança,  vá para Anexos Seguros da ATP da Política de Gerenciamento de Ameaças e clique em \>  \>  **Configurações Globais.**</span><span class="sxs-lookup"><span data-stu-id="2a111-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="2a111-121">No menu **Configurações** globais exibido, vá para a configuração Ativar o Defender para **Office 365 para SharePoint, OneDrive** e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2a111-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="2a111-122">Mova o alternância para a direita para ativar Anexos Seguros para ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2a111-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="2a111-123">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2a111-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="2a111-124">Usar o PowerShell do Exchange Online para ativar Anexos Seguros para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2a111-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="2a111-125">Se você preferir usar o PowerShell para ativar Anexos Seguros para SharePoint, OneDrive e Microsoft Teams, conecte-se ao [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2a111-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="2a111-126">Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="2a111-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="2a111-127">Etapa 2: (Recomendado) Usar o PowerShell do SharePoint Online para impedir que os usuários baixem arquivos mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="2a111-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="2a111-128">Por padrão, os usuários não podem abrir, mover, copiar ou compartilhar arquivos mal-intencionados detectados pela ATP.</span><span class="sxs-lookup"><span data-stu-id="2a111-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="2a111-129">No entanto, eles podem excluir e baixar arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="2a111-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="2a111-130">Para impedir que os usuários baixem arquivos mal-intencionados, [conecte-se ao PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) do SharePoint Online e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2a111-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="2a111-131">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="2a111-131">**Notes**:</span></span>

- <span data-ttu-id="2a111-132">Essa configuração afeta usuários e administradores.</span><span class="sxs-lookup"><span data-stu-id="2a111-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="2a111-133">As pessoas ainda podem excluir arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="2a111-133">People can still delete malicious files.</span></span>

<span data-ttu-id="2a111-134">Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="2a111-134">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="2a111-135">Etapa 3 (Recomendado) Usar o Centro de Conformidade e Segurança & para criar uma política de alerta para arquivos detectados</span><span class="sxs-lookup"><span data-stu-id="2a111-135">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="2a111-136">Você pode criar uma política de alerta que notifica você e outros administradores quando o serviço Anexos Seguros do SharePoint, OneDrive e Microsoft Teams detecta um arquivo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="2a111-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="2a111-137">Para saber mais sobre alertas, consulte [Criar alertas de atividade no Centro de conformidade & segurança.](../../compliance/create-activity-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="2a111-137">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="2a111-138">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="2a111-138">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="2a111-139">Na página **Políticas de alerta,** clique em **Nova política de alerta.**</span><span class="sxs-lookup"><span data-stu-id="2a111-139">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="2a111-140">O **assistente nova política de** alerta é aberto em um fly out. Na página **Nomear seu alerta,** de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="2a111-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="2a111-141">**Nome:** digite um nome exclusivo e descritivo.</span><span class="sxs-lookup"><span data-stu-id="2a111-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="2a111-142">Por exemplo, arquivos mal-intencionados em bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="2a111-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="2a111-143">**Descrição:** digite uma descrição opcional.</span><span class="sxs-lookup"><span data-stu-id="2a111-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="2a111-144">Por exemplo, notifica os administradores quando arquivos mal-intencionados são detectados no SharePoint Online, No OneDrive ou no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2a111-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="2a111-145">**Gravidade:** deixe o valor **padrão** Baixo selecionado ou selecione **Médio** ou **Alto.**</span><span class="sxs-lookup"><span data-stu-id="2a111-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="2a111-146">**Selecione uma categoria:** Selecione **Gerenciamento de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="2a111-146">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="2a111-147">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2a111-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="2a111-148">Na página **Criar configurações de alerta,** de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="2a111-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="2a111-149">**O que você deseja alertar?: Atividade é:** Selecionar **malware detectado no arquivo.**</span><span class="sxs-lookup"><span data-stu-id="2a111-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="2a111-150">**Como você deseja que o alerta seja disparado?**: Deixe o valor padrão Sempre que uma **atividade corresponde à regra** selecionada.</span><span class="sxs-lookup"><span data-stu-id="2a111-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="2a111-151">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2a111-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="2a111-152">Na página **Definir seus destinatários,** de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="2a111-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="2a111-153">**Enviar notificações por email:** verifique se essa configuração está selecionada.</span><span class="sxs-lookup"><span data-stu-id="2a111-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="2a111-154">Na caixa **Destinatários de email,** selecione um ou mais administradores globais, administradores de segurança ou leitores de segurança que devem receber notificação quando um arquivo mal-intencionado for detectado.</span><span class="sxs-lookup"><span data-stu-id="2a111-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="2a111-155">**Limite de notificação** diária: deixe o valor padrão **Sem limite** selecionado.</span><span class="sxs-lookup"><span data-stu-id="2a111-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="2a111-156">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2a111-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="2a111-157">Na página **Revisar suas configurações,** revise as configurações e clique em **Editar** em qualquer uma das seções para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="2a111-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="2a111-158">Na seção Deseja ativar a política **imediatamente?** Deixe o valor padrão Sim, a ligue **imediatamente selecionado.**</span><span class="sxs-lookup"><span data-stu-id="2a111-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="2a111-159">Quando terminar, clique em **Concluir.**</span><span class="sxs-lookup"><span data-stu-id="2a111-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="2a111-160">Usar o PowerShell & segurança e conformidade para criar uma política de alerta para arquivos detectados</span><span class="sxs-lookup"><span data-stu-id="2a111-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="2a111-161">Se você preferir usar o PowerShell para criar a mesma política de alerta conforme descrito na seção anterior &, conecte-se ao [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) do Centro de Conformidade e Segurança e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2a111-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="2a111-162">**Observação:** o valor _de Severidade_ padrão é Baixo.</span><span class="sxs-lookup"><span data-stu-id="2a111-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="2a111-163">Para especificar Médio ou Alto, inclua o parâmetro _severity_ e o valor no comando.</span><span class="sxs-lookup"><span data-stu-id="2a111-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="2a111-164">Para informações detalhadas de sintaxes e de parâmetros, [consulte New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="2a111-164">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="2a111-165">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="2a111-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="2a111-166">Para verificar se você ativas com êxito os Anexos Seguros para o SharePoint, o OneDrive e o Microsoft Teams, use uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="2a111-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="2a111-167">No Centro de Conformidade [&](https://protection.office.com)Segurança,  vá para Anexos Seguros da POLÍTICA de Gerenciamento de Ameaças da ATP, selecione Configurações Globais e verifique o valor da configuração Ativar o \>  \> Defender para **Office 365 para SharePoint, OneDrive** e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2a111-167">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="2a111-168">No PowerShell do Exchange Online, execute o seguinte comando para verificar a configuração da propriedade:</span><span class="sxs-lookup"><span data-stu-id="2a111-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="2a111-169">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="2a111-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="2a111-170">Para verificar se você bloqueou com êxito as pessoas de baixar arquivos mal-intencionados, abra o PowerShell do SharePoint Online e execute o seguinte comando para verificar o valor da propriedade:</span><span class="sxs-lookup"><span data-stu-id="2a111-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="2a111-171">Para informações detalhadas de sintaxes e de parâmetros, [consulte Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="2a111-171">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="2a111-172">Para verificar se você configurou com êxito uma política de alerta para arquivos detectados, use uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="2a111-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="2a111-173">No Centro de Conformidade & Segurança, vá para Políticas de **Alertas** e selecione a política de alerta e \>  \> verifique as configurações.</span><span class="sxs-lookup"><span data-stu-id="2a111-173">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="2a111-174">No PowerShell & Centro de Conformidade e Segurança, substitua pelo nome da política de alerta, execute o seguinte comando e \<AlertPolicyName\> verifique os valores de propriedade:</span><span class="sxs-lookup"><span data-stu-id="2a111-174">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="2a111-175">Para informações detalhadas de sintaxes e de parâmetros, [consulte Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="2a111-175">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="2a111-176">Use o [relatório de status de](view-email-security-reports.md#threat-protection-status-report) proteção contra ameaças para exibir informações sobre arquivos detectados no SharePoint, No OneDrive e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2a111-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="2a111-177">Especificamente, você pode usar o **view data by: Content \> Malware** view.</span><span class="sxs-lookup"><span data-stu-id="2a111-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
