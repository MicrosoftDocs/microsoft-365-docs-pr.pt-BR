---
title: Obter acesso e realizar backup dos dados de um ex-usuário
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: Saiba como preservar os arquivos e emails de um funcionário quando a pessoa deixa sua organização.
ms.openlocfilehash: 11c946e5c242b05fea3a15b9427f36029c61082f
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142558"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="98c94-103">Obter acesso e realizar backup dos dados de um ex-usuário</span><span class="sxs-lookup"><span data-stu-id="98c94-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="98c94-104">Quando um funcionário deixa sua organização, você provavelmente deseja acessar seus dados (documentos e emails) e examiná-los, fazer o backup ou dar a ele um novo funcionário.</span><span class="sxs-lookup"><span data-stu-id="98c94-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="98c94-105">Acessar os documentos do OneDrive de um usuário antigo</span><span class="sxs-lookup"><span data-stu-id="98c94-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="98c94-106">Se você remover a licença de um usuário, mas não excluir a conta, poderá dar a si mesmo o acesso ao conteúdo no OneDrive do usuário.</span><span class="sxs-lookup"><span data-stu-id="98c94-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="98c94-107">Se você excluir a conta do usuário, você terá 30 dias por padrão para acessar os dados do OneDrive do usuário anterior.</span><span class="sxs-lookup"><span data-stu-id="98c94-107">If you delete the user's account, you have 30 days by default to access the former user’s OneDrive data.</span></span> <span data-ttu-id="98c94-108">[Saiba como definir a retenção do onedrive para usuários excluídos](/onedrive/set-retention).</span><span class="sxs-lookup"><span data-stu-id="98c94-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="98c94-109">Se você não [restaurar uma conta de usuário](/office365/admin/add-users/restore-user) dentro desse tempo, o conteúdo do onedrive será excluído.</span><span class="sxs-lookup"><span data-stu-id="98c94-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="98c94-110">Para preservar os arquivos do OneDrive de um usuário antigo, primeiro acesse seu OneDrive e mova os arquivos que você deseja manter.</span><span class="sxs-lookup"><span data-stu-id="98c94-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="98c94-111">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="98c94-111">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="98c94-112">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="98c94-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="98c94-113">Selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="98c94-113">Select a user.</span></span>

3. <span data-ttu-id="98c94-114">No painel direito, selecione **onedrive**.</span><span class="sxs-lookup"><span data-stu-id="98c94-114">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="98c94-115">Em **obter acesso a arquivos**, selecione **criar link para arquivos**.</span><span class="sxs-lookup"><span data-stu-id="98c94-115">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="98c94-116">Selecione o link para abrir o local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="98c94-116">Select the link to open the file location.</span></span> <span data-ttu-id="98c94-117">Baixe os arquivos para o seu computador ou selecione **mover para** ou **copiar para** para movê-los ou copiá-los para o seu próprio onedrive ou para uma biblioteca compartilhada.</span><span class="sxs-lookup"><span data-stu-id="98c94-117">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="98c94-118">Você pode mover ou copiar até 500 MB de arquivos e pastas por vez.</span><span class="sxs-lookup"><span data-stu-id="98c94-118">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="98c94-119">Quando você move ou copia documentos que têm histórico de versões, apenas a versão mais recente é movida.</span><span class="sxs-lookup"><span data-stu-id="98c94-119">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="98c94-120">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="98c94-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="98c94-121">Selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="98c94-121">Select a user.</span></span>

3. <span data-ttu-id="98c94-122">No painel direito, expanda **configurações do onedrive**e, em seguida, ao lado de **acesso**, selecione **arquivos do Access**.</span><span class="sxs-lookup"><span data-stu-id="98c94-122">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="98c94-123">Selecione o link para abrir o local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="98c94-123">Select the link to open the file location.</span></span> <span data-ttu-id="98c94-124">Baixe os arquivos para o seu computador ou selecione **mover para** ou **copiar para** para movê-los ou copiá-los para o seu próprio onedrive ou para uma biblioteca compartilhada.</span><span class="sxs-lookup"><span data-stu-id="98c94-124">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="98c94-125">Você pode mover ou copiar até 500 MB de arquivos e pastas por vez.</span><span class="sxs-lookup"><span data-stu-id="98c94-125">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="98c94-126">Quando você move ou copia documentos que têm histórico de versões, apenas a versão mais recente é movida.</span><span class="sxs-lookup"><span data-stu-id="98c94-126">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="98c94-127">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="98c94-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="98c94-128">Selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="98c94-128">Select a user.</span></span>

