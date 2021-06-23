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
ms.openlocfilehash: b64b3cfb29b3be999c9e26804e35dc4d02e48fbb
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083087"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="52dd4-103">Ative os anexos seguros para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52dd4-103">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="52dd4-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="52dd4-104">**Applies to**</span></span>
- [<span data-ttu-id="52dd4-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="52dd4-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="52dd4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52dd4-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="52dd4-107">O Microsoft Defender para Office 365 para SharePoint, OneDrive e Microsoft Teams protege sua organização contra o compartilhamento inadvertida de arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="52dd4-107">Microsoft Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="52dd4-108">Para obter mais informações, [consulte Cofre Attachments for SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="52dd4-108">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="52dd4-109">Este artigo contém as etapas para habilenciar e configurar Cofre anexos para SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="52dd4-109">This article contains the steps for enabling and configuring Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="52dd4-110">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="52dd4-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="52dd4-111">Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="52dd4-111">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="52dd4-112">Para ir diretamente para a página **Cofre Anexos,** abra <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="52dd4-112">To go directly to the **Safe Attachments** page, open <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="52dd4-113">Para ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams, você precisa ser membro dos  grupos  de função Gerenciamento da Organização ou Administrador de Segurança no portal Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="52dd4-113">To turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="52dd4-114">Para obter mais informações, veja [Permissões no portal do Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="52dd4-114">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="52dd4-115">Para usar SharePoint PowerShell Online para impedir que as pessoas baixem arquivos mal-intencionados, você precisa ser membro das funções Administrador [Global](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) ou SharePoint [Administrador](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="52dd4-115">To use SharePoint Online PowerShell to prevent people from downloading malicious files, you need to be member of the [Global Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or [SharePoint Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) roles in Azure AD.</span></span>

- <span data-ttu-id="52dd4-116">Verifique se o log de auditoria está habilitado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="52dd4-116">Verify that audit logging is enabled for your organization.</span></span> <span data-ttu-id="52dd4-117">Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="52dd4-117">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="52dd4-118">Permitir até 30 minutos para que as configurações entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="52dd4-118">Allow up to 30 minutes for the settings to take effect.</span></span>

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="52dd4-119">Etapa 1: use o portal Microsoft 365 Defender para ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52dd4-119">Step 1: Use the Microsoft 365 Defender portal to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

1. <span data-ttu-id="52dd4-120">No portal Microsoft 365 Defender, vá para Políticas & **políticas** políticas de ameaça \>  \>  seção \> **Cofre Anexos**.</span><span class="sxs-lookup"><span data-stu-id="52dd4-120">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="52dd4-121">Na página **Cofre Anexos,** clique em **Configurações globais**.</span><span class="sxs-lookup"><span data-stu-id="52dd4-121">On the **Safe Attachments** page, click **Global settings**.</span></span>

3. <span data-ttu-id="52dd4-122">Na seção **Configurações globais** que aparecem, vá para a seção Proteger arquivos **SharePoint, OneDrive e Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="52dd4-122">In the **Global settings** fly out that appears, go to the **Protect files in SharePoint, OneDrive, and Microsoft Teams** section.</span></span>

   <span data-ttu-id="52dd4-123">Mova Office 365 Ativar o Defender para **SharePoint, OneDrive** e Microsoft Teams alternar para a Microsoft Teams direita para ativar o Cofre Attachments para SharePoint, OneDrive e ![ ](../../media/scc-toggle-on.png) Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="52dd4-123">Move the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** toggle to the right ![Toggle on](../../media/scc-toggle-on.png) to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   <span data-ttu-id="52dd4-124">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="52dd4-124">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="52dd4-125">Use Exchange Online PowerShell para ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="52dd4-125">Use Exchange Online PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="52dd4-126">Se você preferir usar o PowerShell para ativar o Cofre Attachments para SharePoint, OneDrive e Microsoft Teams, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="52dd4-126">If you'd rather use PowerShell to turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

<span data-ttu-id="52dd4-127">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="52dd4-127">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a><span data-ttu-id="52dd4-128">Etapa 2: (Recomendado) Use SharePoint PowerShell Online para impedir que os usuários baixem arquivos mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="52dd4-128">Step 2: (Recommended) Use SharePoint Online PowerShell to prevent users from downloading malicious files</span></span>

<span data-ttu-id="52dd4-129">Por padrão, os usuários não podem abrir, mover, copiar ou compartilhar arquivos <sup>\*</sup> mal-intencionados detectados pelo Cofre Attachments para SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="52dd4-129">By default, users can't open, move, copy, or share<sup>\*</sup> malicious files that are detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="52dd4-130">No entanto, eles podem excluir e baixar arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="52dd4-130">However, they can delete and download malicious files.</span></span>

<span data-ttu-id="52dd4-131"><sup>\*</sup> Se os usuários **acessam Gerenciar acesso,** a opção **Compartilhar** ainda estará disponível.</span><span class="sxs-lookup"><span data-stu-id="52dd4-131"><sup>\*</sup> If users go to **Manage access**, the **Share** option is still available.</span></span>

<span data-ttu-id="52dd4-132">Para impedir que os usuários baixem arquivos mal-intencionados, [conecte-se SharePoint PowerShell Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="52dd4-132">To prevent users from downloading malicious files, [connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and run the following command:</span></span>

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

<span data-ttu-id="52dd4-133">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="52dd4-133">**Notes**:</span></span>

- <span data-ttu-id="52dd4-134">Essa configuração afeta usuários e administradores.</span><span class="sxs-lookup"><span data-stu-id="52dd4-134">This setting affects both users and admins.</span></span>
- <span data-ttu-id="52dd4-135">As pessoas ainda podem excluir arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="52dd4-135">People can still delete malicious files.</span></span>

<span data-ttu-id="52dd4-136">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="52dd4-136">For detailed syntax and parameter information, see [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="52dd4-137">Etapa 3 (Recomendado) Use o portal Microsoft 365 Defender para criar uma política de alerta para arquivos detectados</span><span class="sxs-lookup"><span data-stu-id="52dd4-137">Step 3 (Recommended) Use the Microsoft 365 Defender portal to create an alert policy for detected files</span></span>

<span data-ttu-id="52dd4-138">Você pode criar uma política de alerta que notifica você e outros administradores quando Cofre anexos para SharePoint, OneDrive e Microsoft Teams detecta um arquivo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="52dd4-138">You can create an alert policy that notifies you and other admins when Safe Attachments for SharePoint, OneDrive, and Microsoft Teams detects a malicious file.</span></span> <span data-ttu-id="52dd4-139">Para saber mais sobre alertas, consulte [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="52dd4-139">To learn more about alerts, see [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).</span></span>

1. <span data-ttu-id="52dd4-140">No portal Microsoft 365 Defender, acesse Políticas & **política** \> **de alerta ou** abra <https://security.microsoft.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="52dd4-140">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** or open <https://security.microsoft.com/alertpolicies>.</span></span>

2. <span data-ttu-id="52dd4-141">Na página **Política de alerta,** clique em **Nova política de alerta.**</span><span class="sxs-lookup"><span data-stu-id="52dd4-141">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="52dd4-142">O **assistente nova política de alerta** é aberto em uma saída de emergência. Na página **Nomear seu alerta,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="52dd4-142">The **New alert policy** wizard opens in a fly out. On the **Name your alert** page, configure the following settings:</span></span>
   - <span data-ttu-id="52dd4-143">**Nome**: Digite um nome exclusivo e descritivo.</span><span class="sxs-lookup"><span data-stu-id="52dd4-143">**Name**: Type a unique and descriptive name.</span></span> <span data-ttu-id="52dd4-144">Por exemplo, Arquivos Mal-intencionados em bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="52dd4-144">For example, Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="52dd4-145">**Descrição**: digite uma descrição opcional.</span><span class="sxs-lookup"><span data-stu-id="52dd4-145">**Description**: Type an optional description.</span></span> <span data-ttu-id="52dd4-146">Por exemplo, Notifica os administradores quando arquivos mal-intencionados são detectados no SharePoint Online, OneDrive ou Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="52dd4-146">For example, Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>
   - <span data-ttu-id="52dd4-147">**Severidade**: Selecione **Baixo,** **Médio** ou **Alto** na listada.</span><span class="sxs-lookup"><span data-stu-id="52dd4-147">**Severity**: Select **Low**, **Medium**, or **High** from the drop down list.</span></span>
   - <span data-ttu-id="52dd4-148">**Categoria**: Selecione **Gerenciamento de ameaças** na lista lista listada.</span><span class="sxs-lookup"><span data-stu-id="52dd4-148">**Category**: Select **Threat management** from the drop down list.</span></span>

   <span data-ttu-id="52dd4-149">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="52dd4-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="52dd4-150">Na página **Criar configurações de** alerta, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="52dd4-150">On the **Create alert settings** page, configure the following settings:</span></span>
   - <span data-ttu-id="52dd4-151">**O que você deseja alertar?** section \> **Activity is** \> Select **Detected malware in file** from the drop down list.</span><span class="sxs-lookup"><span data-stu-id="52dd4-151">**What do you want to alert on?** section \> **Activity is** \> Select **Detected malware in file** from the drop down list.</span></span>
   - <span data-ttu-id="52dd4-152">**Como deseja que o alerta seja acionado?** seção: Deixe o valor padrão **Sempre que uma atividade corresponde à regra** selecionada.</span><span class="sxs-lookup"><span data-stu-id="52dd4-152">**How do you want the alert to be triggered?** section: Leave the default value **Every time an activity matches the rule** selected.</span></span>

   <span data-ttu-id="52dd4-153">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="52dd4-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="52dd4-154">Na página **Definir seus destinatários,** configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="52dd4-154">On the **Set your recipients** page, configure the following settings:</span></span>
   - <span data-ttu-id="52dd4-155">Verifique **se As notificações de email de** envio estão selecionadas.</span><span class="sxs-lookup"><span data-stu-id="52dd4-155">Verify **Send email notifications** is selected.</span></span> <span data-ttu-id="52dd4-156">Na caixa **Destinatários de** email, selecione um ou mais administradores globais, administradores de segurança ou leitores de segurança que devem receber notificação quando um arquivo mal-intencionado for detectado.</span><span class="sxs-lookup"><span data-stu-id="52dd4-156">In the **Email recipients** box, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="52dd4-157">**Limite de notificação diário**: Deixar o valor padrão **Nenhum limite** selecionado.</span><span class="sxs-lookup"><span data-stu-id="52dd4-157">**Daily notification limit**: Leave the default value **No limit** selected.</span></span>

   <span data-ttu-id="52dd4-158">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="52dd4-158">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="52dd4-159">Na página **Revisar suas configurações,** revise suas configurações.</span><span class="sxs-lookup"><span data-stu-id="52dd4-159">On the **Review your settings** page, review your settings.</span></span> <span data-ttu-id="52dd4-160">Você pode selecionar **Editar** em cada seção para modificar as configurações da seção.</span><span class="sxs-lookup"><span data-stu-id="52dd4-160">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="52dd4-161">Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.</span><span class="sxs-lookup"><span data-stu-id="52dd4-161">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="52dd4-162">Na seção Deseja ativar a política **imediatamente?** Deixe o valor padrão Sim, a a ligue **imediatamente selecionada.**</span><span class="sxs-lookup"><span data-stu-id="52dd4-162">In the **Do you want to turn the policy on right away?** section, leave the default value **Yes, turn it on right away** selected.</span></span>

   <span data-ttu-id="52dd4-163">Quando terminar, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="52dd4-163">When you're finished, click **Finish**.</span></span>

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a><span data-ttu-id="52dd4-164">Usar o & de Conformidade do PowerShell para criar uma política de alerta para arquivos detectados</span><span class="sxs-lookup"><span data-stu-id="52dd4-164">Use Security & Compliance PowerShell to create an alert policy for detected files</span></span>

<span data-ttu-id="52dd4-165">Se você preferir usar o PowerShell para criar a mesma política de alerta conforme descrito na seção anterior &, conecte-se ao Centro de Conformidade e Segurança do [PowerShell](/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="52dd4-165">If you'd rather use PowerShell to create the same alert policy as described in the previous section, [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command:</span></span>

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

<span data-ttu-id="52dd4-166">**Observação**: o valor _padrão severity_ é Low.</span><span class="sxs-lookup"><span data-stu-id="52dd4-166">**Note**: The default _Severity_ value is Low.</span></span> <span data-ttu-id="52dd4-167">Para especificar Médio ou Alto, inclua o parâmetro _Severity_ e o valor no comando.</span><span class="sxs-lookup"><span data-stu-id="52dd4-167">To specify Medium or High, include the _Severity_ parameter and value in the command.</span></span>

<span data-ttu-id="52dd4-168">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span><span class="sxs-lookup"><span data-stu-id="52dd4-168">For detailed syntax and parameter information, see [New-ActivityAlert](/powershell/module/exchange/new-activityalert).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="52dd4-169">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="52dd4-169">How do you know these procedures worked?</span></span>

- <span data-ttu-id="52dd4-170">Para verificar se você a Cofre anexos para SharePoint, OneDrive e Microsoft Teams, use uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="52dd4-170">To verify that you've successfully turned on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, use either of the following steps:</span></span>

  - <span data-ttu-id="52dd4-171">No portal Microsoft 365 Defender, vá até  Políticas & regras Políticas de Políticas de Ameaças seção \>  \>  \> **Cofre Anexos,** selecione **Configurações** Globais e verifique o valor da configuração Ativar o Defender para Office 365 para **SharePoint, OneDrive** e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="52dd4-171">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Attachments**, select **Global settings**, and verify the value of the **Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams** setting.</span></span>

  - <span data-ttu-id="52dd4-172">No Exchange Online PowerShell, execute o seguinte comando para verificar a configuração da propriedade:</span><span class="sxs-lookup"><span data-stu-id="52dd4-172">In Exchange Online PowerShell, run the following command to verify the property setting:</span></span>

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    <span data-ttu-id="52dd4-173">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="52dd4-173">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>

- <span data-ttu-id="52dd4-174">Para verificar se você bloqueou com êxito as pessoas de baixar arquivos mal-intencionados, abra SharePoint PowerShell Online e execute o seguinte comando para verificar o valor da propriedade:</span><span class="sxs-lookup"><span data-stu-id="52dd4-174">To verify that you've successfully blocked people from downloading malicious files, open SharePoint Online PowerShell, and run the following command to verify the property value:</span></span>

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  <span data-ttu-id="52dd4-175">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span><span class="sxs-lookup"><span data-stu-id="52dd4-175">For detailed syntax and parameter information, see [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>

- <span data-ttu-id="52dd4-176">Para verificar se você configurou com êxito uma política de alerta para arquivos detectados, use qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="52dd4-176">To verify that you've successfully configured an alert policy for detected files, use any of the following steps:</span></span>
  - <span data-ttu-id="52dd4-177">No portal Microsoft 365 Defender, vá para Políticas & Política de alerta selecione **a** política de alerta e verifique \>  \> as configurações.</span><span class="sxs-lookup"><span data-stu-id="52dd4-177">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Alert policy** \> select the alert policy, and verify the settings.</span></span>
  - <span data-ttu-id="52dd4-178">No Microsoft 365 Defender portal PowerShell, substitua pelo nome da política de alerta, execute o seguinte comando e \<AlertPolicyName\> verifique os valores da propriedade:</span><span class="sxs-lookup"><span data-stu-id="52dd4-178">In Microsoft 365 Defender portal PowerShell, replace \<AlertPolicyName\> with the name of the alert policy, run the following command, and verify the property values:</span></span>

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    <span data-ttu-id="52dd4-179">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span><span class="sxs-lookup"><span data-stu-id="52dd4-179">For detailed syntax and parameter information, see [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).</span></span>

- <span data-ttu-id="52dd4-180">Use o [relatório de status de proteção](view-email-security-reports.md#threat-protection-status-report) contra ameaças para exibir informações sobre arquivos detectados em SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="52dd4-180">Use the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report) to view information about detected files in SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="52dd4-181">Especificamente, você pode usar o **view data by: Content \> Malware** view.</span><span class="sxs-lookup"><span data-stu-id="52dd4-181">Specifically, you can use the **View data by: Content \> Malware** view.</span></span>
