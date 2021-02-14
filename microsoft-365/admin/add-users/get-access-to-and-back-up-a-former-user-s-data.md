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
# <a name="get-access-to-and-back-up-a-former-users-data"></a>Obtenha acesso e faça backup dos dados de um usuário anterior


Quando um funcionário deixa sua organização, você provavelmente deseja acessar seus dados (documentos e emails) e revisá-los, fazer o back-up ou dar a um novo funcionário.
  
    
## <a name="access-a-former-users-onedrive-documents"></a>Acessar os documentos do OneDrive de um usuário antigo

Se você remover a licença de um usuário, mas não excluir a conta, poderá dar a si mesmo acesso ao conteúdo no OneDrive do usuário. Se você excluir a conta do usuário, terá 30 dias por padrão para acessar os dados do OneDrive do usuário anterior. [Saiba como definir a retenção do OneDrive para usuários excluídos.](/onedrive/set-retention) Se você não restaurar uma [conta de usuário](/office365/admin/add-users/restore-user) nesse período, o conteúdo do OneDrive será excluído. 

Para preservar os arquivos do OneDrive de um usuário anterior, primeiro dê a si mesmo acesso ao OneDrive e mova os arquivos que você deseja manter. 

::: moniker range="o365-worldwide"

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.  
    
2. Selecione um usuário.

3. No painel direito, selecione **OneDrive.** Em **Obter acesso a arquivos,** selecione Criar link para **arquivos.**

4. Selecione o link para abrir o local do arquivo. Baixe os arquivos em seu computador ou selecione **Mover** para **ou** Copiar para movê-los ou copiá-los para seu próprio OneDrive ou para uma biblioteca compartilhada. 

> [!NOTE]
> Você pode mover ou copiar até 500 MB de arquivos e pastas por vez.<br/>
> Quando você move ou copia documentos com histórico de versões, somente a versão mais recente é movida.  

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.  

2. Selecione um usuário.

3. No painel direito, expanda as **Configurações do OneDrive** e, ao lado do **Access,** selecione **arquivos do Access.**

4. Selecione o link para abrir o local do arquivo. Baixe os arquivos em seu computador ou selecione **Mover** para **ou** Copiar para movê-los ou copiá-los para seu próprio OneDrive ou para uma biblioteca compartilhada. 

> [!NOTE]
> Você pode mover ou copiar até 500 MB de arquivos e pastas por vez.<br/>
> Quando você move ou copia documentos com histórico de versões, somente a versão mais recente é movida.  

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>. 

2. Selecione um usuário.

3. No painel direito, expanda as **Configurações do OneDrive** e, ao lado do **Access,** selecione **arquivos do Access.**

4. Selecione o link para abrir o local do arquivo. Baixe os arquivos em seu computador ou selecione **Mover** para **ou** Copiar para movê-los ou copiá-los para seu próprio OneDrive ou para uma biblioteca compartilhada.  

> [!NOTE]
> Você pode mover ou copiar até 500 MB de arquivos e pastas por vez.<br/>
> Quando você move ou copia documentos com histórico de versões, somente a versão mais recente é movida.  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a>Revogar o acesso de administrador ao OneDrive de um usuário

Como administrador global, você pode dar a si mesmo acesso ao conteúdo no OneDrive de um usuário, mas talvez queira remover o acesso quando não precisar mais dele. 

::: moniker range="o365-worldwide"

1. Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administração como</a> um administrador global ou administrador do SharePoint. 

    Se você receber uma mensagem de que não tem permissão para acessar o centro de administração, você não tem permissões de administrador em sua organização.

::: moniker-end

::: moniker range="o365-germany"

1. Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administração como</a> um administrador global ou administrador do SharePoint.

    Se você receber uma mensagem de que não tem permissão para acessar o centro de administração, não terá permissões de administrador em sua organização.

::: moniker-end

::: moniker range="o365-21vianet"

1. Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administração como</a> um administrador global ou administrador do SharePoint.

    Se você receber uma mensagem de que não tem permissão para acessar o centro de administração, você não tem permissões de administrador em sua organização.

::: moniker-end

2. No painel esquerdo, selecione Centros **de administração do** \> **SharePoint.** (Talvez seja necessário selecionar **Mostrar tudo** para ver a lista de centros de administração.)

3. Se o centro de administração do SharePoint clássico aparecer, selecione Abrir **agora** na parte superior da página para abrir o centro de administração do SharePoint.

4. No painel esquerdo, selecione **Mais recursos.**

5. Em **Perfis de usuário,** selecione **Abrir**.

6. Em **Pessoas,** selecione **Gerenciar Perfis de Usuário.**

7. Insira o nome do usuário e selecione **Find**.

8. Clique com o botão direito do mouse no usuário e escolha Gerenciar proprietários **do conjunto de sites.**

9. Remova a pessoa que não precisa mais acessar os dados do usuário e selecione **OK.**

    
## <a name="access-the-outlook-data-of-a-former-user"></a>Acessar os dados do Outlook de um usuário anterior

Para salvar as mensagens de email, calendário, tarefas e contatos do ex-funcionário, exporte as informações para um Arquivo de Dados do Outlook (.pst).
  
