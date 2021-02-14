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
description: Saiba como preservar arquivos e emails de um funcionário quando a pessoa sair da sua organização.
ms.openlocfilehash: 32f64efb30acb5438e5add8bcb897200951e6362
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780608"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="81d43-103">Obtenha acesso e faça backup dos dados de um usuário anterior</span><span class="sxs-lookup"><span data-stu-id="81d43-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="81d43-104">Quando um funcionário deixa sua organização, você provavelmente deseja acessar seus dados (documentos e emails) e revisá-los, fazer o back-up ou dar a um novo funcionário.</span><span class="sxs-lookup"><span data-stu-id="81d43-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="81d43-105">Acessar os documentos do OneDrive de um usuário antigo</span><span class="sxs-lookup"><span data-stu-id="81d43-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="81d43-106">Se você remover a licença de um usuário, mas não excluir a conta, poderá dar a si mesmo acesso ao conteúdo no OneDrive do usuário.</span><span class="sxs-lookup"><span data-stu-id="81d43-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="81d43-107">Se você excluir a conta do usuário, terá 30 dias por padrão para acessar os dados do OneDrive do usuário anterior.</span><span class="sxs-lookup"><span data-stu-id="81d43-107">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="81d43-108">[Saiba como definir a retenção do OneDrive para usuários excluídos.](/onedrive/set-retention)</span><span class="sxs-lookup"><span data-stu-id="81d43-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="81d43-109">Se você não restaurar uma [conta de usuário](/office365/admin/add-users/restore-user) nesse período, o conteúdo do OneDrive será excluído.</span><span class="sxs-lookup"><span data-stu-id="81d43-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="81d43-110">Para preservar os arquivos do OneDrive de um usuário anterior, primeiro dê a si mesmo acesso ao OneDrive e mova os arquivos que você deseja manter.</span><span class="sxs-lookup"><span data-stu-id="81d43-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="81d43-111">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="81d43-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="81d43-112">Selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="81d43-112">Select a user.</span></span>

3. <span data-ttu-id="81d43-113">No painel direito, selecione **OneDrive.**</span><span class="sxs-lookup"><span data-stu-id="81d43-113">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="81d43-114">Em **Obter acesso a arquivos,** selecione Criar link para **arquivos.**</span><span class="sxs-lookup"><span data-stu-id="81d43-114">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="81d43-115">Selecione o link para abrir o local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="81d43-115">Select the link to open the file location.</span></span> <span data-ttu-id="81d43-116">Baixe os arquivos em seu computador ou selecione **Mover** para **ou** Copiar para movê-los ou copiá-los para seu próprio OneDrive ou para uma biblioteca compartilhada.</span><span class="sxs-lookup"><span data-stu-id="81d43-116">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="81d43-117">Você pode mover ou copiar até 500 MB de arquivos e pastas por vez.</span><span class="sxs-lookup"><span data-stu-id="81d43-117">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="81d43-118">Quando você move ou copia documentos com histórico de versões, somente a versão mais recente é movida.</span><span class="sxs-lookup"><span data-stu-id="81d43-118">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="81d43-119">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="81d43-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="81d43-120">Selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="81d43-120">Select a user.</span></span>

3. <span data-ttu-id="81d43-121">No painel direito, expanda as **Configurações do OneDrive** e, ao lado do **Access,** selecione **arquivos do Access.**</span><span class="sxs-lookup"><span data-stu-id="81d43-121">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="81d43-122">Selecione o link para abrir o local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="81d43-122">Select the link to open the file location.</span></span> <span data-ttu-id="81d43-123">Baixe os arquivos em seu computador ou selecione **Mover** para **ou** Copiar para movê-los ou copiá-los para seu próprio OneDrive ou para uma biblioteca compartilhada.</span><span class="sxs-lookup"><span data-stu-id="81d43-123">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="81d43-124">Você pode mover ou copiar até 500 MB de arquivos e pastas por vez.</span><span class="sxs-lookup"><span data-stu-id="81d43-124">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="81d43-125">Quando você move ou copia documentos com histórico de versões, somente a versão mais recente é movida.</span><span class="sxs-lookup"><span data-stu-id="81d43-125">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="81d43-126">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="81d43-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="81d43-127">Selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="81d43-127">Select a user.</span></span>

