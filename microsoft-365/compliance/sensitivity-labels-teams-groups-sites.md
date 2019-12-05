---
title: Usar etiquetas de confidencialidade com o Microsoft Teams, grupos do Office 365 e sites do SharePoint (visualização pública)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/03/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Você pode aplicar rótulos ao Microsoft Teams, grupos do Office 365 e sites do SharePoint.
ms.openlocfilehash: ebe5e00c3458782e1874274cb508326968461ce3
ms.sourcegitcommit: 1bd81cf48c7fab1b8aaf7c3f550ce42ab02136dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2019
ms.locfileid: "39822487"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a><span data-ttu-id="4845a-103">Usar etiquetas de confidencialidade com o Microsoft Teams, grupos do Office 365 e sites do SharePoint (visualização pública)</span><span class="sxs-lookup"><span data-stu-id="4845a-103">Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)</span></span>

<span data-ttu-id="4845a-104">Ao criar rótulos de confidencialidade no [centro de conformidade da Microsoft 365](https://protection.office.com/), agora você pode aplicá-los ao Microsoft Teams, grupos do Office 365 e sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4845a-104">When you create sensitivity labels in the [Microsoft 365 compliance center](https://protection.office.com/), you can now apply them to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="4845a-105">Você pode associar políticas aos rótulos a serem controlados:</span><span class="sxs-lookup"><span data-stu-id="4845a-105">You can associate policies with the labels to control:</span></span>

- <span data-ttu-id="4845a-106">Configurações públicas/privadas</span><span class="sxs-lookup"><span data-stu-id="4845a-106">Public/private settings</span></span>
- <span data-ttu-id="4845a-107">Acesso de convidados</span><span class="sxs-lookup"><span data-stu-id="4845a-107">Guest access</span></span>
- <span data-ttu-id="4845a-108">Acesso de dispositivos não gerenciados</span><span class="sxs-lookup"><span data-stu-id="4845a-108">Access from unmanaged devices</span></span>

<span data-ttu-id="4845a-109">Quando você aplica um rótulo a uma equipe ou grupo, o rótulo se aplica automaticamente ao site de equipe do SharePoint conectado e ao contrário.</span><span class="sxs-lookup"><span data-stu-id="4845a-109">When you apply a label to a team or group, the label automatically applies to the connected SharePoint team site and the other way around.</span></span>

<span data-ttu-id="4845a-110">Agora, você também pode habilitar os rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4845a-110">Now, You can also enable sensitivity labels for Office files in SharePoint and OneDrive.</span></span> <span data-ttu-id="4845a-111">[Saiba mais](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="4845a-111">[Learn more](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a><span data-ttu-id="4845a-112">Sobre a visualização pública do Microsoft Teams, grupos do Office 365 e sites do SharePoint</span><span class="sxs-lookup"><span data-stu-id="4845a-112">About the public preview for Microsoft Teams, Office 365 groups, and SharePoint sites</span></span>

<span data-ttu-id="4845a-113">Os rótulos de confidencialidade para o Microsoft Teams, os grupos do Office 365 e os sites do SharePoint são implantados gradualmente para locatários e podem ser alterados antes da versão final.</span><span class="sxs-lookup"><span data-stu-id="4845a-113">Sensitivity labels for Microsoft Teams, Office 365 groups, and SharePoint sites is gradually rolling out to tenants and might change before final release.</span></span>

<span data-ttu-id="4845a-114">A visualização pública não funciona com as redes de distribuição de conteúdo do Office 365 (CDNs).</span><span class="sxs-lookup"><span data-stu-id="4845a-114">The public preview doesn't work with Office 365 Content Delivery Networks (CDNs).</span></span>

## <a name="overview"></a><span data-ttu-id="4845a-115">Visão geral</span><span class="sxs-lookup"><span data-stu-id="4845a-115">Overview</span></span>

<span data-ttu-id="4845a-116">Quando você publica rótulos de sensibilidade, os usuários no Office 365 têm acesso à mesma lista de rótulos.</span><span class="sxs-lookup"><span data-stu-id="4845a-116">When you publish sensitivity labels, users across Office 365 have access to the same list of labels.</span></span>

<span data-ttu-id="4845a-117">Estas imagens mostram:</span><span class="sxs-lookup"><span data-stu-id="4845a-117">These images show:</span></span>

- <span data-ttu-id="4845a-118">Como a lista aparece quando você cria um novo site de equipe do SharePoint</span><span class="sxs-lookup"><span data-stu-id="4845a-118">How the list appears when you create a new team site from SharePoint</span></span>

- <span data-ttu-id="4845a-119">Ao exibir a lista no Word</span><span class="sxs-lookup"><span data-stu-id="4845a-119">When you view the list in Word</span></span>

![Um rótulo de confidencialidade ao criar um site de equipe do SharePoint](media/sensitivity-label-new-team-site.png)

![Um rótulo de confidencialidade exibido no aplicativo da área de trabalho Word](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a><span data-ttu-id="4845a-122">Habilitar esta visualização usando o Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="4845a-122">Enable this preview by using Azure PowerShell</span></span>

1. <span data-ttu-id="4845a-123">Entre no Azure como um administrador global usando o Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4845a-123">Sign in to Azure as a global admin by using Azure PowerShell.</span></span> <span data-ttu-id="4845a-124">Para obter instruções, consulte [entrar com o Azure PowerShell](/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="4845a-124">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="4845a-125">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="4845a-125">Run the following command:</span></span>

```powershell
  Connect-AzureAD
  $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
  if ($setting -eq $null)
  {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
  }
  else
  {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
  }
```

<span data-ttu-id="4845a-126">O Office 365 não usa mais as classificações antigas para novos grupos e sites do SharePoint quando você habilita essa visualização.</span><span class="sxs-lookup"><span data-stu-id="4845a-126">Office 365 no longer uses the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="4845a-127">Se você usou a [classificação de site do Azure ad](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting ["classificationlist"]), os grupos e sites existentes ainda exibem as classificações antigas.</span><span class="sxs-lookup"><span data-stu-id="4845a-127">If you used [Azure AD site classification](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), existing groups and sites still display the old classifications.</span></span> <span data-ttu-id="4845a-128">Para exibir as novas classificações, converta-as.</span><span class="sxs-lookup"><span data-stu-id="4845a-128">To display the new classifications, convert them.</span></span> <span data-ttu-id="4845a-129">Para obter informações sobre como converter, confira [se você usou a classificação clássica de sites do Azure ad](#if-you-used-classic-azure-ad-site-classification).</span><span class="sxs-lookup"><span data-stu-id="4845a-129">For information about how to convert them, see [If you used classic Azure AD site classification](#if-you-used-classic-azure-ad-site-classification).</span></span> 

## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a><span data-ttu-id="4845a-130">Definir configurações de site e de grupo ao criar ou editar rótulos de sensibilidade</span><span class="sxs-lookup"><span data-stu-id="4845a-130">Set site and group settings when you create or edit sensitivity labels</span></span>

<span data-ttu-id="4845a-131">Após habilitar a visualização, siga estas etapas para criar ou editar rótulos de sensibilidade.</span><span class="sxs-lookup"><span data-stu-id="4845a-131">After you enable the preview, follow these steps to create or edit sensitivity labels.</span></span> <span data-ttu-id="4845a-132">Você deve concluir estas etapas para que os novos rótulos de sensibilidade funcionem com sites e grupos, mesmo que já tenha rótulos definidos.</span><span class="sxs-lookup"><span data-stu-id="4845a-132">You must complete these steps for the new sensitivity labels to work with sites and groups, even if you already have labels defined.</span></span> <span data-ttu-id="4845a-133">As alterações nessas configurações podem levar até 24 horas de sincronização.</span><span class="sxs-lookup"><span data-stu-id="4845a-133">Changes to these settings may take up to 24 hours sync.</span></span>

1. <span data-ttu-id="4845a-134">No centro de conformidade da Microsoft 365, selecione**Rótulos de sensibilidade**de **classificação** > .</span><span class="sxs-lookup"><span data-stu-id="4845a-134">In the Microsoft 365 compliance center, select **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="4845a-135">Selecione **criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="4845a-135">Select **Create a label**.</span></span> <span data-ttu-id="4845a-136">Se você já tiver um rótulo, pule para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="4845a-136">If you already have a label, skip to the next step.</span></span>

3. <span data-ttu-id="4845a-137">Selecione as opções desejadas e, na guia **configurações de site e grupo** , escolha:</span><span class="sxs-lookup"><span data-stu-id="4845a-137">Select the options you want, and then on the **Site and group settings** tab, choose:</span></span>

    - <span data-ttu-id="4845a-138">Privacidade (pública/privada): privada significa que somente membros aprovados em sua organização podem ver o que está dentro do grupo.</span><span class="sxs-lookup"><span data-stu-id="4845a-138">Privacy (Public/Private): Private means only approved members in your organization can see what's inside the group.</span></span> <span data-ttu-id="4845a-139">Qualquer outra pessoa em sua organização não consegue ver o que está no grupo.</span><span class="sxs-lookup"><span data-stu-id="4845a-139">Anyone else in your organization can't see what's in the group.</span></span> [<span data-ttu-id="4845a-140">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="4845a-140">Learn more</span></span>](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - <span data-ttu-id="4845a-141">Acesso de convidados: você pode controlar se os convidados podem ser adicionados a um grupo.</span><span class="sxs-lookup"><span data-stu-id="4845a-141">Guest access: You can control if guests can be added to a group.</span></span> [<span data-ttu-id="4845a-142">Saiba mais sobre como gerenciar o acesso de convidados nos grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="4845a-142">Learn about managing guest access in Office 365 Groups</span></span>](/office365/admin/create-groups/manage-guest-access-in-groups)
    - <span data-ttu-id="4845a-143">Dispositivos não gerenciados: essa configuração permite bloquear ou limitar o acesso ao conteúdo do SharePoint de dispositivos que não são internos ou compatíveis com o AD híbrido no Intune.</span><span class="sxs-lookup"><span data-stu-id="4845a-143">Unmanaged devices: This setting lets you block or limit access to SharePoint content from devices that aren't hybrid AD joined or compliant in Intune.</span></span> <span data-ttu-id="4845a-144">Se você selecionar dispositivos não gerenciados, precisará ir para o Azure AD para concluir a configuração da política.</span><span class="sxs-lookup"><span data-stu-id="4845a-144">If you select Unmanaged devices, you need to go to Azure AD to finish setting up the policy.</span></span> <span data-ttu-id="4845a-145">Para obter informações, consulte [controlar o acesso de dispositivos não gerenciados](/sharepoint/control-access-from-unmanaged-devices).</span><span class="sxs-lookup"><span data-stu-id="4845a-145">For info, see [Control access from unmanaged devices](/sharepoint/control-access-from-unmanaged-devices).</span></span>

![A guia Configurações de site e grupo](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> <span data-ttu-id="4845a-147">Somente as configurações de site e grupo terão efeito quando você aplicar um rótulo a uma equipe, grupo ou site.</span><span class="sxs-lookup"><span data-stu-id="4845a-147">Only the site and group settings take effect when you apply a label to a team, group, or site.</span></span> <span data-ttu-id="4845a-148">Outras configurações, como a criptografia e a marcação de conteúdo, não são aplicadas a todo o conteúdo dentro da equipe, grupo ou site.</span><span class="sxs-lookup"><span data-stu-id="4845a-148">Other settings, such as encryption and content marking, aren't applied to all content within the team, group, or site.</span></span> <span data-ttu-id="4845a-149">Da mesma forma, se você criar um rótulo e não ativar as configurações de site e de grupo, o rótulo ainda estará disponível quando os usuários criarem equipes, grupos e sites, mas não fizer nada quando os usuários a aplicarem.</span><span class="sxs-lookup"><span data-stu-id="4845a-149">Similarly, if you create a label and don't turn on site and group settings, the label will still be available when users create teams, groups, and sites, but it won't do anything when users apply it.</span></span>

[<span data-ttu-id="4845a-150">Saiba como publicar um rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="4845a-150">Learn how to publish a sensitivity label</span></span>](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="troubleshoot-sensitivity-label-deployment"></a><span data-ttu-id="4845a-151">Solucionando problemas de implantação de rótulo de sensibilidade</span><span class="sxs-lookup"><span data-stu-id="4845a-151">Troubleshoot sensitivity label deployment</span></span>

<span data-ttu-id="4845a-152">Se você tiver problemas ao criar um grupo Teams ou Office 365 após habilitar essas configurações ou fazer uma alteração na descrição de um rótulo de confidencialidade, salve o rótulo, espere algumas horas e, em seguida, tente criar novamente o grupo Team ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="4845a-152">If you experience issues when you create a Teams or Office 365 group after you enable these settings or make a change to a sensitivity label's description, save the label, wait a few hours, and then try to create the Team or Office 365 group again.</span></span>

<span data-ttu-id="4845a-153">Se você ainda não conseguir ver o novo rótulo de confidencialidade do SharePoint Online, entre em contato com o suporte da Microsoft imediatamente.</span><span class="sxs-lookup"><span data-stu-id="4845a-153">If you are still not able to see the new sensitivity label from SharePoint Online, then contact Microsoft Support immediately.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-team"></a><span data-ttu-id="4845a-154">Aplicar um rótulo de confidencialidade a uma nova equipe</span><span class="sxs-lookup"><span data-stu-id="4845a-154">Apply a sensitivity label to a new team</span></span>

<span data-ttu-id="4845a-155">Os usuários podem selecionar rótulos de confidencialidade quando criarem novas equipes no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4845a-155">Users can select sensitivity labels when they create new teams in Microsoft Teams.</span></span> <span data-ttu-id="4845a-156">Quando eles selecionam o nível de sensibilidade, a configuração de privacidade muda conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="4845a-156">When they select the sensitivity level, the privacy setting changes as necessary.</span></span> <span data-ttu-id="4845a-157">Dependendo da configuração de acesso de convidados selecionada para o rótulo, os usuários podem ou não adicionar pessoas de fora da organização para a equipe.</span><span class="sxs-lookup"><span data-stu-id="4845a-157">Depending on the guest access setting you selected for the label, users can or can't add people outside the organization to the team.</span></span>

![A configuração de privacidade ao criar uma nova equipe](media/privacy-setting-new-team.png)

<span data-ttu-id="4845a-159">Depois de criar a equipe, o rótulo de confidencialidade aparecerá no canto superior direito de todos os canais.</span><span class="sxs-lookup"><span data-stu-id="4845a-159">After you create the team, the sensitivity label appears in the upper-right corner of all channels.</span></span>

![O rótulo de confidencialidade aparece na equipe](media/privacy-setting-teams.png)

<span data-ttu-id="4845a-161">O serviço aplica automaticamente o mesmo rótulo de confidencialidade ao grupo do Office 365 e ao site de equipe do SharePoint conectado.</span><span class="sxs-lookup"><span data-stu-id="4845a-161">The service automatically applies the same sensitivity label to the Office 365 group and the connected SharePoint team site.</span></span>

## <a name="apply-a-sensitivity-label-to-a-new-group"></a><span data-ttu-id="4845a-162">Aplicar um rótulo de confidencialidade a um novo grupo</span><span class="sxs-lookup"><span data-stu-id="4845a-162">Apply a sensitivity label to a new group</span></span>

<span data-ttu-id="4845a-163">No Outlook na Web, a caixa nova **sensibilidade** contém rótulos publicados.</span><span class="sxs-lookup"><span data-stu-id="4845a-163">In Outlook on the web, the new **Sensitivity** box contains published labels.</span></span> <span data-ttu-id="4845a-164">Se os usuários quiserem mais informações, poderão clicar no ícone ajuda para ler os detalhes sobre os rótulos disponíveis e as políticas associadas.</span><span class="sxs-lookup"><span data-stu-id="4845a-164">If users want more info, they can click the help icon to read details about the available labels and associated policies.</span></span>

![Criar um grupo e selecionar uma opção em sensibilidade](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a><span data-ttu-id="4845a-166">Aplicar um rótulo de confidencialidade a um novo site</span><span class="sxs-lookup"><span data-stu-id="4845a-166">Apply a sensitivity label to a new site</span></span>

<span data-ttu-id="4845a-167">Administradores e usuários finais podem selecionar rótulos de confidencialidade ao criar sites de equipe e sites de comunicação modernos.</span><span class="sxs-lookup"><span data-stu-id="4845a-167">Admins and end users can select sensitivity labels when they create modern team sites and communication sites.</span></span>

[<span data-ttu-id="4845a-168">Saiba como criar um site no novo centro de administração do SharePoint</span><span class="sxs-lookup"><span data-stu-id="4845a-168">Learn how to create a site in the new SharePoint admin center</span></span>](/sharepoint/create-site-collection)

<span data-ttu-id="4845a-169">Quando os usuários criam sites de comunicação e equipe modernos, um rótulo de confidencialidade já estará selecionado por padrão.</span><span class="sxs-lookup"><span data-stu-id="4845a-169">When users create modern team and communication sites, a sensitivity label is already selected by default.</span></span> <span data-ttu-id="4845a-170">Os usuários podem selecionar o ícone de ajuda para saber mais sobre os rótulos.</span><span class="sxs-lookup"><span data-stu-id="4845a-170">Users can select the help icon to learn more about the labels.</span></span>

![Criar um site e selecionar uma opção em sensibilidade](media/sensitivity-label-new-communication-site.png)

<span data-ttu-id="4845a-172">Quando os usuários navegam até o site, eles podem ver o nome do rótulo e as políticas aplicadas.</span><span class="sxs-lookup"><span data-stu-id="4845a-172">When users browse to the site, they can see the name of the label and applied policies.</span></span>

![Um site com um rótulo de sensibilidade aplicado](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a><span data-ttu-id="4845a-174">Gerenciar rótulos de sensibilidade no centro de administração do SharePoint</span><span class="sxs-lookup"><span data-stu-id="4845a-174">Manage sensitivity labels in the SharePoint admin center</span></span>

<span data-ttu-id="4845a-175">Para exibir e editar os rótulos, use a página sites ativos no novo centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4845a-175">To view and edit the labels, use the Active sites page in the new SharePoint admin center.</span></span>

![A coluna sensibilidade na página sites ativos](media/manage-site-sensitivity-labels.png)

<span data-ttu-id="4845a-177">[Saiba mais sobre o gerenciamento de sites no novo centro de administração do SharePoint](/sharepoint/manage-sites-in-new-admin-center).</span><span class="sxs-lookup"><span data-stu-id="4845a-177">[Learn more about managing sites in the new SharePoint admin center](/sharepoint/manage-sites-in-new-admin-center).</span></span>

## <a name="change-site-and-group-settings-for-a-label"></a><span data-ttu-id="4845a-178">Alterar as configurações de site e de grupo de um rótulo</span><span class="sxs-lookup"><span data-stu-id="4845a-178">Change site and group settings for a label</span></span>

<span data-ttu-id="4845a-179">Como prática recomendada, não altere as configurações depois de aplicar um rótulo a várias equipes, grupos ou sites.</span><span class="sxs-lookup"><span data-stu-id="4845a-179">As a best practice, don't change settings after you've applied a label to several teams, groups, or sites.</span></span> <span data-ttu-id="4845a-180">Se for necessário fazer uma alteração, você precisará usar um script do PowerShell do Azure AD para aplicar as atualizações manualmente.</span><span class="sxs-lookup"><span data-stu-id="4845a-180">If you must make a change, you'll need to use an Azure AD PowerShell script to manually apply updates.</span></span> <span data-ttu-id="4845a-181">Esse método garante que todas as equipes, sites e grupos existentes imponham a nova configuração.</span><span class="sxs-lookup"><span data-stu-id="4845a-181">This method ensures all existing teams, sites, and groups enforce the new setting.</span></span>

## <a name="support-for-the-new-sensitivity-labels"></a><span data-ttu-id="4845a-182">Suporte para os novos rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="4845a-182">Support for the new sensitivity labels</span></span>

<span data-ttu-id="4845a-183">Os seguintes aplicativos e serviços suportam os rótulos de confidencialidade nesta visualização:</span><span class="sxs-lookup"><span data-stu-id="4845a-183">The following apps and services support the sensitivity labels in this preview:</span></span>

- <span data-ttu-id="4845a-184">Centro de conformidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4845a-184">Microsoft 365 compliance center</span></span>
- <span data-ttu-id="4845a-185">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4845a-185">SharePoint</span></span>
- <span data-ttu-id="4845a-186">Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="4845a-186">Outlook on the web</span></span>
- <span data-ttu-id="4845a-187">Teams</span><span class="sxs-lookup"><span data-stu-id="4845a-187">Teams</span></span>
- <span data-ttu-id="4845a-188">Centro de administração do SharePoint</span><span class="sxs-lookup"><span data-stu-id="4845a-188">SharePoint admin center</span></span>
- <span data-ttu-id="4845a-189">Centro de administração do Azure AD</span><span class="sxs-lookup"><span data-stu-id="4845a-189">Azure AD admin center</span></span>

<span data-ttu-id="4845a-190">Você não pode usar os seguintes aplicativos e serviços para criar grupos do Office 365 com os novos rótulos de sensibilidade:</span><span class="sxs-lookup"><span data-stu-id="4845a-190">You can't use the following apps and services to create Office 365 groups with the new sensitivity labels:</span></span>

- <span data-ttu-id="4845a-191">Outlook para Mac</span><span class="sxs-lookup"><span data-stu-id="4845a-191">Outlook for the Mac</span></span>
- <span data-ttu-id="4845a-192">Móvel do Outlook</span><span class="sxs-lookup"><span data-stu-id="4845a-192">Outlook mobile</span></span>  
- <span data-ttu-id="4845a-193">Área de trabalho do Outlook para Windows</span><span class="sxs-lookup"><span data-stu-id="4845a-193">Outlook desktop for Windows</span></span>
- <span data-ttu-id="4845a-194">Forms</span><span class="sxs-lookup"><span data-stu-id="4845a-194">Forms</span></span>  
- <span data-ttu-id="4845a-195">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="4845a-195">Dynamics 365</span></span>  
- <span data-ttu-id="4845a-196">Yammer</span><span class="sxs-lookup"><span data-stu-id="4845a-196">Yammer</span></span>  
- <span data-ttu-id="4845a-197">Stream</span><span class="sxs-lookup"><span data-stu-id="4845a-197">Stream</span></span>  
- <span data-ttu-id="4845a-198">Planner</span><span class="sxs-lookup"><span data-stu-id="4845a-198">Planner</span></span>  
- <span data-ttu-id="4845a-199">Project</span><span class="sxs-lookup"><span data-stu-id="4845a-199">Project</span></span>  
- <span data-ttu-id="4845a-200">PowerBI</span><span class="sxs-lookup"><span data-stu-id="4845a-200">PowerBI</span></span>  
- <span data-ttu-id="4845a-201">Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4845a-201">Teams admin center</span></span>  
- <span data-ttu-id="4845a-202">Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4845a-202">Microsoft 365 admin center</span></span>  
- <span data-ttu-id="4845a-203">Centro de administração do Exchange</span><span class="sxs-lookup"><span data-stu-id="4845a-203">Exchange admin center</span></span>

## <a name="if-you-used-classic-azure-ad-site-classification"></a><span data-ttu-id="4845a-204">Se você usou a classificação clássica de site do Azure AD</span><span class="sxs-lookup"><span data-stu-id="4845a-204">If you used classic Azure AD site classification</span></span>

<span data-ttu-id="4845a-205">O Office 365 não oferece mais suporte às classificações antigas para novos grupos e sites do SharePoint quando você habilita essa visualização.</span><span class="sxs-lookup"><span data-stu-id="4845a-205">Office 365 no longer supports the old classifications for new groups and SharePoint sites when you enable this preview.</span></span> <span data-ttu-id="4845a-206">No entanto, os grupos e sites existentes ainda exibem as classificações antigas, a menos que você as converta.</span><span class="sxs-lookup"><span data-stu-id="4845a-206">However, existing groups and sites still display the old classifications unless you convert them.</span></span> <span data-ttu-id="4845a-207">As classificações antigas incluem a classificação de sites "modernos" que você configurou, possivelmente por meio do Azure AD PowerShell ou da biblioteca principal de PnP `ClassificationList` , que definiu valores para a configuração.</span><span class="sxs-lookup"><span data-stu-id="4845a-207">Old classifications include the "modern" sites classification you set up, possibly through Azure AD PowerShell or the PnP Core library, that defined values for the `ClassificationList` setting.</span></span>

<span data-ttu-id="4845a-208">Por exemplo, no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4845a-208">For example, in PowerShell:</span></span>

```powershell
   ($setting["ClassificationList"])
```

<span data-ttu-id="4845a-209">Para obter mais informações sobre o antigo método de classificação, confira [classificação de sites "modernos" do SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span><span class="sxs-lookup"><span data-stu-id="4845a-209">For more information about the old classification method, see [SharePoint "modern" sites classification](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).</span></span>

<span data-ttu-id="4845a-210">Com base em sua implantação atual, você tem duas opções para converter suas classificações antigas para as novas classificações.</span><span class="sxs-lookup"><span data-stu-id="4845a-210">Based on your current deployment, you have two options to convert your old classifications to the new classifications.</span></span>

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="4845a-211">Se você nunca usou rótulos de confidencialidade (rótulos unificados de proteção de informações da Microsoft) para arquivos e email</span><span class="sxs-lookup"><span data-stu-id="4845a-211">If you never used sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="4845a-212">Recomendamos que você:</span><span class="sxs-lookup"><span data-stu-id="4845a-212">We recommend that you:</span></span>

1. <span data-ttu-id="4845a-213">Crie novos rótulos de sensibilidade no centro de conformidade da Microsoft 365 com os mesmos nomes de suas classificações existentes.</span><span class="sxs-lookup"><span data-stu-id="4845a-213">Create new sensitivity labels in the Microsoft 365 compliance center that have the same names as your existing classifications.</span></span>
2. <span data-ttu-id="4845a-214">Use o PowerShell para aplicar os novos rótulos aos grupos existentes do Office 365 e sites do SharePoint usando o mapeamento de nome.</span><span class="sxs-lookup"><span data-stu-id="4845a-214">Use PowerShell to apply the new labels to existing Office 365 groups and SharePoint sites using name mapping.</span></span>
3. <span data-ttu-id="4845a-215">Exclua as classificações antigas.</span><span class="sxs-lookup"><span data-stu-id="4845a-215">Delete the old classifications.</span></span>

<span data-ttu-id="4845a-216">Os aplicativos e serviços que dão suporte aos novos rótulos de sensibilidade irão mostrá-los.</span><span class="sxs-lookup"><span data-stu-id="4845a-216">Apps and services that support the new sensitivity labels will show them.</span></span> <span data-ttu-id="4845a-217">Você cria novas equipes, grupos e sites com os novos rótulos.</span><span class="sxs-lookup"><span data-stu-id="4845a-217">You create new teams, groups, and sites with the new labels.</span></span> <span data-ttu-id="4845a-218">Os usuários ainda podem criar grupos de aplicativos e serviços que não dão suporte aos novos rótulos.</span><span class="sxs-lookup"><span data-stu-id="4845a-218">Users can still create groups from apps and services that don't support the new labels.</span></span> <span data-ttu-id="4845a-219">No entanto, os usuários não podem aplicar um rótulo a esses grupos.</span><span class="sxs-lookup"><span data-stu-id="4845a-219">However, users can't apply a label to these groups.</span></span> <span data-ttu-id="4845a-220">Use o PowerShell para aplicar os novos rótulos de sensibilidade a esses grupos.</span><span class="sxs-lookup"><span data-stu-id="4845a-220">Use PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="4845a-221">Você pode manter suas classificações antigas; no entanto, é altamente recomendável usar o PowerShell para aplicar os novos rótulos de sensibilidade a esses grupos.</span><span class="sxs-lookup"><span data-stu-id="4845a-221">You can keep your old classifications; however, we highly recommend using PowerShell to apply the new sensitivity labels to these groups.</span></span>

<span data-ttu-id="4845a-222">Os aplicativos e serviços que dão suporte aos novos rótulos de sensibilidade serão criados com os novos rótulos.</span><span class="sxs-lookup"><span data-stu-id="4845a-222">Apps and services that support the new sensitivity labels will get created with the new labels.</span></span> <span data-ttu-id="4845a-223">Quando os usuários criam grupos de aplicativos e serviços que não dão suporte aos novos rótulos, eles podem selecionar uma classificação.</span><span class="sxs-lookup"><span data-stu-id="4845a-223">When users create groups from apps and services that don't support the new labels, they can select a classification.</span></span>

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a><span data-ttu-id="4845a-224">Se você usar rótulos de confidencialidade (rótulos unificados de proteção de informações da Microsoft) para arquivos e email</span><span class="sxs-lookup"><span data-stu-id="4845a-224">If you use sensitivity labels (unified Microsoft Information Protection labels) for files and email</span></span>

<span data-ttu-id="4845a-225">Assim que você habilitar esta visualização, vá para cada etiqueta no centro de conformidade da Microsoft 365 e aplique as políticas desejadas para sites e grupos.</span><span class="sxs-lookup"><span data-stu-id="4845a-225">As soon as you enable this preview, go to each label in the Microsoft 365 compliance center and apply the policies you want for sites and groups.</span></span> <span data-ttu-id="4845a-226">Os usuários começarão a ver seus rótulos existentes disponíveis para sites e grupos.</span><span class="sxs-lookup"><span data-stu-id="4845a-226">Users will start seeing your existing labels available for sites and groups.</span></span>

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a><span data-ttu-id="4845a-227">Prepare o Shell de gerenciamento do SharePoint Online antes de rerotular grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="4845a-227">Prepare the SharePoint Online Management Shell before you relabel Office 365 groups</span></span>

<span data-ttu-id="4845a-228">Antes de aplicar novos rótulos, verifique se você está executando o Shell de gerenciamento do SharePoint Online mais recente.</span><span class="sxs-lookup"><span data-stu-id="4845a-228">Before you apply new labels, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="4845a-229">Se você já tiver a versão mais recente, poderá ir em frente e [rerotular grupos do Office 365 com novos rótulos de sensibilidade](#relabel-office-365-groups-with-new-sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="4845a-229">If you already have the latest version, you can go ahead and [Relabel Office 365 groups with new sensitivity labels](#relabel-office-365-groups-with-new-sensitivity-labels).</span></span>

<span data-ttu-id="4845a-230">Para preparar o Shell de gerenciamento do SharePoint Online para a visualização:</span><span class="sxs-lookup"><span data-stu-id="4845a-230">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="4845a-231">Se você instalou uma versão anterior do Shell de gerenciamento do SharePoint Online, vá para **Adicionar ou remover programas** e desinstalar o "Shell de gerenciamento do SharePoint Online".</span><span class="sxs-lookup"><span data-stu-id="4845a-231">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell”.</span></span>

2. <span data-ttu-id="4845a-232">Em um navegador da Web, vá até a página centro de download e [Baixe o Shell de gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="4845a-232">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="4845a-233">Selecione seu idioma e clique em **baixar**.</span><span class="sxs-lookup"><span data-stu-id="4845a-233">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="4845a-234">Escolha entre o arquivo x64 e x86. msi.</span><span class="sxs-lookup"><span data-stu-id="4845a-234">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="4845a-235">Baixe o arquivo x64 se você executar a versão de 64 bits do Windows ou o arquivo x86 se você estiver executando a versão de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="4845a-235">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you’re run the 32-bit version.</span></span> <span data-ttu-id="4845a-236">Se você não souber, confira [qual versão do sistema operacional Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="4845a-236">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="4845a-237">Depois de baixar o arquivo, execute o arquivo e siga as etapas no assistente de instalação.</span><span class="sxs-lookup"><span data-stu-id="4845a-237">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a><span data-ttu-id="4845a-238">Reetiquetar grupos do Office 365 com novos rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="4845a-238">Relabel Office 365 groups with new sensitivity labels</span></span>

1. <span data-ttu-id="4845a-239">Verifique se você está usando a versão mais recente do Shell de gerenciamento do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4845a-239">Ensure that you're using the latest version of the SharePoint Online Management Shell.</span></span> <span data-ttu-id="4845a-240">Para obter instruções, consulte [preparar o Shell de gerenciamento do SharePoint Online antes de rerotular grupos do Office 365](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="4845a-240">For instructions, see [Prepare the SharePoint Online Management Shell before you relabel Office 365 groups](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).</span></span>

2. <span data-ttu-id="4845a-241">Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global ou de administrador do SharePoint no Office 365, conecte-se ao Shell de gerenciamento do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4845a-241">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint Online Management Shell.</span></span> <span data-ttu-id="4845a-242">Veja como em [Introdução ao Shell de Gerenciamento do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="4845a-242">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

3. <span data-ttu-id="4845a-243">Execute o seguinte comando para obter a lista de rótulos de confidencialidade e seus GUIDs.</span><span class="sxs-lookup"><span data-stu-id="4845a-243">Run the following command to get the list of sensitivity labels and their GUIDs.</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. <span data-ttu-id="4845a-244">Anote o GUID do rótulo que você deseja substituir.</span><span class="sxs-lookup"><span data-stu-id="4845a-244">Make a note of the GUID for the label you want to overwrite.</span></span> <span data-ttu-id="4845a-245">Por exemplo, o rótulo "geral".</span><span class="sxs-lookup"><span data-stu-id="4845a-245">For example, the "General" label.</span></span>

5. <span data-ttu-id="4845a-246">Use o seguinte comando para obter a lista de grupos que têm a classificação "geral".</span><span class="sxs-lookup"><span data-stu-id="4845a-246">Use the following command to get the list of groups that have the “General” classification.</span></span> <span data-ttu-id="4845a-247">Ao executar este comando, você se conectará ao PowerShell do Exchange Online e executará o cmdlet Get-unificado.</span><span class="sxs-lookup"><span data-stu-id="4845a-247">When you run this command, you'll connect to Exchange Online PowerShell and run the Get-UnifiedGroup cmdlet.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. <span data-ttu-id="4845a-248">Para cada grupo, adicione o novo GUID de rótulo de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="4845a-248">For each group, add the new sensitivity label GUID.</span></span>

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
