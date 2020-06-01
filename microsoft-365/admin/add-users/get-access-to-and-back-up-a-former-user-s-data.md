---
title: Obtenha acesso e faça backup dos dados de um usuário anterior
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: Saiba como preservar os arquivos e emails de um funcionário quando a pessoa deixa sua organização.
ms.openlocfilehash: 13cc1117c52a45f4ec1389d2e8b9f0189f4730e1
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/31/2020
ms.locfileid: "44431708"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="07365-103">Obtenha acesso e faça backup dos dados de um usuário anterior</span><span class="sxs-lookup"><span data-stu-id="07365-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="07365-104">Quando um funcionário deixa sua organização, você provavelmente deseja acessar seus dados (documentos e emails) e examiná-los, fazer o backup ou dar a ele um novo funcionário.</span><span class="sxs-lookup"><span data-stu-id="07365-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="07365-105">Acessar os documentos do OneDrive de um usuário antigo</span><span class="sxs-lookup"><span data-stu-id="07365-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="07365-106">Se você remover a licença de um usuário, mas não excluir a conta, poderá dar a si mesmo o acesso ao conteúdo no OneDrive do usuário.</span><span class="sxs-lookup"><span data-stu-id="07365-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="07365-107">Se você excluir a conta do usuário, você terá 30 dias por padrão para acessar os dados do OneDrive do usuário anterior.</span><span class="sxs-lookup"><span data-stu-id="07365-107">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="07365-108">[Saiba como definir a retenção do onedrive para usuários excluídos](/onedrive/set-retention).</span><span class="sxs-lookup"><span data-stu-id="07365-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="07365-109">Se você não [restaurar uma conta de usuário](/office365/admin/add-users/restore-user) dentro desse tempo, o conteúdo do onedrive será excluído.</span><span class="sxs-lookup"><span data-stu-id="07365-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="07365-110">Para preservar os arquivos do OneDrive de um usuário antigo, primeiro acesse seu OneDrive e mova os arquivos que você deseja manter.</span><span class="sxs-lookup"><span data-stu-id="07365-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="07365-111">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="07365-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="07365-112">Selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="07365-112">Select a user.</span></span>

3. <span data-ttu-id="07365-113">No painel direito, selecione **onedrive**.</span><span class="sxs-lookup"><span data-stu-id="07365-113">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="07365-114">Em **obter acesso a arquivos**, selecione **criar link para arquivos**.</span><span class="sxs-lookup"><span data-stu-id="07365-114">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="07365-115">Selecione o link para abrir o local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="07365-115">Select the link to open the file location.</span></span> <span data-ttu-id="07365-116">Baixe os arquivos para o seu computador ou selecione **mover para** ou **copiar para** para movê-los ou copiá-los para o seu próprio onedrive ou para uma biblioteca compartilhada.</span><span class="sxs-lookup"><span data-stu-id="07365-116">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="07365-117">Você pode mover ou copiar até 500 MB de arquivos e pastas por vez.</span><span class="sxs-lookup"><span data-stu-id="07365-117">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="07365-118">Quando você move ou copia documentos que têm histórico de versões, apenas a versão mais recente é movida.</span><span class="sxs-lookup"><span data-stu-id="07365-118">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="07365-119">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="07365-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="07365-120">Selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="07365-120">Select a user.</span></span>

3. <span data-ttu-id="07365-121">No painel direito, expanda **configurações do onedrive**e, em seguida, ao lado de **acesso**, selecione **arquivos do Access**.</span><span class="sxs-lookup"><span data-stu-id="07365-121">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="07365-122">Selecione o link para abrir o local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="07365-122">Select the link to open the file location.</span></span> <span data-ttu-id="07365-123">Baixe os arquivos para o seu computador ou selecione **mover para** ou **copiar para** para movê-los ou copiá-los para o seu próprio onedrive ou para uma biblioteca compartilhada.</span><span class="sxs-lookup"><span data-stu-id="07365-123">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="07365-124">Você pode mover ou copiar até 500 MB de arquivos e pastas por vez.</span><span class="sxs-lookup"><span data-stu-id="07365-124">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="07365-125">Quando você move ou copia documentos que têm histórico de versões, apenas a versão mais recente é movida.</span><span class="sxs-lookup"><span data-stu-id="07365-125">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="07365-126">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="07365-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="07365-127">Selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="07365-127">Select a user.</span></span>

