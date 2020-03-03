---
title: Gerenciar quem pode criar Grupos do Office 365
f1.keywords:
- NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Saiba como controlar quais usuários podem criar grupos do Office 365.
ms.openlocfilehash: a6016f6406b211aae216702910a696be50e1b82c
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352632"
---
# <a name="manage-who-can-create-office-365-groups"></a><span data-ttu-id="7a602-103">Gerenciar quem pode criar Grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="7a602-103">Manage who can create Office 365 Groups</span></span>

  
<span data-ttu-id="7a602-104">Como os usuários podem criar Grupos do Office 365 com facilidade, você não recebe milhões de solicitações para criá-los em nome de outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="7a602-104">Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="7a602-105">Dependendo da sua empresa, no entanto, talvez você queira controlar quem tem a capacidade de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="7a602-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="7a602-106">Este artigo explica como desabilitar a capacidade de criar grupos **em todos os serviços do Office 365 que usam grupos**:</span><span class="sxs-lookup"><span data-stu-id="7a602-106">This article explains how to disable the ability to create groups **in all Office 365 services that use groups**:</span></span> 
  
- <span data-ttu-id="7a602-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="7a602-107">Outlook</span></span>
    
- <span data-ttu-id="7a602-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7a602-108">SharePoint</span></span>
    
- <span data-ttu-id="7a602-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="7a602-109">Yammer</span></span>
    
- <span data-ttu-id="7a602-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a602-110">Microsoft Teams</span></span>

- <span data-ttu-id="7a602-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="7a602-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="7a602-112">StaffHub</span><span class="sxs-lookup"><span data-stu-id="7a602-112">StaffHub</span></span>
    
- <span data-ttu-id="7a602-113">Planner</span><span class="sxs-lookup"><span data-stu-id="7a602-113">Planner</span></span>
    
- <span data-ttu-id="7a602-114">PowerBI</span><span class="sxs-lookup"><span data-stu-id="7a602-114">PowerBI</span></span>

- <span data-ttu-id="7a602-115">Roteiro</span><span class="sxs-lookup"><span data-stu-id="7a602-115">Roadmap</span></span>
    
<span data-ttu-id="7a602-116">Você pode restringir a criação de grupo do Office 365 aos membros de um determinado grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="7a602-116">You can restrict Office 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="7a602-117">Para configurar isso, use o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a602-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="7a602-118">Este artigo orienta você pelas etapas necessárias.</span><span class="sxs-lookup"><span data-stu-id="7a602-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="7a602-119">As etapas neste artigo não impedem que os membros de determinadas funções criem grupos.</span><span class="sxs-lookup"><span data-stu-id="7a602-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="7a602-120">Os administradores globais do Office 365 podem criar grupos por meio de qualquer meio, como o centro de administração do Microsoft 365, o Planner, o Teams, o Exchange e o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7a602-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="7a602-121">Outras funções podem criar grupos por meio limitado, listados abaixo.</span><span class="sxs-lookup"><span data-stu-id="7a602-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="7a602-122">Administrador do Exchange: centro de administração do Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7a602-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="7a602-123">Suporte à camada 1 do parceiro: centro de administração do Microsoft 365, centro de administração do Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7a602-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="7a602-124">Suporte à camada 2 do parceiro: centro de administração do Microsoft 365, centro de administração do Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7a602-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="7a602-125">Gravadores de diretório: Azure AD</span><span class="sxs-lookup"><span data-stu-id="7a602-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="7a602-126">Administrador do SharePoint: centro de administração do SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7a602-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="7a602-127">Administrador do teams Service: centro de administração do Microsoft Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7a602-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="7a602-128">Administrador de gerenciamento de usuários: centro de administração do Microsoft 365, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="7a602-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="7a602-129">Se você for membro de uma dessas funções, poderá criar Grupos do Office 365 para usuários restritos e atribuir o usuário como o proprietário do grupo.</span><span class="sxs-lookup"><span data-stu-id="7a602-129">If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="7a602-130">Os usuários que possuem essa função podem criar grupos conectados no Yammer, independentemente de qualquer configuração do PowerShell que possa impedir a criação.</span><span class="sxs-lookup"><span data-stu-id="7a602-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="7a602-131">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="7a602-131">Licensing requirements</span></span>

<span data-ttu-id="7a602-132">Para gerenciar quem cria grupos, as seguintes pessoas precisam de licenças do Azure AD Premium ou licenças do Azure AD Basic EDU atribuídas a eles:</span><span class="sxs-lookup"><span data-stu-id="7a602-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="7a602-133">O administrador que configura essas definições de criação de grupos</span><span class="sxs-lookup"><span data-stu-id="7a602-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="7a602-134">Os membros do grupo de segurança que têm permissão para criar grupos</span><span class="sxs-lookup"><span data-stu-id="7a602-134">The members of the security group who are allowed to create Groups</span></span>

