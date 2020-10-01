---
title: Ativar o Office 365 ATP-SharePoint, OneDrive & Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Saiba como ativar a ATP para SharePoint, OneDrive e Teams, incluindo como definir alertas para arquivos detectados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1cd345ae74b81c23f92b9e9b7d712efa8b875503
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326896"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="6e997-103">Ative a ATP para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e997-103">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6e997-104">A proteção avançada contra ameaças do Office 365 (ATP) para o SharePoint, o OneDrive e o Microsoft Teams protege sua organização contra o compartilhamento inadvertidamente de arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="6e997-104">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="6e997-105">Para obter mais informações, consulte [ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6e997-105">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="6e997-106">Este artigo contém as etapas para habilitar e configurar a ATP para SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6e997-106">This article contains the steps for enabling and configuring ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6e997-107">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="6e997-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6e997-108">Abra o Centro de Conformidade e Segurança em <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="6e997-108">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="6e997-109">Para ir diretamente para a página de **anexos seguros de ATP** , abra <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="6e997-109">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="6e997-110">Para ativar a ATP para SharePoint, OneDrive e Microsoft Teams, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="6e997-110">To turn on ATP for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="6e997-111">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6e997-111">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="6e997-112">Para usar o PowerShell do SharePoint Online para impedir que as pessoas baixem arquivos mal-intencionados, você precisa ser membro das funções administrador [global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) ou [administrador do SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6e997-112">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="6e997-113">Verifique se o log de auditoria está habilitado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="6e997-113">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="6e997-114">Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="6e997-114">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="6e997-115">Aguarde até 30 minutos para que as configurações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="6e997-115">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="6e997-116">Etapa 1: usar o centro de conformidade de & de segurança para ativar a ATP para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e997-116">Step 1: Use the Security & Compliance Center to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="6e997-117">No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** \> **Policy** \> e **anexos seguros de ATP**e clique em **configurações globais**.</span><span class="sxs-lookup"><span data-stu-id="6e997-117">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="6e997-118">Nas **configurações globais** que aparecem, vá para a configuração ativar a **ATP para SharePoint, onedrive e Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="6e997-118">In the **Global settings** fly out that appears, go to the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="6e997-119">Mova o botão de alternância para a direita ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) para ativar a ATP para SharePoint, onedrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6e997-119">Move the toggle to the right ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) to turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="6e997-120">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6e997-120">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="6e997-121">Usar o PowerShell do Exchange Online para ativar a ATP para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e997-121">Use Exchange Online PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="6e997-122">Se preferir usar o PowerShell para ativar a ATP para SharePoint, OneDrive e Microsoft Teams, [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="6e997-122">If you'd rather use PowerShell to turn on ATP for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="6e997-123">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="6e997-123">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="6e997-124">Etapa 2: (recomendado) usar o SharePoint Online PowerShell para impedir que os usuários baixem arquivos mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="6e997-124">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="6e997-125">Por padrão, os usuários não podem abrir, mover, copiar ou compartilhar arquivos mal-intencionados detectados pela ATP.</span><span class="sxs-lookup"><span data-stu-id="6e997-125">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="6e997-126">No entanto, eles podem excluir e baixar arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="6e997-126">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="6e997-127">Para impedir que os usuários baixem arquivos mal-intencionados, [Conecte-se ao PowerShell do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="6e997-127">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="6e997-128">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="6e997-128">**Notes**:</span></span>

- <span data-ttu-id="6e997-129">Essa configuração afeta tanto usuários quanto administradores.</span><span class="sxs-lookup"><span data-stu-id="6e997-129">This setting affects both users and admins.</span></span>
- <span data-ttu-id="6e997-130">As pessoas ainda podem excluir arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="6e997-130">People can still delete malicious files.</span></span>

<span data-ttu-id="6e997-131">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="6e997-131">For detailed syntax and parameter information, see [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="6e997-132">Etapa 3 (recomendado) usar o centro de conformidade de & de segurança para criar uma política de alerta para arquivos detectados</span><span class="sxs-lookup"><span data-stu-id="6e997-132">Step 3 (Recommended) Use the Security & Compliance Center to create an alert policy for detected files</span></span>

<span data-ttu-id="6e997-133">Você pode criar uma política de alerta que notifique você e outros administradores quando a ATP para SharePoint, OneDrive e Microsoft Teams detectar um arquivo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="6e997-133">You can create an alert policy that notifies you and other admins when ATP for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="6e997-134">Para saber mais sobre alertas, confira [criar alertas de atividade no centro de conformidade de & de segurança](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="6e997-134">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="6e997-135">No [centro de conformidade & segurança](https://protection.office.com), vá para **Alerts** \> **políticas de alerta** de alertas ou abrir <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="6e997-135">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="6e997-136">Na página **políticas de alerta** , clique em **nova política de alerta**.</span><span class="sxs-lookup"><span data-stu-id="6e997-136">On the **Alert policies** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="6e997-137">O **novo** assistente de política de alerta é aberto em uma saída. Na página **nomear o alerta** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="6e997-137">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="6e997-138">**Name**: digite um nome exclusivo e descritivo.</span><span class="sxs-lookup"><span data-stu-id="6e997-138">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="6e997-139">Por exemplo, arquivos mal-intencionados em bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="6e997-139">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="6e997-140">**Descrição**: digite uma descrição opcional.</span><span class="sxs-lookup"><span data-stu-id="6e997-140">**Description**: Type an optional description.</span></span> <span data-ttu-id="6e997-141">Por exemplo, notifica os administradores quando arquivos mal-intencionados são detectados no SharePoint Online, no OneDrive ou no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6e997-141">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="6e997-142">**Severidade**: Deixe o valor padrão **baixo** selecionado ou selecione **médio** ou **alto**.</span><span class="sxs-lookup"><span data-stu-id="6e997-142">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="6e997-143">**Selecione uma categoria**: selecione **Gerenciamento de ameaças**.</span><span class="sxs-lookup"><span data-stu-id="6e997-143">**Select a category**: Select **Threat management**.</span></span>

   <span data-ttu-id="6e997-144">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6e997-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6e997-145">Na página **criar configurações de alerta** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="6e997-145">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="6e997-146">**O que você deseja alertar?: a atividade é**: selecione **malware detectado no arquivo**.</span><span class="sxs-lookup"><span data-stu-id="6e997-146">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="6e997-147">**Como você deseja que o alerta seja disparado?**: Deixe o valor padrão **sempre que uma atividade corresponder à regra** selecionada.</span><span class="sxs-lookup"><span data-stu-id="6e997-147">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="6e997-148">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6e997-148">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6e997-149">Na página **definir seus destinatários** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="6e997-149">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="6e997-150">**Enviar notificações por email**: Verifique se essa configuração está selecionada.</span><span class="sxs-lookup"><span data-stu-id="6e997-150">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="6e997-151">Na caixa **destinatários de email** , selecione um ou mais administradores globais, administradores de segurança ou leitores de segurança que devem receber notificações quando um arquivo mal-intencionado for detectado.</span><span class="sxs-lookup"><span data-stu-id="6e997-151">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="6e997-152">**Limite diário de notificação**: Deixe o valor padrão **sem limite** selecionado.</span><span class="sxs-lookup"><span data-stu-id="6e997-152">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="6e997-153">Quando terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6e997-153">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6e997-154">Na página **revise Your Settings** , revise as configurações e clique em **Editar** em qualquer uma das seções para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="6e997-154">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="6e997-155">Na seção **você deseja ativar a política imediatamente?** , deixe o valor padrão **Sim, ative-o ao lado direito** .</span><span class="sxs-lookup"><span data-stu-id="6e997-155">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="6e997-156">Quando tiver concluído, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="6e997-156">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="6e997-157">Usar o Security & Compliance PowerShell para criar uma política de alerta para arquivos detectados</span><span class="sxs-lookup"><span data-stu-id="6e997-157">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="6e997-158">Se preferir usar o PowerShell para criar a mesma política de alerta, conforme descrito na seção anterior, [Conecte-se ao PowerShell do centro de conformidade de segurança &](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="6e997-158">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="6e997-159">**Observação**: o valor padrão de _severidade_ é baixo.</span><span class="sxs-lookup"><span data-stu-id="6e997-159">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="6e997-160">Para especificar médio ou alto, inclua o parâmetro e o valor de _gravidade_ no comando.</span><span class="sxs-lookup"><span data-stu-id="6e997-160">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="6e997-161">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="6e997-161">For detailed syntax and parameter information, see [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6e997-162">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="6e997-162">How do you know these procedures worked?</span></span>

- <span data-ttu-id="6e997-163">Para verificar se você ativou com êxito a ATP para SharePoint, OneDrive e Microsoft Teams, use uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="6e997-163">To verify that you've successfully turned on ATP for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="6e997-164">No [centro de conformidade & segurança](https://protection.office.com), vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**, selecione **configurações globais**e verifique o valor da configuração **Ativar ATP para SharePoint, onedrive e Microsoft Teams** .</span><span class="sxs-lookup"><span data-stu-id="6e997-164">In the [Security & Compliance Center](https://protection.office.com), go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, select **Global settings**, and verify the value of the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="6e997-165">No PowerShell do Exchange Online, execute o seguinte comando para verificar a configuração da propriedade:</span><span class="sxs-lookup"><span data-stu-id="6e997-165">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="6e997-166">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="6e997-166">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="6e997-167">Para verificar se você bloqueou com êxito as pessoas de baixar arquivos mal-intencionados, abra o PowerShell do SharePoint Online e execute o seguinte comando para verificar o valor da propriedade:</span><span class="sxs-lookup"><span data-stu-id="6e997-167">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="6e997-168">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="6e997-168">For detailed syntax and parameter information, see [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="6e997-169">Para verificar se você configurou com êxito uma política de alerta para arquivos detectados, use qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="6e997-169">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="6e997-170">No centro de conformidade & segurança, vá para **alertas** \> **regras** \> de alerta selecione a política de alerta e verifique as configurações.</span><span class="sxs-lookup"><span data-stu-id="6e997-170">In the Security & Compliance Center, go to **Alerts** \> **Alert policies** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="6e997-171">Em segurança & o PowerShell do centro de conformidade, substitua o \<AlertPolicyName\> nome da política de alerta, execute o seguinte comando e verifique os valores de propriedade:</span><span class="sxs-lookup"><span data-stu-id="6e997-171">In Security & Compliance Center PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="6e997-172">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="6e997-172">For detailed syntax and parameter information, see [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="6e997-173">Use o [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report) para exibir informações sobre arquivos detectados no SharePoint, no onedrive e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6e997-173">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="6e997-174">Especificamente, você pode usar o modo de exibição **exibir dados por: conteúdo de \> malware** .</span><span class="sxs-lookup"><span data-stu-id="6e997-174">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