3. <span data-ttu-id="98c94-129">No painel direito, expanda **configurações do onedrive**e, em seguida, ao lado de **acesso**, selecione **arquivos do Access**.</span><span class="sxs-lookup"><span data-stu-id="98c94-129">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="98c94-130">Selecione o link para abrir o local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="98c94-130">Select the link to open the file location.</span></span> <span data-ttu-id="98c94-131">Baixe os arquivos para o seu computador ou selecione **mover para** ou **copiar para** para movê-los ou copiá-los para o seu próprio onedrive ou para uma biblioteca compartilhada.</span><span class="sxs-lookup"><span data-stu-id="98c94-131">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="98c94-132">Você pode mover ou copiar até 500 MB de arquivos e pastas por vez.</span><span class="sxs-lookup"><span data-stu-id="98c94-132">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="98c94-133">Quando você move ou copia documentos que têm histórico de versões, apenas a versão mais recente é movida.</span><span class="sxs-lookup"><span data-stu-id="98c94-133">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="98c94-134">Revogar o acesso do administrador ao OneDrive de um usuário</span><span class="sxs-lookup"><span data-stu-id="98c94-134">Revoke admin access to a user’s OneDrive</span></span>

<span data-ttu-id="98c94-135">Como administrador global, você pode dar a si mesmo acesso ao conteúdo no OneDrive de um usuário, mas talvez queira remover o acesso quando não precisar mais dele.</span><span class="sxs-lookup"><span data-stu-id="98c94-135">As global admin, you can give yourself access to the content in a user’s OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="98c94-136">Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Administração</a> como administrador global ou administrador do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="98c94-136">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="98c94-137">Se você receber uma mensagem informando que você não tem permissão para acessar o centro de administração, você não tem permissões de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="98c94-137">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="98c94-138">Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Administração</a> como administrador global ou administrador do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="98c94-138">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="98c94-139">Se você receber uma mensagem informando que você não tem permissão para acessar o centro de administração, você não tem permissões de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="98c94-139">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="98c94-140">Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Administração</a> como administrador global ou administrador do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="98c94-140">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="98c94-141">Se você receber uma mensagem informando que você não tem permissão para acessar o centro de administração, você não tem permissões de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="98c94-141">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="98c94-142">No painel esquerdo, selecione **central** \> de administração **do SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="98c94-142">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="98c94-143">(Talvez seja necessário selecionar **Mostrar tudo** para ver a lista de centros de administração.)</span><span class="sxs-lookup"><span data-stu-id="98c94-143">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="98c94-144">Se aparecer o centro de administração do SharePoint clássico, selecione **Abrir agora**, na parte superior da página, para abrir o novo centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="98c94-144">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

4. <span data-ttu-id="98c94-145">No painel esquerdo, selecione **mais recursos**.</span><span class="sxs-lookup"><span data-stu-id="98c94-145">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="98c94-146">Em **perfis de usuário**, selecione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="98c94-146">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="98c94-147">Em **pessoas**, selecione **gerenciar perfis de usuário**.</span><span class="sxs-lookup"><span data-stu-id="98c94-147">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="98c94-148">Insira o nome do usuário e selecione **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="98c94-148">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="98c94-149">Clique com o botão direito do mouse no usuário e escolha **gerenciar proprietários do conjunto de sites**.</span><span class="sxs-lookup"><span data-stu-id="98c94-149">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="98c94-150">Remova a pessoa que não precisa mais acessar os dados do usuário e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c94-150">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="98c94-151">Acessar os dados do Outlook de um usuário anterior</span><span class="sxs-lookup"><span data-stu-id="98c94-151">Access the Outlook data of a former user</span></span>