<span data-ttu-id="7a602-135">As seguintes pessoas não precisam de licenças do Azure AD Premium ou do Azure AD Basic EDU atribuídas:</span><span class="sxs-lookup"><span data-stu-id="7a602-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="7a602-136">Pessoas que são membros de grupos do Office 365 e que não têm a capacidade de criar outros grupos.</span><span class="sxs-lookup"><span data-stu-id="7a602-136">People who are members of Office 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a><span data-ttu-id="7a602-137">Etapa 1: Criar um grupo de segurança para os usuários que precisam criar Grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="7a602-137">Step 1: Create a security group for users who need to create Office 365 Groups</span></span>

<span data-ttu-id="7a602-138">Somente um grupo de segurança em sua organização pode ser usado para controlar quem é capaz de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="7a602-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="7a602-139">Mas você pode aninhar outros grupos de segurança como membros deste grupo.</span><span class="sxs-lookup"><span data-stu-id="7a602-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="7a602-140">Por exemplo, o grupo chamado Permitir a criação de grupo é o grupo de segurança designado e os grupos chamados Usuários do Microsoft Planner e Usuários do Exchange Online são membros daquele grupo.</span><span class="sxs-lookup"><span data-stu-id="7a602-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="7a602-141">Os administradores nas funções listadas acima não precisam ser membros desse grupo: Eles retêm a capacidade de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="7a602-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a602-142">Certifique-se de usar um **grupo de segurança** para restringir quem pode criar grupos.</span><span class="sxs-lookup"><span data-stu-id="7a602-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="7a602-143">Se você tentar usar um Grupo do Office 365, os membros não poderão criar um grupo do SharePoint, porque ele procura um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="7a602-143">If you try to use an Office 365 Group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="7a602-144">No centro de administração, vá para <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">a página grupos</a> de **grupos** \> .</span><span class="sxs-lookup"><span data-stu-id="7a602-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="7a602-145">Clique em **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="7a602-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="7a602-146">Escolha **segurança** como o tipo de grupo.</span><span class="sxs-lookup"><span data-stu-id="7a602-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="7a602-147">Lembre-se do nome do grupo!</span><span class="sxs-lookup"><span data-stu-id="7a602-147">Remember the name of the group!</span></span> <span data-ttu-id="7a602-148">Você precisará disso posteriormente.</span><span class="sxs-lookup"><span data-stu-id="7a602-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="7a602-149">Conclua a configuração do grupo de segurança, adicionando pessoas ou outros grupos de segurança que você deseja poder criar grupos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="7a602-149">Finish setting up the security group, adding people or other security groups who you want to be able to create Groups in your org.</span></span>
    
<span data-ttu-id="7a602-150">Para obter instruções detalhadas, consulte [criar, editar ou excluir um grupo de segurança no centro de administração do Microsoft 365](../email/create-edit-or-delete-a-security-group.md).</span><span class="sxs-lookup"><span data-stu-id="7a602-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
  
## <a name="step-2-install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="7a602-151">Etapa 2: instalar a versão de visualização do PowerShell do Azure Active Directory para o Graph</span><span class="sxs-lookup"><span data-stu-id="7a602-151">Step 2: Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

<span data-ttu-id="7a602-152">Estes procedimentos exigem a versão de visualização do PowerShell do Azure Active Directory para Graph.</span><span class="sxs-lookup"><span data-stu-id="7a602-152">These procedures require the preview version of the Azure Active Directory PowerShell for Graph.</span></span> <span data-ttu-id="7a602-153">A versão GA não funcionará.</span><span class="sxs-lookup"><span data-stu-id="7a602-153">The GA version will not work.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="7a602-154">Não é possível instalar as versões de visualização e GA no mesmo computador ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="7a602-154">You cannot install both the preview and GA versions on the same computer at the same time.</span></span> <span data-ttu-id="7a602-155">Você pode instalar o módulo no Windows 10, Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="7a602-155">You can install the module on Windows 10, Windows Server 2016.</span></span>

  
<span data-ttu-id="7a602-156">Como prática recomendada, convém estar  *sempre*  atualizado: desinstale a versão anterior do AzureADPreview ou do AzureAD e baixe a mais recente.</span><span class="sxs-lookup"><span data-stu-id="7a602-156">As a best practice, we recommend  *always*  staying current: uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
1. <span data-ttu-id="7a602-157">Na barra de pesquisa, digite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7a602-157">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="7a602-158">Clique com o botão direito do mouse em **Windows PowerShell** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="7a602-158">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
    
    ![Abra o PowerShell como "Executar como administrador".](../../media/52517af8-c7b0-4c8f-b2f3-0f82f9d5ace1.png)
    