3. <span data-ttu-id="81d43-128">No painel direito, expanda as **Configurações do OneDrive** e, ao lado do **Access,** selecione **arquivos do Access.**</span><span class="sxs-lookup"><span data-stu-id="81d43-128">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="81d43-129">Selecione o link para abrir o local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="81d43-129">Select the link to open the file location.</span></span> <span data-ttu-id="81d43-130">Baixe os arquivos em seu computador ou selecione **Mover** para **ou** Copiar para movê-los ou copiá-los para seu próprio OneDrive ou para uma biblioteca compartilhada.</span><span class="sxs-lookup"><span data-stu-id="81d43-130">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="81d43-131">Você pode mover ou copiar até 500 MB de arquivos e pastas por vez.</span><span class="sxs-lookup"><span data-stu-id="81d43-131">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="81d43-132">Quando você move ou copia documentos com histórico de versões, somente a versão mais recente é movida.</span><span class="sxs-lookup"><span data-stu-id="81d43-132">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="81d43-133">Revogar o acesso de administrador ao OneDrive de um usuário</span><span class="sxs-lookup"><span data-stu-id="81d43-133">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="81d43-134">Como administrador global, você pode dar a si mesmo acesso ao conteúdo no OneDrive de um usuário, mas talvez queira remover o acesso quando não precisar mais dele.</span><span class="sxs-lookup"><span data-stu-id="81d43-134">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="81d43-135">Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administração como</a> um administrador global ou administrador do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="81d43-135">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="81d43-136">Se você receber uma mensagem de que não tem permissão para acessar o centro de administração, você não tem permissões de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="81d43-136">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="81d43-137">Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administração como</a> um administrador global ou administrador do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="81d43-137">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="81d43-138">Se você receber uma mensagem de que não tem permissão para acessar o centro de administração, não terá permissões de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="81d43-138">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="81d43-139">Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administração como</a> um administrador global ou administrador do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="81d43-139">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="81d43-140">Se você receber uma mensagem de que não tem permissão para acessar o centro de administração, você não tem permissões de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="81d43-140">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="81d43-141">No painel esquerdo, selecione Centros **de administração do** \> **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="81d43-141">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="81d43-142">(Talvez seja necessário selecionar **Mostrar tudo** para ver a lista de centros de administração.)</span><span class="sxs-lookup"><span data-stu-id="81d43-142">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="81d43-143">Se o centro de administração do SharePoint clássico aparecer, selecione Abrir **agora** na parte superior da página para abrir o centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="81d43-143">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the SharePoint admin center.</span></span>

4. <span data-ttu-id="81d43-144">No painel esquerdo, selecione **Mais recursos.**</span><span class="sxs-lookup"><span data-stu-id="81d43-144">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="81d43-145">Em **Perfis de usuário,** selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="81d43-145">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="81d43-146">Em **Pessoas,** selecione **Gerenciar Perfis de Usuário.**</span><span class="sxs-lookup"><span data-stu-id="81d43-146">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="81d43-147">Insira o nome do usuário e selecione **Find**.</span><span class="sxs-lookup"><span data-stu-id="81d43-147">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="81d43-148">Clique com o botão direito do mouse no usuário e escolha Gerenciar proprietários **do conjunto de sites.**</span><span class="sxs-lookup"><span data-stu-id="81d43-148">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="81d43-149">Remova a pessoa que não precisa mais acessar os dados do usuário e selecione **OK.**</span><span class="sxs-lookup"><span data-stu-id="81d43-149">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="81d43-150">Acessar os dados do Outlook de um usuário anterior</span><span class="sxs-lookup"><span data-stu-id="81d43-150">Access the Outlook data of a former user</span></span>