<span data-ttu-id="98c94-152">Para salvar as mensagens de email, calendário, tarefas e contatos do funcionário anterior, exporte as informações para um arquivo de dados do Outlook (. pst).</span><span class="sxs-lookup"><span data-stu-id="98c94-152">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="98c94-153">[Adicione o email do funcionário antigo](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) ao seu Outlook (se você [redefinir a senha do usuário](reset-passwords.md), você pode defini-la como algo que só você sabe.)</span><span class="sxs-lookup"><span data-stu-id="98c94-153">[Add the former employee's email](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="98c94-154">No Outlook, selecione **arquivo**.</span><span class="sxs-lookup"><span data-stu-id="98c94-154">In Outlook, select **File**.</span></span>
    
    ![Esta é a aparência da faixa de opções no Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="98c94-156">Selecione **abrir &amp; exportar** \> **importar/exportar**.</span><span class="sxs-lookup"><span data-stu-id="98c94-156">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Comando importar/exportar no modo de exibição Backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="98c94-158">Selecione **exportar para um arquivo**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="98c94-158">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![Exportar para uma opção de arquivo no assistente de importação e exportação](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="98c94-160">Selecione **arquivo de dados do Outlook (. pst)** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="98c94-160">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="98c94-161">Selecione a conta que você deseja exportar selecionando o nome ou o endereço de email, como caixa de correio-Anne Weiler ou anne@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="98c94-161">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="98c94-162">Se você deseja exportar tudo em sua conta, incluindo email, calendário, contatos, tarefas e anotações, verifique se a caixa de seleção **incluir subpastas** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="98c94-162">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="98c94-163">Você pode exportar uma conta por vez.</span><span class="sxs-lookup"><span data-stu-id="98c94-163">You can export one account at a time.</span></span> <span data-ttu-id="98c94-164">Se você quiser exportar várias contas, após uma conta ser exportada, repita essas etapas.</span><span class="sxs-lookup"><span data-stu-id="98c94-164">If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![Caixa de diálogo Exportar arquivo de dados do Outlook com a pasta principal selecionada e incluir subpastas verificadas](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="98c94-166">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="98c94-166">Select **Next**.</span></span>
    
8. <span data-ttu-id="98c94-167">Selecione **procurar** para selecionar onde salvar o arquivo de dados do Outlook (. pst).</span><span class="sxs-lookup"><span data-stu-id="98c94-167">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="98c94-168">Digite um *nome de arquivo*e, em seguida, selecione **OK** para continuar.</span><span class="sxs-lookup"><span data-stu-id="98c94-168">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="98c94-169">Se você tiver usado exportar antes, o local da pasta e o nome do arquivo anteriores serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="98c94-169">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="98c94-170">Digite um *nome de arquivo diferente* antes de selecionar **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c94-170">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="98c94-171">Se você estiver exportando para um Arquivo de Dados do Outlook (.pst) já existente, em **Opções**, especifique o que fazer ao exportar itens que já existem no arquivo.</span><span class="sxs-lookup"><span data-stu-id="98c94-171">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="98c94-172">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="98c94-172">Select **Finish**.</span></span>
    
<span data-ttu-id="98c94-173">O Outlook começa a exportação imediatamente, a menos que um novo arquivo de dados do Outlook (. pst) seja criado ou um arquivo protegido por senha seja usado.</span><span class="sxs-lookup"><span data-stu-id="98c94-173">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="98c94-174">Se você estiver criando um arquivo de dados do Outlook (. pst), uma senha opcional poderá ajudar a proteger o arquivo.</span><span class="sxs-lookup"><span data-stu-id="98c94-174">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="98c94-175">Quando a caixa de diálogo **criar arquivo de dados do Outlook** for exibida, digite a *senha* nas caixas **senha** e **Confirmar senha** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c94-175">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="98c94-176">Na caixa de diálogo **senha do arquivo de dados do Outlook** , digite a *senha*e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c94-176">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="98c94-177">Se você estiver exportando para um arquivo de dados do Outlook (. pst) existente protegido por senha, na caixa de diálogo **senha do arquivo de dados do Outlook** , digite a *senha*e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c94-177">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="98c94-178">Confira como [exportar ou fazer backup de email, contatos e calendário para um arquivo. pst do Outlook](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) no Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="98c94-178">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="98c94-179">Por padrão, seu email fica disponível offline por um período de 12 meses.</span><span class="sxs-lookup"><span data-stu-id="98c94-179">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="98c94-180">Se necessário, Confira como [aumentar os dados disponíveis offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span><span class="sxs-lookup"><span data-stu-id="98c94-180">If required, see how to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="98c94-181">Conceder a outro usuário acesso ao email de um usuário anterior</span><span class="sxs-lookup"><span data-stu-id="98c94-181">Give another user access to a former user's email</span></span> 

<span data-ttu-id="98c94-182">Para dar acesso às mensagens de email, calendário, tarefas e contatos do antigo funcionário para outro funcionário, importe as informações para a caixa de entrada do Outlook de outro funcionário.</span><span class="sxs-lookup"><span data-stu-id="98c94-182">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="98c94-183">Você também pode [converter a caixa de correio do usuário anterior em uma caixa de correio compartilhada](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) ou [encaminhar o email de um antigo funcionário para outro funcionário](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="98c94-183">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="98c94-184">No Outlook, vá para **arquivo** \> **abrir &amp; exportar** \> **importar/exportar**.</span><span class="sxs-lookup"><span data-stu-id="98c94-184">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="98c94-185">Isso inicia o assistente de importação e exportação.</span><span class="sxs-lookup"><span data-stu-id="98c94-185">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="98c94-186">Selecione **importar de outro programa ou arquivo**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="98c94-186">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![Assistente de importação e exportação](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="98c94-188">Selecione **arquivo de dados do Outlook (. pst)** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="98c94-188">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="98c94-189">Navegue até o arquivo. pst que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="98c94-189">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="98c94-190">Em **Opções**, escolha como você deseja lidar com duplicatas</span><span class="sxs-lookup"><span data-stu-id="98c94-190">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="98c94-191">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="98c94-191">Select **Next**.</span></span>
    
7. <span data-ttu-id="98c94-192">Se uma senha foi atribuída ao arquivo de dados do Outlook (. pst), insira a senha e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c94-192">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="98c94-193">Definir as opções de importação de itens.</span><span class="sxs-lookup"><span data-stu-id="98c94-193">Set the options for importing items.</span></span> <span data-ttu-id="98c94-194">As configurações padrão normalmente não precisam ser alteradas.</span><span class="sxs-lookup"><span data-stu-id="98c94-194">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="98c94-195">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="98c94-195">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="98c94-196">As etapas permanecem as mesmas para acessar os dados de email e do OneDrive de um usuário existente.</span><span class="sxs-lookup"><span data-stu-id="98c94-196">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="98c94-197">Se quiser importar ou restaurar apenas alguns itens de um arquivo de dados do Outlook (. pst), você pode abrir o arquivo de dados do Outlook.</span><span class="sxs-lookup"><span data-stu-id="98c94-197">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="98c94-198">Em seguida, no painel de navegação, arraste os itens das pastas de arquivos de dados do Outlook para suas pastas existentes do Outlook.</span><span class="sxs-lookup"><span data-stu-id="98c94-198">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="98c94-199">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="98c94-199">Related articles</span></span>
[<span data-ttu-id="98c94-200">Remover um ex-funcionário do Office 365</span><span class="sxs-lookup"><span data-stu-id="98c94-200">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="98c94-201">Adicionar e remover administradores em uma conta do OneDrive</span><span class="sxs-lookup"><span data-stu-id="98c94-201">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="98c94-202">Restaurar um OneDrive excluído</span><span class="sxs-lookup"><span data-stu-id="98c94-202">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="98c94-203">Retenção e exclusão do OneDrive</span><span class="sxs-lookup"><span data-stu-id="98c94-203">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  