3. <span data-ttu-id="07365-128">No painel direito, expanda **configurações do onedrive**e, em seguida, ao lado de **acesso**, selecione **arquivos do Access**.</span><span class="sxs-lookup"><span data-stu-id="07365-128">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="07365-129">Selecione o link para abrir o local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="07365-129">Select the link to open the file location.</span></span> <span data-ttu-id="07365-130">Baixe os arquivos para o seu computador ou selecione **mover para** ou **copiar para** para movê-los ou copiá-los para o seu próprio onedrive ou para uma biblioteca compartilhada.</span><span class="sxs-lookup"><span data-stu-id="07365-130">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="07365-131">Você pode mover ou copiar até 500 MB de arquivos e pastas por vez.</span><span class="sxs-lookup"><span data-stu-id="07365-131">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="07365-132">Quando você move ou copia documentos que têm histórico de versões, apenas a versão mais recente é movida.</span><span class="sxs-lookup"><span data-stu-id="07365-132">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="07365-133">Revogar o acesso do administrador ao OneDrive de um usuário</span><span class="sxs-lookup"><span data-stu-id="07365-133">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="07365-134">Como administrador global, você pode dar a si mesmo acesso ao conteúdo no OneDrive de um usuário, mas talvez queira remover o acesso quando não precisar mais dele.</span><span class="sxs-lookup"><span data-stu-id="07365-134">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="07365-135">Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Administração</a> como administrador global ou administrador do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="07365-135">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="07365-136">Se você receber uma mensagem informando que você não tem permissão para acessar o centro de administração, você não tem permissões de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="07365-136">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="07365-137">Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Administração</a> como administrador global ou administrador do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="07365-137">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="07365-138">Se você receber uma mensagem informando que você não tem permissão para acessar o centro de administração, você não tem permissões de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="07365-138">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="07365-139">Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Administração</a> como administrador global ou administrador do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="07365-139">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="07365-140">Se você receber uma mensagem informando que você não tem permissão para acessar o centro de administração, você não tem permissões de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="07365-140">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="07365-141">No painel esquerdo, selecione **central de administração** \> **do SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="07365-141">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="07365-142">(Talvez seja necessário selecionar **Mostrar tudo** para ver a lista de centros de administração.)</span><span class="sxs-lookup"><span data-stu-id="07365-142">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="07365-143">Se o centro de administração do SharePoint clássico aparecer, selecione **abrir agora** na parte superior da página para abrir o centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="07365-143">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the SharePoint admin center.</span></span>

4. <span data-ttu-id="07365-144">No painel esquerdo, selecione **mais recursos**.</span><span class="sxs-lookup"><span data-stu-id="07365-144">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="07365-145">Em **perfis de usuário**, selecione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="07365-145">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="07365-146">Em **pessoas**, selecione **gerenciar perfis de usuário**.</span><span class="sxs-lookup"><span data-stu-id="07365-146">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="07365-147">Insira o nome do usuário e selecione **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="07365-147">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="07365-148">Clique com o botão direito do mouse no usuário e escolha **gerenciar proprietários do conjunto de sites**.</span><span class="sxs-lookup"><span data-stu-id="07365-148">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="07365-149">Remova a pessoa que não precisa mais acessar os dados do usuário e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="07365-149">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="07365-150">Acessar os dados do Outlook de um usuário anterior</span><span class="sxs-lookup"><span data-stu-id="07365-150">Access the Outlook data of a former user</span></span>