<span data-ttu-id="81d43-151">Para salvar as mensagens de email, calendário, tarefas e contatos do ex-funcionário, exporte as informações para um Arquivo de Dados do Outlook (.pst).</span><span class="sxs-lookup"><span data-stu-id="81d43-151">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="81d43-152">[Adicione o email do ex-funcionário](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) ao Seu Outlook (se você redefinir a senha do [usuário,](reset-passwords.md)poderá defini-lo como algo que você só conhece.)</span><span class="sxs-lookup"><span data-stu-id="81d43-152">[Add the former employee's email](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="81d43-153">No Outlook, selecione **Arquivo.**</span><span class="sxs-lookup"><span data-stu-id="81d43-153">In Outlook, select **File**.</span></span>
    
    ![Esta é a aparência da faixa de opções no Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="81d43-155">Selecione **Abrir &amp; Exportação** \> **Importação/Exportação.**</span><span class="sxs-lookup"><span data-stu-id="81d43-155">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Comando Importar/Exportar no exibição Backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="81d43-157">Selecione **Exportar para um arquivo** e, em seguida, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="81d43-157">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![Exportar para uma opção de arquivo no Assistente para Importação e Exportação](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="81d43-159">Selecione **Arquivo de Dados do Outlook (.pst)** e, em seguida, selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="81d43-159">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="81d43-160">Selecione a conta que você deseja exportar selecionando o nome ou endereço de email, como Mailbox - Anne Weiler ou anne@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="81d43-160">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="81d43-161">Se você quiser exportar tudo em sua conta, incluindo email, calendário, contatos, tarefas e anotações, verifique se a caixa de seleção Incluir **subpastas** está marcada.</span><span class="sxs-lookup"><span data-stu-id="81d43-161">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="81d43-162">Você pode exportar uma conta por vez.</span><span class="sxs-lookup"><span data-stu-id="81d43-162">You can export one account at a time.</span></span> <span data-ttu-id="81d43-163">Se você quiser exportar várias contas, depois que uma conta for exportada, repita essas etapas.</span><span class="sxs-lookup"><span data-stu-id="81d43-163">If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![Caixa de diálogo Exportar Arquivo de Dados do Outlook com a pasta superior selecionada e Incluir subpastas marcadas](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="81d43-165">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="81d43-165">Select **Next**.</span></span>
    
8. <span data-ttu-id="81d43-166">Selecione **Procurar** para selecionar onde salvar o Arquivo de Dados do Outlook (.pst).</span><span class="sxs-lookup"><span data-stu-id="81d43-166">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="81d43-167">Digite um  *nome de arquivo* e selecione **OK** para continuar.</span><span class="sxs-lookup"><span data-stu-id="81d43-167">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="81d43-168">Se você já usou a exportação antes, o local da pasta anterior e o nome do arquivo aparecerão.</span><span class="sxs-lookup"><span data-stu-id="81d43-168">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="81d43-169">Digite um  *nome de arquivo diferente*  antes de selecionar **OK**.</span><span class="sxs-lookup"><span data-stu-id="81d43-169">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="81d43-170">Se você estiver exportando para um Arquivo de Dados do Outlook (.pst) já existente, em **Opções**, especifique o que fazer ao exportar itens que já existem no arquivo.</span><span class="sxs-lookup"><span data-stu-id="81d43-170">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="81d43-171">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="81d43-171">Select **Finish**.</span></span>
    
<span data-ttu-id="81d43-172">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span><span class="sxs-lookup"><span data-stu-id="81d43-172">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="81d43-173">Se você estiver criando um Arquivo de Dados do Outlook (.pst), uma senha opcional poderá ajudar a proteger o arquivo.</span><span class="sxs-lookup"><span data-stu-id="81d43-173">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="81d43-174">Quando a caixa de diálogo Criar  Arquivo de Dados  do **Outlook** for exibida, digite a senha nas caixas **Senha** e Verificar Senha e selecione **OK.**</span><span class="sxs-lookup"><span data-stu-id="81d43-174">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="81d43-175">Na caixa de diálogo Senha do Arquivo de Dados do **Outlook,** digite *a senha* e selecione **OK.**</span><span class="sxs-lookup"><span data-stu-id="81d43-175">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="81d43-176">Se você estiver exportando para um Arquivo de Dados do Outlook (.pst) existente protegido por senha, na caixa de diálogo Senha do Arquivo de Dados do **Outlook,** digite a senha e selecione **OK.**</span><span class="sxs-lookup"><span data-stu-id="81d43-176">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="81d43-177">Veja como exportar ou fazer backup de email, contatos e calendário para um arquivo [.pst do Outlook](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) no Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="81d43-177">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="81d43-178">Por padrão, seu email fica disponível offline por um período de 12 meses.</span><span class="sxs-lookup"><span data-stu-id="81d43-178">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="81d43-179">Se necessário, veja como aumentar [os dados disponíveis offline.](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)</span><span class="sxs-lookup"><span data-stu-id="81d43-179">If required, see how to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="81d43-180">Dar a outro usuário acesso ao email de um usuário antigo</span><span class="sxs-lookup"><span data-stu-id="81d43-180">Give another user access to a former user's email</span></span> 

<span data-ttu-id="81d43-181">Para dar acesso a mensagens de email, calendário, tarefas e contatos do ex-funcionário para outro funcionário, importe as informações para a caixa de entrada do Outlook de outro funcionário.</span><span class="sxs-lookup"><span data-stu-id="81d43-181">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="81d43-182">Você também pode converter a caixa de correio do [ex-usuário em](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) uma caixa de correio compartilhada ou encaminhar o email de um [ex-funcionário para outro funcionário.](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)</span><span class="sxs-lookup"><span data-stu-id="81d43-182">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="81d43-183">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span><span class="sxs-lookup"><span data-stu-id="81d43-183">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="81d43-184">Isso inicia o Assistente para Importação e Exportação.</span><span class="sxs-lookup"><span data-stu-id="81d43-184">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="81d43-185">Selecione **Importar de outro programa ou arquivo e,** em seguida, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="81d43-185">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![Assistente para Importação e Exportação](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="81d43-187">Select **Outlook Data File (.pst)**, and select **Next**.</span><span class="sxs-lookup"><span data-stu-id="81d43-187">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="81d43-188">Navegue até o arquivo .pst que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="81d43-188">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="81d43-189">Em **Opções,** escolha como deseja lidar com duplicatas</span><span class="sxs-lookup"><span data-stu-id="81d43-189">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="81d43-190">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="81d43-190">Select **Next**.</span></span>
    
7. <span data-ttu-id="81d43-191">Se uma senha tiver sido atribuída ao Arquivo de Dados do Outlook (.pst), insira a senha e selecione **OK.**</span><span class="sxs-lookup"><span data-stu-id="81d43-191">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="81d43-192">De definidas as opções de importação de itens.</span><span class="sxs-lookup"><span data-stu-id="81d43-192">Set the options for importing items.</span></span> <span data-ttu-id="81d43-193">As configurações padrão geralmente não precisam ser alteradas.</span><span class="sxs-lookup"><span data-stu-id="81d43-193">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="81d43-194">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="81d43-194">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="81d43-195">As etapas permanecem as mesmas para acessar o OneDrive e os dados de email de um usuário existente.</span><span class="sxs-lookup"><span data-stu-id="81d43-195">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="81d43-196">Se você quiser importar ou restaurar apenas alguns itens de um Arquivo de Dados do Outlook (.pst), poderá abrir o Arquivo de Dados do Outlook.</span><span class="sxs-lookup"><span data-stu-id="81d43-196">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="81d43-197">Em seguida, no painel de navegação, arraste os itens das pastas arquivo de dados do Outlook para suas pastas existentes do Outlook.</span><span class="sxs-lookup"><span data-stu-id="81d43-197">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="81d43-198">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="81d43-198">Related articles</span></span>
[<span data-ttu-id="81d43-199">Remover um ex-funcionário do Office 365</span><span class="sxs-lookup"><span data-stu-id="81d43-199">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="81d43-200">Adicionar e remover administradores em uma conta do OneDrive</span><span class="sxs-lookup"><span data-stu-id="81d43-200">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="81d43-201">Restaurar um OneDrive excluído</span><span class="sxs-lookup"><span data-stu-id="81d43-201">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="81d43-202">Retenção e exclusão do OneDrive</span><span class="sxs-lookup"><span data-stu-id="81d43-202">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  
