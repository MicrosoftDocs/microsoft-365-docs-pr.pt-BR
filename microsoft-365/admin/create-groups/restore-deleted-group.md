---
title: Restaurar um Grupo do Office 365 excluído
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 'Saiba como restaurar um grupo excluído do Office 365 usando o centro de administração do Exchange. '
ms.openlocfilehash: 98eb00d90f5b607a58cd32728ce43cb4a1de1ff5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237416"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="8e830-103">Restaurar um Grupo do Office 365 excluído</span><span class="sxs-lookup"><span data-stu-id="8e830-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="8e830-104">Se você for o proprietário de um grupo do Office 365, poderá restaurar o grupo seguindo estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8e830-104">If you are the owner of an Office 365 group, you can restore the group yourself by following these steps.</span></span>

1. <span data-ttu-id="8e830-105">Na [página grupos excluídos](https://outlook.office.com/people/group/deleted), selecione a opção **gerenciar grupos** no nó **grupos** e, em seguida, escolha **excluído**.</span><span class="sxs-lookup"><span data-stu-id="8e830-105">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="8e830-106">Clique na guia **restaurar** ao lado do grupo que você deseja restaurar.</span><span class="sxs-lookup"><span data-stu-id="8e830-106">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="8e830-107">Se o grupo excluído não aparecer aqui, entre em contato com um administrador.</span><span class="sxs-lookup"><span data-stu-id="8e830-107">If the deleted group doesn't appear here, contact an administrator.</span></span>
  
<span data-ttu-id="8e830-108">Se você for um usuário que deseja restaurar um grupo do Office 365, peça ao administrador para executar estas etapas ou entrar em contato com o suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="8e830-108">If you're a user who wants to restore an Office 365 group, ask an administrator to do these steps for you or contact your help desk.</span></span>  
   
<span data-ttu-id="8e830-109">Se você tiver excluído um grupo, ele será mantido por 30 dias por padrão.</span><span class="sxs-lookup"><span data-stu-id="8e830-109">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="8e830-110">Este período de 30 dias é considerado uma "exclusão reversível" porque você ainda pode restaurar o grupo.</span><span class="sxs-lookup"><span data-stu-id="8e830-110">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="8e830-111">Após 30 dias, o grupo e seu conteúdo associado são excluídos permanentemente e não podem ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="8e830-111">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>
  
<span data-ttu-id="8e830-112">Durante o período de "exclusão reversível", se um usuário tentar acessar o site, ele receberá uma mensagem de _proibido_ 404.</span><span class="sxs-lookup"><span data-stu-id="8e830-112">During the "soft-delete" period, if a user tries to access the site they will get a 404 _forbidden_ message.</span></span> <span data-ttu-id="8e830-113">Após esse período, se um usuário tentar acessar o site, ele receberá uma mensagem 404 _não encontrada_ .</span><span class="sxs-lookup"><span data-stu-id="8e830-113">After this period, if a user tries to access the site, they will get a 404 _not found_ message.</span></span>
  
<span data-ttu-id="8e830-114">Quando um grupo de é restaurado, o seguinte conteúdo é restaurado:</span><span class="sxs-lookup"><span data-stu-id="8e830-114">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="8e830-115">Azure Active Directory (AD) grupos do Office 365, propriedades e membros.</span><span class="sxs-lookup"><span data-stu-id="8e830-115">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="8e830-116">Endereços de email do grupo.</span><span class="sxs-lookup"><span data-stu-id="8e830-116">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="8e830-117">Calendário e caixa de entrada compartilhada do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8e830-117">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="8e830-118">Arquivos e site de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8e830-118">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="8e830-119">Bloco de anotações do OneNote</span><span class="sxs-lookup"><span data-stu-id="8e830-119">OneNote notebook</span></span>
    
- <span data-ttu-id="8e830-120">Planner</span><span class="sxs-lookup"><span data-stu-id="8e830-120">Planner</span></span>
    
- <span data-ttu-id="8e830-121">Teams</span><span class="sxs-lookup"><span data-stu-id="8e830-121">Teams</span></span>

- <span data-ttu-id="8e830-122">Grupo e conteúdo de grupo do Yammer (se o grupo do Office 365 foi criado a partir do Yammer)</span><span class="sxs-lookup"><span data-stu-id="8e830-122">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>
    
<span data-ttu-id="8e830-123">Você também pode [Excluir permanentemente um grupo do Office 365](#permanently-delete-an-office-365-group) caso não possa esperar os 30 dias do período de retenção para que o conteúdo seja excluído permanentemente.</span><span class="sxs-lookup"><span data-stu-id="8e830-123">You can also [Permanently delete an Office 365 group](#permanently-delete-an-office-365-group) if you can't wait the 30 days for the retention period to expire for the content to be permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="8e830-124">O proprietário do grupo do Office 365 excluído também é capaz de restaurar o grupo.</span><span class="sxs-lookup"><span data-stu-id="8e830-124">The owner of the deleted Office 365 group is also able to restore the group.</span></span> <span data-ttu-id="8e830-125">Para restaurar um grupo do Office 365 usando permissão de proprietário sem permissão de administrador, confira [restaurar um grupo do office 365 usando o PowerShell](#restore-an-office-365-group-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="8e830-125">To restore an office 365 group using owner permission without administrator permission, see [Restore an Office 365 Group using PowerShell](#restore-an-office-365-group-using-powershell).</span></span>

## <a name="restore-an-office-365-group-using-the-exchange-admin-center"></a><span data-ttu-id="8e830-126">Restaurar um grupo do Office 365 usando o Centro de administração do Exchange</span><span class="sxs-lookup"><span data-stu-id="8e830-126">Restore an Office 365 Group using the Exchange admin center</span></span>

<span data-ttu-id="8e830-127">Você deve ter permissões de administrador global do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8e830-127">You must have Office 365 global administrator permissions.</span></span>

1. <span data-ttu-id="8e830-128">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="8e830-128">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="8e830-129">No Centro de administração do Exchange, selecione **destinatários** e escolha **grupos**.</span><span class="sxs-lookup"><span data-stu-id="8e830-129">In the Exchange admin center, select **recipients**, and then choose **groups**.</span></span> <span data-ttu-id="8e830-130">Você pode ver se o grupo está ativo ou excluído de forma reversível.</span><span class="sxs-lookup"><span data-stu-id="8e830-130">You can view whether the group is Active or soft-deleted.</span></span> <span data-ttu-id="8e830-131">Se o grupo tiver sido excluído permanentemente, ele não aparecerá na lista.</span><span class="sxs-lookup"><span data-stu-id="8e830-131">If the group has been permanently deleted, it won't be listed at all.</span></span>
  
3. <span data-ttu-id="8e830-132">Para exibir o horário exato em que o grupo foi excluído por software, selecione o grupo e exiba as informações no painel direito.</span><span class="sxs-lookup"><span data-stu-id="8e830-132">To view the exact time when the group was soft-deleted, select the group and view the info in the right pane.</span></span>
      
4. <span data-ttu-id="8e830-133">Selecione o grupo que você deseja restaurar e, em seguida, selecione o ícone restaurar.</span><span class="sxs-lookup"><span data-stu-id="8e830-133">Select the group you want to restore, and then select the restore icon.</span></span>
    
    ![Escolha o grupo que você deseja restaurar e, em seguida, selecione o ícone restaurar.](../media/restore-group.png)
  
5. <span data-ttu-id="8e830-135">Selecionar atualizar</span><span class="sxs-lookup"><span data-stu-id="8e830-135">Select refresh</span></span> ![Ícone Atualizar](../media/6464df90-2a91-4c1f-92a6-9a38c7696ac3.gif) <span data-ttu-id="8e830-137">para atualizar as informações na página.</span><span class="sxs-lookup"><span data-stu-id="8e830-137">to update the information on the page.</span></span> <span data-ttu-id="8e830-138">Seu grupo será exibido como Ativo.</span><span class="sxs-lookup"><span data-stu-id="8e830-138">Your group will show as Active.</span></span> <span data-ttu-id="8e830-139">Todos os formulários e dados de formulário associados ao grupo também serão restaurados.</span><span class="sxs-lookup"><span data-stu-id="8e830-139">Any forms and form data associated with your group will also be restored.</span></span>
    
## <a name="restore-an-office-365-group-using-powershell"></a><span data-ttu-id="8e830-140">Restaurar um grupo do Office 365 usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e830-140">Restore an Office 365 Group using PowerShell</span></span>

<span data-ttu-id="8e830-141">Você deve ter permissões de administrador global do Office 365 ou ser um antigo proprietário do grupo do Office 365 excluído.</span><span class="sxs-lookup"><span data-stu-id="8e830-141">You must have Office 365 global administrator permissions, or be a former owner of the deleted Office 365 group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e830-142">Se você usar remove-MsolGroup no PowerShell para excluir um grupo, isso excluirá o grupo permanentemente.</span><span class="sxs-lookup"><span data-stu-id="8e830-142">If you use Remove-MsolGroup in PowerShell to delete a group, this will delete the group permanently.</span></span> <span data-ttu-id="8e830-143">Ao usar o PowerShell para excluir grupos, é recomendável usar **Remove-AzureADMSGroup** para excluir o grupo do Office365 temporariamente.</span><span class="sxs-lookup"><span data-stu-id="8e830-143">When using PowerShell to delete groups, it's best practice to use **Remove-AzureADMSGroup** to soft-delete the Office 365 group.</span></span> <span data-ttu-id="8e830-144">Assim você poderá recuperá-lo caso necessário.</span><span class="sxs-lookup"><span data-stu-id="8e830-144">That way you can restore it if needed.</span></span> 
  
### <a name="install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="8e830-145">Instalar a versão de visualização do PowerShell do Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="8e830-145">Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e830-146">Não é possível instalar as versões de visualização e GA no mesmo computador ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="8e830-146">You cannot install both the preview and GA versions on the same computer at the same time.</span></span>
  
<span data-ttu-id="8e830-147">Como prática recomendada, recomendamos *sempre* permanecer atualizado, ou seja, desinstalar o antigo AzureADPreview ou a versão antiga do AzureAD e obter o mais recente.</span><span class="sxs-lookup"><span data-stu-id="8e830-147">As a best practice, we recommend *always* staying current, i.e. uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
 
1. <span data-ttu-id="8e830-148">Na barra de pesquisa, digite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e830-148">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="8e830-149">Clique com o botão direito do mouse em **Windows PowerShell** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="8e830-149">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
  
2. <span data-ttu-id="8e830-150">Revise seus módulos instalados:</span><span class="sxs-lookup"><span data-stu-id="8e830-150">Review your installed modules:</span></span>
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. <span data-ttu-id="8e830-151">Para desinstalar a versão anterior do AzureADPreview ou do AzureAD, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8e830-151">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
```
   Uninstall-Module AzureADPreview
```

<span data-ttu-id="8e830-152">ou</span><span class="sxs-lookup"><span data-stu-id="8e830-152">or</span></span>
  
```
   Uninstall-Module AzureAD
```

4. <span data-ttu-id="8e830-153">To install the latest version of AzureADPreview, run this command:</span><span class="sxs-lookup"><span data-stu-id="8e830-153">To install the latest version of AzureADPreview, run this command:</span></span>
  
```
   Install-Module AzureADPreview
```



<span data-ttu-id="8e830-154">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. </span><span class="sxs-lookup"><span data-stu-id="8e830-154">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>
  
### <a name="restore-the-deleted-group"></a><span data-ttu-id="8e830-155">Restaure o grupo excluído</span><span class="sxs-lookup"><span data-stu-id="8e830-155">Restore the deleted group</span></span>
  
1. <span data-ttu-id="8e830-156">Você instalou o módulo **AzureADPreview** , conforme instruído na seção previoius "instalar a versão de visualização do módulo do Azure Active Directory para Windows PowerShell"?</span><span class="sxs-lookup"><span data-stu-id="8e830-156">Did you install the **AzureADPreview** module, as instructed in the previoius section "Install the preview version of the Azure Active Directory Module for Windows PowerShell"?</span></span>  <span data-ttu-id="8e830-157">Não ter a versão de **visualização** mais recente é o principal motivo pelo qual esses procedimentos não funcionam.</span><span class="sxs-lookup"><span data-stu-id="8e830-157">Not having the most current **preview** version is the #1 reason these steps don't work for people.</span></span> 
    
2. <span data-ttu-id="8e830-158">Se ainda não o fez, abra uma janela do Windows PowerShell no seu computador (não importa se for uma janela normal do Windows PowerShell ou uma que você abriu selecionando **Executar como administrador**).</span><span class="sxs-lookup"><span data-stu-id="8e830-158">If you haven't already, open a Windows PowerShell window on your computer (it doesn't matter if it's a normal Windows PowerShell window, or one you opened by selecting **Run as administrator**).</span></span>
    
3. <span data-ttu-id="8e830-159">Execute os seguintes comandos pressionando **Enter** depois de cada um:</span><span class="sxs-lookup"><span data-stu-id="8e830-159">Run the following commands by pressing **Enter** after each one:</span></span> 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```



  <span data-ttu-id="8e830-160">Na tela **entrar na sua conta** que é aberta, insira seu nome de usuário e senha da conta administrativa para conectá-lo ao seu serviço do Azure AD e selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="8e830-160">On the **Sign in to your Account** screen that opens, enter your administrative account user name and password to connect you to your Azure AD service, and select **Sign in**.</span></span>
  
4. <span data-ttu-id="8e830-161">Execute este comando para exibir todos os grupos do Office 365 excluídos por software em sua organização que ainda estejam dentro do período de exclusão reversível de 30 dias:</span><span class="sxs-lookup"><span data-stu-id="8e830-161">Run this command to display all soft-deleted Office 365 groups in your organization that are still within the 30 day soft-deletion period:</span></span>
    
  ```
  Get-AzureADMSDeletedGroup
  ```

5. <span data-ttu-id="8e830-162">Anote a ID de objeto do grupo, ou grupos, que você deseja restaurar.</span><span class="sxs-lookup"><span data-stu-id="8e830-162">Take note of the object ID of the group, or groups, you want to restore.</span></span> <span data-ttu-id="8e830-163">Se você não vir o grupo que está procurando nessa lista, provavelmente ele já foi descartado permanentemente.</span><span class="sxs-lookup"><span data-stu-id="8e830-163">If you don't see the group you're looking for on this list then it has likely been permanently purged already.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="8e830-164">Se um novo grupo tiver sido criado com o mesmo alias ou endereço SMTP do grupo excluído, será necessário excluir esse novo grupo antes que você possa restaurar o grupo excluído.</span><span class="sxs-lookup"><span data-stu-id="8e830-164">If a new group has been created with the same alias or SMTP address as your deleted group, you will have to delete that new group before you'll be able to restore your deleted group.</span></span> 
  
6. <span data-ttu-id="8e830-165">Para restaurar esse grupo, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="8e830-165">To restore that group, run this command:</span></span>
    
  ```
  Restore-AzureADMSDeletedDirectoryObject -Id <objectId>
  ```

7. <span data-ttu-id="8e830-166">Esse processo geralmente leva apenas alguns minutos, mas em alguns casos raros, pode levar até 24 horas para ser totalmente restaurado.</span><span class="sxs-lookup"><span data-stu-id="8e830-166">This process usually takes just a few minutes but in a few rare cases it can take as long as 24 hours to be completely restored.</span></span> <span data-ttu-id="8e830-167">Para verificar se o grupo foi restaurado, execute este comando no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8e830-167">To verify that the group has been successfully restored, run this command in PowerShell:</span></span>
    
  ```
  Get-AzureADGroup -ObjectId <objectId>
  ```

<span data-ttu-id="8e830-p110">Após a restauração ser concluída, o grupo deverá reaparecer no painel de navegação no Outlook e no Outlook na Web. Todo o conteúdo restaurado, inclusive o SharePoint e o Planner, deverá estar disponível para os membros do grupo novamente.</span><span class="sxs-lookup"><span data-stu-id="8e830-p110">Once the restore has successfully completed, the group should reappear on the navigation pane in Outlook and Outlook on the web. All restored content, including SharePoint and Planner, should be available to the group members again.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="8e830-170">Excluir permanentemente um grupo do Office 365</span><span class="sxs-lookup"><span data-stu-id="8e830-170">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="8e830-171">Às vezes, você pode querer limpar permanentemente um grupo sem esperar que o período de exclusão reversível de 30 dias expire.</span><span class="sxs-lookup"><span data-stu-id="8e830-171">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="8e830-172">Para fazer isso, inicie o PowerShell e execute este comando para obter a ID de objeto do grupo:</span><span class="sxs-lookup"><span data-stu-id="8e830-172">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="8e830-173">Anote a ID de objeto do grupo, ou grupos, que você deseja excluir permanentemente.</span><span class="sxs-lookup"><span data-stu-id="8e830-173">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8e830-174">Ao limpar o grupo, você removerá o grupo e os dados nele para sempre.</span><span class="sxs-lookup"><span data-stu-id="8e830-174">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="8e830-175">Para limpar o grupo, execute o seguinte comando no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8e830-175">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="8e830-p112">Para confirmar que o grupo foi limpo, execute o cmdlet  *Get-AzureADMSDeletedGroup*  novamente para confirmar que ele não aparece mais na lista de grupos temporariamente excluídos. Em alguns casos pode levar até 24 horas para que o grupo e todos os dados nele sejam excluídos permanentemente.</span><span class="sxs-lookup"><span data-stu-id="8e830-p112">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="8e830-178">Você tem dúvidas sobre os Grupos do Office 365?</span><span class="sxs-lookup"><span data-stu-id="8e830-178">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="8e830-179">Visite a [comunidade de tecnologia da Microsoft](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para postar perguntas e participar de conversas sobre grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8e830-179">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="8e830-180">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="8e830-180">Related articles</span></span>

[<span data-ttu-id="8e830-181">Gerenciar Grupos do Office 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e830-181">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="8e830-182">Excluir grupos usando o cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="8e830-182">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="8e830-183">Gerenciar as configurações do site de equipe conectado ao grupo</span><span class="sxs-lookup"><span data-stu-id="8e830-183">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="8e830-184">Excluir um grupo no Outlook</span><span class="sxs-lookup"><span data-stu-id="8e830-184">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