<span data-ttu-id="07365-151">Para salvar as mensagens de email, calendário, tarefas e contatos do funcionário anterior, exporte as informações para um arquivo de dados do Outlook (. pst).</span><span class="sxs-lookup"><span data-stu-id="07365-151">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="07365-152">[Adicione o email do funcionário antigo](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) ao seu Outlook (se você [redefinir a senha do usuário](reset-passwords.md), você pode defini-la como algo que só você sabe.)</span><span class="sxs-lookup"><span data-stu-id="07365-152">[Add the former employee's email](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="07365-153">No Outlook, selecione **arquivo**.</span><span class="sxs-lookup"><span data-stu-id="07365-153">In Outlook, select **File**.</span></span>
    
    ![Esta é a aparência da faixa de opções no Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="07365-155">Selecione **abrir &amp; Exportar** \> **importar/exportar**.</span><span class="sxs-lookup"><span data-stu-id="07365-155">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Comando importar/exportar no modo de exibição Backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="07365-157">Selecione **exportar para um arquivo**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="07365-157">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![Exportar para uma opção de arquivo no assistente de importação e exportação](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="07365-159">Selecione **arquivo de dados do Outlook (. pst)** e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="07365-159">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="07365-160">Selecione a conta que você deseja exportar selecionando o nome ou o endereço de email, como caixa de correio-Anne Weiler ou anne@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="07365-160">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="07365-161">Se você deseja exportar tudo em sua conta, incluindo email, calendário, contatos, tarefas e anotações, verifique se a caixa de seleção **incluir subpastas** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="07365-161">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="07365-162">Você pode exportar uma conta por vez.</span><span class="sxs-lookup"><span data-stu-id="07365-162">You can export one account at a time.</span></span> <span data-ttu-id="07365-163">Se você quiser exportar várias contas, após uma conta ser exportada, repita essas etapas.</span><span class="sxs-lookup"><span data-stu-id="07365-163">If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![Caixa de diálogo Exportar arquivo de dados do Outlook com a pasta principal selecionada e incluir subpastas verificadas](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="07365-165">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="07365-165">Select **Next**.</span></span>
    
8. <span data-ttu-id="07365-166">Selecione **procurar** para selecionar onde salvar o arquivo de dados do Outlook (. pst).</span><span class="sxs-lookup"><span data-stu-id="07365-166">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="07365-167">Digite um *nome de arquivo*e, em seguida, selecione **OK** para continuar.</span><span class="sxs-lookup"><span data-stu-id="07365-167">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="07365-168">Se você tiver usado exportar antes, o local da pasta e o nome do arquivo anteriores serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="07365-168">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="07365-169">Digite um *nome de arquivo diferente* antes de selecionar **OK**.</span><span class="sxs-lookup"><span data-stu-id="07365-169">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="07365-170">Se você estiver exportando para um Arquivo de Dados do Outlook (.pst) já existente, em **Opções**, especifique o que fazer ao exportar itens que já existem no arquivo.</span><span class="sxs-lookup"><span data-stu-id="07365-170">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="07365-171">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="07365-171">Select **Finish**.</span></span>
    
<span data-ttu-id="07365-172">O Outlook começa a exportação imediatamente, a menos que um novo arquivo de dados do Outlook (. pst) seja criado ou um arquivo protegido por senha seja usado.</span><span class="sxs-lookup"><span data-stu-id="07365-172">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="07365-173">Se você estiver criando um arquivo de dados do Outlook (. pst), uma senha opcional poderá ajudar a proteger o arquivo.</span><span class="sxs-lookup"><span data-stu-id="07365-173">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="07365-174">Quando a caixa de diálogo **criar arquivo de dados do Outlook** for exibida, digite a *senha* nas caixas **senha** e **Confirmar senha** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="07365-174">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="07365-175">Na caixa de diálogo **senha do arquivo de dados do Outlook** , digite a *senha*e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="07365-175">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="07365-176">Se você estiver exportando para um arquivo de dados do Outlook (. pst) existente protegido por senha, na caixa de diálogo **senha do arquivo de dados do Outlook** , digite a *senha*e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="07365-176">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="07365-177">Confira como [exportar ou fazer backup de email, contatos e calendário para um arquivo. pst do Outlook](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) no Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="07365-177">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="07365-178">Por padrão, seu email fica disponível offline por um período de 12 meses.</span><span class="sxs-lookup"><span data-stu-id="07365-178">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="07365-179">Se necessário, Confira como [aumentar os dados disponíveis offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span><span class="sxs-lookup"><span data-stu-id="07365-179">If required, see how to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="07365-180">Conceder a outro usuário acesso ao email de um usuário anterior</span><span class="sxs-lookup"><span data-stu-id="07365-180">Give another user access to a former user's email</span></span> 

<span data-ttu-id="07365-181">Para dar acesso às mensagens de email, calendário, tarefas e contatos do antigo funcionário para outro funcionário, importe as informações para a caixa de entrada do Outlook de outro funcionário.</span><span class="sxs-lookup"><span data-stu-id="07365-181">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="07365-182">Você também pode [converter a caixa de correio do usuário anterior em uma caixa de correio compartilhada](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) ou [encaminhar o email de um antigo funcionário para outro funcionário](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="07365-182">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="07365-183">No Outlook, vá para **arquivo** \> **abrir &amp; Exportar** \> **importar/exportar**.</span><span class="sxs-lookup"><span data-stu-id="07365-183">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="07365-184">Isso inicia o assistente de importação e exportação.</span><span class="sxs-lookup"><span data-stu-id="07365-184">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="07365-185">Selecione **importar de outro programa ou arquivo**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="07365-185">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![Assistente de importação e exportação](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="07365-187">Selecione **arquivo de dados do Outlook (. pst)** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="07365-187">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="07365-188">Navegue até o arquivo. pst que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="07365-188">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="07365-189">Em **Opções**, escolha como você deseja lidar com duplicatas</span><span class="sxs-lookup"><span data-stu-id="07365-189">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="07365-190">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="07365-190">Select **Next**.</span></span>
    
7. <span data-ttu-id="07365-191">Se uma senha foi atribuída ao arquivo de dados do Outlook (. pst), insira a senha e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="07365-191">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="07365-192">Definir as opções de importação de itens.</span><span class="sxs-lookup"><span data-stu-id="07365-192">Set the options for importing items.</span></span> <span data-ttu-id="07365-193">As configurações padrão normalmente não precisam ser alteradas.</span><span class="sxs-lookup"><span data-stu-id="07365-193">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="07365-194">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="07365-194">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="07365-195">As etapas permanecem as mesmas para acessar os dados de email e do OneDrive de um usuário existente.</span><span class="sxs-lookup"><span data-stu-id="07365-195">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="07365-196">Se quiser importar ou restaurar apenas alguns itens de um arquivo de dados do Outlook (. pst), você pode abrir o arquivo de dados do Outlook.</span><span class="sxs-lookup"><span data-stu-id="07365-196">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="07365-197">Em seguida, no painel de navegação, arraste os itens das pastas de arquivos de dados do Outlook para suas pastas existentes do Outlook.</span><span class="sxs-lookup"><span data-stu-id="07365-197">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="07365-198">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="07365-198">Related articles</span></span>
[<span data-ttu-id="07365-199">Remover um ex-funcionário do Office 365</span><span class="sxs-lookup"><span data-stu-id="07365-199">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="07365-200">Adicionar e remover administradores em uma conta do OneDrive</span><span class="sxs-lookup"><span data-stu-id="07365-200">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="07365-201">Restaurar um OneDrive excluído</span><span class="sxs-lookup"><span data-stu-id="07365-201">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="07365-202">Retenção e exclusão do OneDrive</span><span class="sxs-lookup"><span data-stu-id="07365-202">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  
