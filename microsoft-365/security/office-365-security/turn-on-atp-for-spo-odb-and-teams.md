---
title: Ativar o Office 365 ATP para SharePoint, OneDrive e Microsoft Teams
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
ms.openlocfilehash: 601549db67d34460f4505941d4f2847a2c8f370b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598148"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="637e6-103">Ativar o Office 365 ATP para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="637e6-103">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="637e6-104">Este artigo destina-se aos clientes corporativos que têm a [Proteção Avançada contra Ameaças do Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="637e6-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="637e6-105">Se você for um usuário doméstico que procura informações sobre links seguros no Outlook, consulte [Advanced Outlook.com Security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="637e6-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="637e6-106">O [Office 365 ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md) protege sua organização contra o compartilhamento inadvertidamente de arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="637e6-106">[Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) protects your organization from inadvertently sharing malicious files.</span></span> <span data-ttu-id="637e6-107">Quando um arquivo mal-intencionado é detectado, esse arquivo é bloqueado para que ninguém possa abri-lo, copiá-lo ou compartilhá-lo até que outras ações sejam executadas pela equipe de segurança da organização.</span><span class="sxs-lookup"><span data-stu-id="637e6-107">When a malicious file is detected, that file is blocked so that no one can open, copy, move, or share it until further actions are taken by the organization's security team.</span></span> <span data-ttu-id="637e6-108">Leia este artigo para habilitar a ATP para o SharePoint, o OneDrive e o Microsoft Teams, configure os alertas a serem notificados sobre os arquivos detectados e execute suas próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="637e6-108">Read this article to turn on ATP for SharePoint, OneDrive, and Teams, set up alerts to be notified about detected files, and take your next steps.</span></span>

<span data-ttu-id="637e6-109">Para definir (ou editar) políticas ATP, você deve ter uma função apropriada atribuída.</span><span class="sxs-lookup"><span data-stu-id="637e6-109">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="637e6-110">Alguns exemplos são descritos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="637e6-110">Some examples are described in the following table:</span></span>

|<span data-ttu-id="637e6-111">Role</span><span class="sxs-lookup"><span data-stu-id="637e6-111">Role</span></span>|<span data-ttu-id="637e6-112">Onde/como a atribuição</span><span class="sxs-lookup"><span data-stu-id="637e6-112">Where/how assigned</span></span>|
|---------|---------|
|<span data-ttu-id="637e6-113">Administrador Global do Office 365</span><span class="sxs-lookup"><span data-stu-id="637e6-113">Office 365 Global Administrator</span></span>|<span data-ttu-id="637e6-114">Por padrão, a pessoa que se inscreve para comprar o Office 365 é um administrador global.</span><span class="sxs-lookup"><span data-stu-id="637e6-114">The person who signs up to buy Office 365 is a global admin by default.</span></span> <span data-ttu-id="637e6-115">(Confira [sobre as funções de administrador do Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para saber mais.)</span><span class="sxs-lookup"><span data-stu-id="637e6-115">(See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="637e6-116">Administrador de Segurança</span><span class="sxs-lookup"><span data-stu-id="637e6-116">Security Administrator</span></span>|<span data-ttu-id="637e6-117">Centro de administração do Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ()</span><span class="sxs-lookup"><span data-stu-id="637e6-117">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="637e6-118">Gerenciamento de Organização do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="637e6-118">Exchange Online Organization Management</span></span>|<span data-ttu-id="637e6-119">Centro de administração do[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange ()</span><span class="sxs-lookup"><span data-stu-id="637e6-119">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="637e6-120">ou</span><span class="sxs-lookup"><span data-stu-id="637e6-120">or</span></span> <br>  <span data-ttu-id="637e6-121">Cmdlets do PowerShell (consulte [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="637e6-121">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))</span></span>|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="637e6-122">Ative a ATP para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="637e6-122">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="637e6-123">**Antes de iniciar esse procedimento, verifique se o log de auditoria já está ativado para o seu ambiente do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="637e6-123">**Before you begin this procedure, make sure that audit logging is already turned on for your Office 365 environment**.</span></span> <span data-ttu-id="637e6-124">Isso geralmente é feito por alguém que tenha a função de logs de auditoria atribuída no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="637e6-124">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="637e6-125">Para obter mais informações, consulte [Ativar ou desativar a pesquisa de log de auditoria do Office 365](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="637e6-125">For more information, see [Turn Office 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="637e6-126">Vá até [https://protection.office.com](https://protection.office.com)e entre com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="637e6-126">Go to [https://protection.office.com](https://protection.office.com), and sign in with your work or school account.</span></span>

2. <span data-ttu-id="637e6-127">No centro de conformidade & segurança do Office 365, no painel de navegação esquerdo, **em gerenciamento de ameaças**, escolha **anexos seguros**da **política** \> .</span><span class="sxs-lookup"><span data-stu-id="637e6-127">In the Office 365 Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![No centro de conformidade & segurança, escolha política de \> gerenciamento de ameaças](../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="637e6-129">Selecione **Ativar ATP para SharePoint, onedrive e Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="637e6-129">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![Ativar a proteção avançada contra ameaças para o SharePoint Online, o OneDrive for Business e o Microsoft Teams](../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="637e6-131">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="637e6-131">Click **Save**.</span></span>

5. <span data-ttu-id="637e6-132">Revise (e, conforme apropriado, edite) as [políticas de anexos seguros](set-up-atp-safe-attachments-policies.md) da sua organização e [as políticas de links seguros](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="637e6-132">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="637e6-133">Recomenda Como administrador global ou administrador do SharePoint Online, execute o cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** com o parâmetro _DisallowInfectedFileDownload_ definido como *true*.</span><span class="sxs-lookup"><span data-stu-id="637e6-133">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to *true*.</span></span>

   - <span data-ttu-id="637e6-134">Definir o parâmetro como *true* bloqueia todas as ações (exceto excluir) para arquivos detectados.</span><span class="sxs-lookup"><span data-stu-id="637e6-134">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="637e6-135">As pessoas não podem abrir, mover, copiar ou compartilhar arquivos detectados.</span><span class="sxs-lookup"><span data-stu-id="637e6-135">People cannot open, move, copy, or share detected files.</span></span>

   - <span data-ttu-id="637e6-136">A definição do parâmetro como *false* bloqueia todas as ações, exceto excluir e baixar.</span><span class="sxs-lookup"><span data-stu-id="637e6-136">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="637e6-137">As pessoas podem optar por aceitar o risco e baixar um arquivo detectado.</span><span class="sxs-lookup"><span data-stu-id="637e6-137">People can choose to accept the risk and download a detected file.</span></span>

7. <span data-ttu-id="637e6-138">Aguarde até 30 minutos para que as alterações se espalhem para todos os datacenters do Office 365.</span><span class="sxs-lookup"><span data-stu-id="637e6-138">Allow up to 30 minutes for your changes to spread to all Office 365 datacenters.</span></span>

8. <span data-ttu-id="637e6-139">Recomenda Vá para configurar alertas para arquivos detectados.</span><span class="sxs-lookup"><span data-stu-id="637e6-139">(Recommended) Proceed to set up alerts for detected files.</span></span>

<span data-ttu-id="637e6-140">Para saber mais sobre como usar o PowerShell com o Office 365, confira [gerenciar o office 365 com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="637e6-140">To learn more about using PowerShell with Office 365, see [Manage Office 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).</span></span>

<span data-ttu-id="637e6-141">Para saber mais sobre a experiência do usuário quando um arquivo foi detectado como mal-intencionado, confira [o que fazer quando um arquivo mal-intencionado é encontrado no SharePoint Online, no onedrive ou no Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="637e6-141">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="set-up-alerts-for-detected-files"></a><span data-ttu-id="637e6-142">Configurar alertas para arquivos detectados</span><span class="sxs-lookup"><span data-stu-id="637e6-142">Set up alerts for detected files</span></span>

<span data-ttu-id="637e6-143">Para receber notificações quando um arquivo no SharePoint Online, no OneDrive for Business ou no Microsoft Teams foi identificado como mal-intencionado, você pode configurar um alerta.</span><span class="sxs-lookup"><span data-stu-id="637e6-143">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="637e6-144">No [centro de conformidade & segurança do Office 365](https://protection.office.com), escolha **alertas** \> **Gerenciar alertas**.</span><span class="sxs-lookup"><span data-stu-id="637e6-144">In the [Office 365 Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="637e6-145">Escolha **nova política de alerta**.</span><span class="sxs-lookup"><span data-stu-id="637e6-145">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="637e6-146">Especifique um nome para o alerta.</span><span class="sxs-lookup"><span data-stu-id="637e6-146">Specify a name for the alert.</span></span> <span data-ttu-id="637e6-147">Por exemplo, você pode digitar arquivos mal-intencionados em bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="637e6-147">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="637e6-148">Digite uma descrição para o alerta.</span><span class="sxs-lookup"><span data-stu-id="637e6-148">Type a description for the alert.</span></span> <span data-ttu-id="637e6-149">Por exemplo, você pode digitar notifica os administradores quando arquivos mal-intencionados são detectados no SharePoint Online, no OneDrive ou no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="637e6-149">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="637e6-150">Na seção **Enviar este alerta quando...** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="637e6-150">In the **Send this alert when...** section, do the following:</span></span>

   <span data-ttu-id="637e6-151">a.</span><span class="sxs-lookup"><span data-stu-id="637e6-151">a.</span></span> <span data-ttu-id="637e6-152">Na lista **atividades** , escolha **malware detectado em arquivo**.</span><span class="sxs-lookup"><span data-stu-id="637e6-152">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="637e6-153">b.</span><span class="sxs-lookup"><span data-stu-id="637e6-153">b.</span></span> <span data-ttu-id="637e6-154">Deixe o campo **usuários** vazio.</span><span class="sxs-lookup"><span data-stu-id="637e6-154">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="637e6-155">Na seção **Enviar este alerta para...** , selecione um ou mais administradores globais, administradores de segurança ou leitores de segurança que devem receber notificações quando um arquivo mal-intencionado for detectado.</span><span class="sxs-lookup"><span data-stu-id="637e6-155">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="637e6-156">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="637e6-156">Click **Save**.</span></span>

<span data-ttu-id="637e6-157">Para saber mais sobre alertas, confira [criar alertas de atividade no centro de conformidade & segurança do Office 365](../../compliance/create-activity-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="637e6-157">To learn more about alerts, see [Create activity alerts in the Office 365 Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="637e6-158">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="637e6-158">Next steps</span></span>

1. [<span data-ttu-id="637e6-159">Exibir informações sobre arquivos mal-intencionados detectados no SharePoint, no OneDrive ou no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="637e6-159">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

2. [<span data-ttu-id="637e6-160">Gerenciar arquivos e mensagens em quarentena como um administrador no Office 365</span><span class="sxs-lookup"><span data-stu-id="637e6-160">Manage quarantined messages and files as an administrator in Office 365</span></span>](manage-quarantined-messages-and-files.md)
