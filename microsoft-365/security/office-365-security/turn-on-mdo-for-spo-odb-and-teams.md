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
description: Os administradores podem aprender a ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams, incluindo como definir alertas para arquivos detectados.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 374e67626eab07cc8ab89a52554658a31e661eec
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929942"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="8b1ef-103">Ative os anexos seguros para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8b1ef-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8b1ef-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="8b1ef-104">**Applies to**</span></span>
- [<span data-ttu-id="8b1ef-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="8b1ef-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8b1ef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b1ef-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8b1ef-107">O Microsoft Defender para Office 365 para SharePoint, OneDrive e Microsoft Teams protege sua organização contra o compartilhamento inadvertida de arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="8b1ef-108">Para obter mais informações, [consulte Cofre Attachments for SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8b1ef-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="8b1ef-109">Este artigo contém as etapas para habilenciar e configurar Cofre anexos para SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8b1ef-110">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="8b1ef-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8b1ef-111">Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="8b1ef-112">Para ir diretamente para a página **Cofre Anexos,** abra <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="8b1ef-112">To go directly to the **Safe Attachments** page, open <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="8b1ef-113">Para ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams, você precisa ser membro dos grupos  de função  Gerenciamento da Organização ou Administrador de Segurança no portal do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="8b1ef-114">Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8b1ef-114">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="8b1ef-115">Para usar SharePoint PowerShell Online para impedir que as pessoas baixem arquivos mal-intencionados, você precisa ser membro das funções Administrador [Global](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) ou SharePoint [Administrador](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="8b1ef-116">Verifique se o log de auditoria está habilitado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="8b1ef-117">Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="8b1ef-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="8b1ef-118">Permitir até 30 minutos para que as configurações entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="8b1ef-119">Etapa 1: use o portal Microsoft 365 Defender para ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8b1ef-119">Step 1: Use the Microsoft 365 Defender portal to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="8b1ef-120">No portal Microsoft 365 Defender, acesse **Políticas** & regras Políticas de ameaça Cofre anexos e clique em \>  \>  **Configurações globais**.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-120">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe attachments**, and click **Global settings**.</span></span>

2. <span data-ttu-id="8b1ef-121">Na **configuração Global** que aparece, vá para a configuração Ativar o Defender para Office 365 **para SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="8b1ef-121">In the **Global settings** fly out that appears, go to the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span> <span data-ttu-id="8b1ef-122">Mova a alternância para a direita Para ativar a Cofre anexos para ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-122">Move the toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="8b1ef-123">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-123">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="8b1ef-124">Use Exchange Online PowerShell para ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8b1ef-124">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="8b1ef-125">Se você preferir usar o PowerShell para ativar o Cofre Attachments para SharePoint, OneDrive e Microsoft Teams, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8b1ef-125">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="8b1ef-126">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="8b1ef-126">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="8b1ef-127">Etapa 2: (Recomendado) Use SharePoint PowerShell Online para impedir que os usuários baixem arquivos mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="8b1ef-127">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="8b1ef-128">Por padrão, os usuários não podem abrir, mover, copiar ou compartilhar arquivos mal-intencionados detectados pela ATP.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-128">By default, users can't open, move, copy, or share malicious files that are detected by ATP.</span></span> <span data-ttu-id="8b1ef-129">No entanto, eles podem excluir e baixar arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-129">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="8b1ef-130">Para impedir que os usuários baixem arquivos mal-intencionados, [conecte-se SharePoint PowerShell Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8b1ef-130">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="8b1ef-131">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="8b1ef-131">**Notes**:</span></span>

- <span data-ttu-id="8b1ef-132">Essa configuração afeta usuários e administradores.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-132">This setting affects both users and admins.</span></span>
- <span data-ttu-id="8b1ef-133">As pessoas ainda podem excluir arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-133">People can still delete malicious files.</span></span>

<span data-ttu-id="8b1ef-134">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="8b1ef-134">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="8b1ef-135">Etapa 3 (Recomendado) Use o portal Microsoft 365 Defender para criar uma política de alerta para arquivos detectados</span><span class="sxs-lookup"><span data-stu-id="8b1ef-135">Step 3 (Recommended) Use the Microsoft 365 Defender portal to create an alert policy for detected files</span></span>

<span data-ttu-id="8b1ef-136">Você pode criar uma política de alerta que notifica você e outros administradores quando Cofre anexos para SharePoint, OneDrive e Microsoft Teams detecta um arquivo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-136">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="8b1ef-137">Para saber mais sobre alertas, consulte [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="8b1ef-137">To learn more about alerts, see [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="8b1ef-138">No portal [Microsoft 365 Defender,](https://security.microsoft.com)vá para **Políticas** & política \> **de alerta** ou abra <https://security.microsoft.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="8b1ef-138">In the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Policies & rules** \> **Alert policy** or open <https://security.microsoft.com/alertpolicies>.</span></span>

2. <span data-ttu-id="8b1ef-139">Na página **Política de alerta,** clique em **Nova política de alerta.**</span><span class="sxs-lookup"><span data-stu-id="8b1ef-139">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="8b1ef-140">O **assistente nova política de alerta** é aberto em uma saída de emergência. Na página **Nomear seu alerta,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8b1ef-140">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>

   - <span data-ttu-id="8b1ef-141">**Nome**: Digite um nome exclusivo e descritivo.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-141">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="8b1ef-142">Por exemplo, Arquivos Mal-intencionados em bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-142">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="8b1ef-143">**Descrição**: digite uma descrição opcional.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-143">**Description**: Type an optional description.</span></span> <span data-ttu-id="8b1ef-144">Por exemplo, Notifica os administradores quando arquivos mal-intencionados são detectados no SharePoint Online, OneDrive ou Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-144">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="8b1ef-145">**Severidade**: deixe o valor padrão **Baixo** selecionado ou selecione **Médio** ou **Alto**.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-145">**Severity**: Leave the default value **Low** selected, or select **Medium** or **High**.</span></span>
   - <span data-ttu-id="8b1ef-146">**Categoria**: Selecione **Gerenciamento de ameaças**.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-146">**Category**: Select **Threat management**.</span></span>

   <span data-ttu-id="8b1ef-147">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-147">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="8b1ef-148">Na página **Criar configurações de** alerta, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8b1ef-148">On the **Create alert settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="8b1ef-149">**O que você deseja alertar?: Atividade é**: Selecionar **malware detectado no arquivo**.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-149">**What do you want to alert on?: Activity is**: Select **Detected malware in file**.</span></span>
   - <span data-ttu-id="8b1ef-150">**Como deseja que o alerta seja acionado?**: Deixar o valor padrão Sempre que uma atividade **corresponde à regra** selecionada.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-150">**How do you want the alert to be triggered?**: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="8b1ef-151">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-151">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="8b1ef-152">Na página **Definir seus destinatários,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8b1ef-152">On the **Set your recipients** page, configure the following settings:</span></span>

   - <span data-ttu-id="8b1ef-153">**Enviar notificações por email**: Verifique se essa configuração está selecionada.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-153">**Send email notifications**: Verify this setting is selected.</span></span> <span data-ttu-id="8b1ef-154">Na caixa **Destinatários de** email, selecione um ou mais administradores globais, administradores de segurança ou leitores de segurança que devem receber notificação quando um arquivo mal-intencionado for detectado.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-154">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="8b1ef-155">**Limite de notificação diário**: Deixar o valor padrão **Nenhum limite** selecionado.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-155">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="8b1ef-156">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-156">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="8b1ef-157">Na página **Revisar suas configurações,** revise as configurações e clique em **Editar** em qualquer uma das seções para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-157">On the **Review your settings** page, review the settings, and click **Edit** in any of the sections to make changes.</span></span>

   <span data-ttu-id="8b1ef-158">Na seção Deseja ativar a política **imediatamente?** Deixe o valor padrão Sim, a a ligue **imediatamente selecionada.**</span><span class="sxs-lookup"><span data-stu-id="8b1ef-158">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="8b1ef-159">Quando terminar, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-159">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="8b1ef-160">Usar o & de Conformidade do PowerShell para criar uma política de alerta para arquivos detectados</span><span class="sxs-lookup"><span data-stu-id="8b1ef-160">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="8b1ef-161">Se você preferir usar o PowerShell para criar a mesma política de alerta conforme descrito na seção anterior &, conecte-se ao Centro de Conformidade e Segurança do [PowerShell](/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8b1ef-161">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="8b1ef-162">**Observação**: o valor _padrão severity_ é Low.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-162">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="8b1ef-163">Para especificar Médio ou Alto, inclua o parâmetro _Severity_ e o valor no comando.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-163">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="8b1ef-164">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="8b1ef-164">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="8b1ef-165">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="8b1ef-165">How do you know these procedures worked?</span></span>

- <span data-ttu-id="8b1ef-166">Para verificar se você a Cofre anexos para SharePoint, OneDrive e Microsoft Teams, use uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="8b1ef-166">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="8b1ef-167">No [portal do Microsoft 365 Defender,](https://security.microsoft.com)  vá para Políticas & regras Políticas de ameaças Cofre \>  \> **anexos,** selecione Configurações globais e verifique o valor da configuração Ativar o Defender para Office 365 para **SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="8b1ef-167">In the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Policies & rules** \> **Threat Policies** \> **Safe attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="8b1ef-168">No Exchange Online PowerShell, execute o seguinte comando para verificar a configuração da propriedade:</span><span class="sxs-lookup"><span data-stu-id="8b1ef-168">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="8b1ef-169">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="8b1ef-169">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="8b1ef-170">Para verificar se você bloqueou com êxito as pessoas de baixar arquivos mal-intencionados, abra SharePoint PowerShell Online e execute o seguinte comando para verificar o valor da propriedade:</span><span class="sxs-lookup"><span data-stu-id="8b1ef-170">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="8b1ef-171">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="8b1ef-171">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="8b1ef-172">Para verificar se você configurou com êxito uma política de alerta para arquivos detectados, use qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="8b1ef-172">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>

  - <span data-ttu-id="8b1ef-173">No portal Microsoft 365 Defender, acesse **Políticas** & Política de alerta selecione a política de alerta e \>  \> verifique as configurações.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-173">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** \> select the alert policy, and verify the settings.</span></span>

  - <span data-ttu-id="8b1ef-174">No Microsoft 365 portal do Defender PowerShell, substitua pelo nome da política de alerta, execute o seguinte comando e \<AlertPolicyName\> verifique os valores da propriedade:</span><span class="sxs-lookup"><span data-stu-id="8b1ef-174">In Microsoft 365 Defender portal PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="8b1ef-175">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="8b1ef-175">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="8b1ef-176">Use o [relatório de status de proteção](view-email-security-reports.md#threat-protection-status-report) contra ameaças para exibir informações sobre arquivos detectados em SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-176">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="8b1ef-177">Especificamente, você pode usar o **view data by: Content \> Malware** view.</span><span class="sxs-lookup"><span data-stu-id="8b1ef-177">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>