3. <span data-ttu-id="7a602-160">Defina a política para RemoteSigned usando [Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).</span><span class="sxs-lookup"><span data-stu-id="7a602-160">Set the policy to RemoteSigned by using [Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).</span></span>
    
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
  
4. <span data-ttu-id="7a602-161">Verifique o módulo instalado:</span><span class="sxs-lookup"><span data-stu-id="7a602-161">Check installed module:</span></span>
    
    ```
    Get-InstalledModule -Name "AzureAD*"
    ```

5. <span data-ttu-id="7a602-162">Para desinstalar a versão anterior do AzureADPreview ou do AzureAD, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7a602-162">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
    ```
    Uninstall-Module AzureADPreview
    ```

    <span data-ttu-id="7a602-163">ou</span><span class="sxs-lookup"><span data-stu-id="7a602-163">or</span></span>
  
    ```
    Uninstall-Module AzureAD
    ```

6. <span data-ttu-id="7a602-164">To install the latest version of AzureADPreview, run this command:</span><span class="sxs-lookup"><span data-stu-id="7a602-164">To install the latest version of AzureADPreview, run this command:</span></span>
  
    ```
    Install-Module AzureADPreview
    ```

    <span data-ttu-id="7a602-165">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. </span><span class="sxs-lookup"><span data-stu-id="7a602-165">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>

<span data-ttu-id="7a602-166">Deixe a janela do PowerShell aberta para a etapa 3, abaixo.</span><span class="sxs-lookup"><span data-stu-id="7a602-166">Leave the PowerShell window open for Step 3, below.</span></span>
  
## <a name="step-3-run-powershell-commands"></a><span data-ttu-id="7a602-167">Etapa 3: executar comandos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a602-167">Step 3: Run PowerShell commands</span></span>

<span data-ttu-id="7a602-168">Copie o script abaixo para um editor de texto, como o bloco de notas, ou o [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="7a602-168">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="7a602-169">Substitua \* \<SecurityGroupName\> \* pelo nome do grupo de segurança que você criou.</span><span class="sxs-lookup"><span data-stu-id="7a602-169">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="7a602-170">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7a602-170">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="7a602-171">Salve o arquivo como GroupCreators. ps1.</span><span class="sxs-lookup"><span data-stu-id="7a602-171">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="7a602-172">Na janela do PowerShell, navegue até o local onde você salvou o arquivo (digite "CD <FileLocation>").</span><span class="sxs-lookup"><span data-stu-id="7a602-172">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="7a602-173">Execute o script digitando:</span><span class="sxs-lookup"><span data-stu-id="7a602-173">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="7a602-174">e [entre com sua conta de administrador](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="7a602-174">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="7a602-175">A última linha do script exibirá as configurações atualizadas:</span><span class="sxs-lookup"><span data-stu-id="7a602-175">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="7a602-177">Se no futuro você quiser alterar o grupo de segurança usado, poderá executar novamente o script com o nome do novo grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="7a602-177">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="7a602-178">Se você deseja desativar a restrição de criação de grupo e novamente permitir que todos os usuários criem grupos, defina $GroupName como "" e $AllowGroupCreation como "true" e execute novamente o script.</span><span class="sxs-lookup"><span data-stu-id="7a602-178">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="7a602-179">Etapa 4: verificar se funciona</span><span class="sxs-lookup"><span data-stu-id="7a602-179">Step 4: Verify that it works</span></span>

1. <span data-ttu-id="7a602-180">Entre no Office 365 com uma conta de usuário de alguém que NÃO tem a capacidade de criar grupos.</span><span class="sxs-lookup"><span data-stu-id="7a602-180">Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="7a602-181">Ou seja, eles não são membros do grupo de segurança que você criou ou de um administrador.</span><span class="sxs-lookup"><span data-stu-id="7a602-181">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="7a602-182">Selecione o bloco do **Planner** .</span><span class="sxs-lookup"><span data-stu-id="7a602-182">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="7a602-183">No Planner, selecione **novo plano** no painel de navegação à esquerda para criar um plano.</span><span class="sxs-lookup"><span data-stu-id="7a602-183">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="7a602-184">Você deve obter uma mensagem informando que o plano e a criação de grupos estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="7a602-184">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="7a602-185">Tente o mesmo procedimento novamente com um membro do grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="7a602-185">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="7a602-186">Se os membros do grupo de segurança não puderem criar grupos, verifique se eles não estão sendo bloqueados por meio da [política de caixa de correio do OWA](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="7a602-186">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="7a602-187">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="7a602-187">Related articles</span></span>

[<span data-ttu-id="7a602-188">Introdução ao Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a602-188">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="7a602-189">Configurar o gerenciamento de grupo de autoatendimento no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7a602-189">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="7a602-190">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="7a602-190">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="7a602-191">Cmdlets do Azure Active Directory para definição de configurações de grupo</span><span class="sxs-lookup"><span data-stu-id="7a602-191">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