1. [Adicione o email do ex-funcionário](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) ao Seu Outlook (se você redefinir a senha do [usuário,](reset-passwords.md)poderá defini-lo como algo que você só conhece.)
    
2. No Outlook, selecione **Arquivo.**
    
    ![Esta é a aparência da faixa de opções no Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. Selecione **Abrir &amp; Exportação** \> **Importação/Exportação.**
    
    ![Comando Importar/Exportar no exibição Backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. Selecione **Exportar para um arquivo** e, em seguida, selecione **Próximo**.
    
    ![Exportar para uma opção de arquivo no Assistente para Importação e Exportação](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. Selecione **Arquivo de Dados do Outlook (.pst)** e, em seguida, selecione **Próximo.**
    
6. Selecione a conta que você deseja exportar selecionando o nome ou endereço de email, como Mailbox - Anne Weiler ou anne@contoso.com. Se você quiser exportar tudo em sua conta, incluindo email, calendário, contatos, tarefas e anotações, verifique se a caixa de seleção Incluir **subpastas** está marcada. 
    
    > [!NOTE]
    > Você pode exportar uma conta por vez. Se você quiser exportar várias contas, depois que uma conta for exportada, repita essas etapas. 
  
    ![Caixa de diálogo Exportar Arquivo de Dados do Outlook com a pasta superior selecionada e Incluir subpastas marcadas](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. Selecione **Avançar**.
    
8. Selecione **Procurar** para selecionar onde salvar o Arquivo de Dados do Outlook (.pst). Digite um  *nome de arquivo* e selecione **OK** para continuar. 
    
    > [!NOTE]
    > Se você já usou a exportação antes, o local da pasta anterior e o nome do arquivo aparecerão. Digite um  *nome de arquivo diferente*  antes de selecionar **OK**. 
  
9. Se você estiver exportando para um Arquivo de Dados do Outlook (.pst) já existente, em **Opções**, especifique o que fazer ao exportar itens que já existem no arquivo.
    
10. Selecione **Concluir**.
    
Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.
  
   - Se você estiver criando um Arquivo de Dados do Outlook (.pst), uma senha opcional poderá ajudar a proteger o arquivo. Quando a caixa de diálogo Criar  Arquivo de Dados  do **Outlook** for exibida, digite a senha nas caixas **Senha** e Verificar Senha e selecione **OK.** Na caixa de diálogo Senha do Arquivo de Dados do **Outlook,** digite *a senha* e selecione **OK.**
    
  - Se você estiver exportando para um Arquivo de Dados do Outlook (.pst) existente protegido por senha, na caixa de diálogo Senha do Arquivo de Dados do **Outlook,** digite a senha e selecione **OK.**
    
Veja como exportar ou fazer backup de email, contatos e calendário para um arquivo [.pst do Outlook](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) no Outlook 2010. 
  
  
  > [!NOTE]
  > Por padrão, seu email fica disponível offline por um período de 12 meses. Se necessário, veja como aumentar [os dados disponíveis offline.](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)
 
## <a name="give-another-user-access-to-a-former-users-email"></a>Dar a outro usuário acesso ao email de um usuário antigo 

Para dar acesso a mensagens de email, calendário, tarefas e contatos do ex-funcionário para outro funcionário, importe as informações para a caixa de entrada do Outlook de outro funcionário.

> [!NOTE]
> Você também pode converter a caixa de correio do [ex-usuário em](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) uma caixa de correio compartilhada ou encaminhar o email de um [ex-funcionário para outro funcionário.](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)

  
1. In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.
    
    Isso inicia o Assistente para Importação e Exportação.
    
2. Selecione **Importar de outro programa ou arquivo e,** em seguida, selecione **Próximo**.
    
    ![Assistente para Importação e Exportação](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. Select **Outlook Data File (.pst)**, and select **Next**.
    
4. Navegue até o arquivo .pst que você deseja importar.
    
5. Em **Opções,** escolha como deseja lidar com duplicatas
    
6. Selecione **Avançar**.
    
7. Se uma senha tiver sido atribuída ao Arquivo de Dados do Outlook (.pst), insira a senha e selecione **OK.**
    
8. De definidas as opções de importação de itens. As configurações padrão geralmente não precisam ser alteradas.
    
9. Selecione **Concluir**.

> [!NOTE]
> As etapas permanecem as mesmas para acessar o OneDrive e os dados de email de um usuário existente.
    
> [!TIP]
> Se você quiser importar ou restaurar apenas alguns itens de um Arquivo de Dados do Outlook (.pst), poderá abrir o Arquivo de Dados do Outlook. Em seguida, no painel de navegação, arraste os itens das pastas arquivo de dados do Outlook para suas pastas existentes do Outlook. 
  
  
## <a name="related-articles"></a>Artigos relacionados
[Remover um ex-funcionário do Office 365](remove-former-employee.md)

[Adicionar e remover administradores em uma conta do OneDrive](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[Restaurar um OneDrive excluído](/onedrive/restore-deleted-onedrive)
  
[Retenção e exclusão do OneDrive](/onedrive/retention-and-deletion)
  
