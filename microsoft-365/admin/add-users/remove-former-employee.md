---
title: Remover um ex-funcionário
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
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: 'Siga esta lista de verificação para remover um funcionário do Microsoft 365 e dados seguros. '
ms.openlocfilehash: 51fd26835cd74fa8403437397d37395fcf1c7301
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844853"
---
# <a name="remove-a-former-employee"></a>Remover um ex-funcionário

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
## <a name="sign-out-now"></a>Sair agora!

::: moniker range="o365-worldwide"

Assista a um pequeno vídeo sobre como remover um funcionário. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Se você achou esse vídeo útil, Confira as [ séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

Para impedir que um funcionário faça logon:

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Selecione a caixa ao lado do nome do usuário e, em seguida, selecione **Redefinir senha**.

3. Insira uma nova senha e, em seguida, selecione **Redefinir**. (Não o envie para eles.)
    
4. Selecione o nome do usuário para ir para o painel de propriedades e, na guia **onedrive** , selecione **Iniciar saída**.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Selecione o usuário e, em seguida, selecione **Redefinir senha**.

3. Insira uma nova senha e, em seguida, selecione **Redefinir**. (Não o envie para eles.)

4. Selecione o usuário novamente, expanda **configurações do onedrive**e, em seguida, selecione **Iniciar** ao lado de **sair**.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Selecione o usuário e, em seguida, selecione **Redefinir senha**.

3. Insira uma nova senha e, em seguida, selecione **Redefinir**. (Não o envie para eles.)

4. Selecione o usuário novamente, expanda **configurações do onedrive**e, em seguida, selecione **Iniciar** ao lado de **sair**.

::: moniker-end

    
Dentro de uma hora ou após elas saírem da página atual do Microsoft 365, elas serão solicitadas a entrar novamente. (Um token de acesso é bom por uma hora, portanto, a linha do tempo depende de quanto tempo resta naquele token e se ele navegará de sua página da Web atual.)
  
 **AVISO DE LIMITAÇÃO**: se o usuário estiver no Outlook na Web, apenas clicando em itens da caixa de correio, é possível que ele não seja excluído imediatamente. Assim que eles selecionam um bloco diferente, como o OneDrive, ou atualizam o navegador, a saída é iniciada. 
  
Para usar o PowerShell para desconectar um usuário imediatamente, confira o cmdlet [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345). 
  
Para saber mais sobre quanto tempo é preciso para excluir alguém do email, confira [O que você precisa saber sobre o encerramento da sessão de email de um funcionário](#what-you-need-to-know-about-terminating-an-employees-email-session).
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>Visão geral de todas as etapas para remover um funcionário e proteger dados
<a name="bkmk_now"> </a>

Uma pergunta que recebemos frequentemente é: o que posso fazer para proteger os dados quando um funcionário deixa a organização? Este artigo explica como bloquear o acesso ao Microsoft 365 e as etapas que você deve seguir para proteger seus dados.
  
> [!NOTE]
> Se você for um administrador global, poderá excluir o funcionário, encaminhar seu email, escolher o que fazer com o conteúdo do OneDrive usando a nova experiência interativa. Para obter mais informações, consulte [Administração Global: excluir um usuário](remove-former-employee.md). No entanto, recomendamos concluir todas as etapas adicionais listadas aqui para garantir que o funcionário não tenha acesso aos dados da sua empresa. 
  
Here's a quick overview. Each step is explained in detail in this article.
  
|||
|:-----|:-----|
|**Etapa** <br/> |**Por que fazer isso** <br/> |
|1. [Salvar o conteúdo da caixa de correio de um ex-funcionário](#save-the-contents-of-a-former-employees-mailbox) <br/> |Isso é útil para a pessoa que assumirá a função do funcionário ou em caso de litígio.  <br/> |
|2. [Encaminhar o email do ex-funcionário a outro funcionário ou convertê-lo em uma caixa de correio compartilhada](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.  <br/> |
|3. [Apagar e bloquear o dispositivo móvel de um ex-funcionário](#wipe-and-block-a-former-employees-mobile-device) <br/> |Remove seus dados comerciais do telefone ou tablet.  <br/> |
|4. [bloquear o acesso de um antigo funcionário aos dados do Microsoft 365](#block-a-former-employees-access-to-microsoft-365-data)<br/> |Ele impede que a pessoa acesse sua antiga caixa de correio e dados da Microsoft 365.  <br/><br/> **Dica**: ao bloquear o acesso de um usuário, você ainda está pagando por sua licença. É preciso excluir a licença da sua assinatura para deixar de pagar por ela (etapa 5).           |
|5. [Mover o conteúdo do OneDrive do funcionário](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |Quando você remove apenas a licença e não exclui a conta do usuário, o conteúdo do OneDrive permanece acessível para você mesmo após os 30 dias.  <br/><br/> Before you delete the account, you should move the content of their OneDrive to another location that's easy for you to access. After you delete an employee's account, the content in their OneDrive is retained for **30** days. During that 30 days, however, you can restore the user's account, and gain access to their OneDrive content. If you restore the user's account, the OneDrive content will remain accessible to you even after 30 days.  <br/> |
|5a. What if the person used their personal computer to access OneDrive and SharePoint?  <br/> |Se ela usou um computador pessoal em vez de um computador corporativo para baixar arquivos do OneDrive e do SharePoint, não há nenhuma maneira de apagar os arquivos armazenados por ela.  <br/><br/> Ela continuará a ter acesso a todos os arquivos que foram sincronizados no computador dela.  <br/> |
|6. [remover e excluir a licença do Microsoft 365 de um funcionário antigo](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person.  <br/><br/> When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  <br/> |
|7. [Excluir a conta de usuário de um ex-funcionário](#delete-a-former-employees-user-account)<br/> |Isso remove a conta do seu centro de administração. Mantenha as coisas organizadas.  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>Salvar o conteúdo da caixa de correio de um ex-funcionário
<a name="bkmk_preserve"> </a>

Há duas maneiras de salvar o conteúdo da caixa de correio do ex-funcionário:
  
1. Add the former employee's email address to your version of Outlook 2013 or 2016, and then export the data to a .pst file. You can import the data to another email account as needed. To learn how to do this, see [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).
    
    OU
    
2. Place a Litigation Hold or In-Place Hold on the mailbox before the deleting the user account. This is much more complicated than the first option but worth doing if: your Enterprise plan includes archiving and legal hold, litigation is a possibility, and you have a technically strong IT department.
    
    Depois de converter a caixa de correio para uma "caixa de correio inativa", os administradores, agentes de conformidade ou gerentes de registros podem usar as ferramentas de Bloqueio e Descoberta Eletrônica In-loco no Exchange Online para acessar e pesquisar o conteúdo.
    
    As caixas de correio inativas não podem receber emails e não são exibidas no catálogo de endereços compartilhados da sua organização ou em outras listas.
    
    Para saber como colocar uma retenção em uma caixa de correio, consulte [gerenciar caixas de correio inativas no Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>Encaminhar o email do ex-funcionário a outro funcionário ou convertê-lo em uma caixa de correio compartilhada
<a name="bkmk_forward"> </a>

Nesta etapa, você atribui o endereço de email do ex-funcionário para outro funcionário ou [converte a caixa de correio do usuário em uma caixa de correio compartilhada](../email/convert-user-mailbox-to-shared-mailbox.md) que você tenha criado. 
  
- Creating a shared mailbox is the less expensive way to go because you won't have to pay for a license **as long as the mailbox is smaller than 50GB**. Over 50GB and you'll need to assign a license to it. 
    
- If you convert the mailbox to a shared mailbox, all the old email will be available, too. This can take up a lot of space.
    
- Quando você configura o encaminhamento de email, apenas os  *novos*  emails enviados ao ex-funcionário são enviados para o funcionário atual. 
    
- O encaminhamento de email requer a atribuição de uma licença para a conta do ex-funcionário.
    
 > [!IMPORTANT] 
 > Se você estiver configurando o encaminhamento de emails ou uma caixa de correio compartilhada, no final, não exclua a conta do funcionário anterior. Ela deve existir para ancorar o encaminhamento de email ou a caixa de correio compartilhada. 

::: moniker range="o365-worldwide"  

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Selecione o nome do funcionário que você deseja bloquear e, em seguida, selecione a guia **email** .

3. Em **encaminhamento de email**, selecione **gerenciar encaminhamento de email**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Selecione **Salvar**. 
    
6. Lembre-se de não excluir a conta do ex-funcionário.
 
::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Selecione o funcionário que você deseja bloquear e expandir **as configurações de email**.

3. Ao lado de **encaminhamento de email**, selecione **Editar**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Selecione **Salvar**. 
    
6. Lembre-se de não excluir a conta do ex-funcionário.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Selecione o funcionário que você deseja bloquear e expandir **as configurações de email**.

3. Ao lado de **encaminhamento de email**, selecione **Editar**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Selecione **Salvar**. 
    
6. Lembre-se de não excluir a conta do ex-funcionário.

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>Apagar e bloquear o dispositivo móvel de um ex-funcionário
<a name="bkmk_mobile"> </a>

Se o ex-funcionário tinha um telefone da organização, você pode usar o Centro de administração do Exchange para apagar e bloquear o dispositivo de modo que todos os dados da organização sejam removidos do dispositivo e que ele não possa mais se conectar ao Office 365.
  

1. Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.

3. No Centro de administração do Exchange, navegue até **Destinatários** \> **Caixas de Correio**. 
    
4. Selecione o usuário e, em **dispositivos móveis**, selecione **Exibir detalhes**. 
    
5. Na página **detalhes do dispositivo móvel** , em **dispositivos móveis**, selecione o dispositivo móvel, selecione **apagar dados** ![ apagar dispositivo ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) e, em seguida, selecione **Bloquear**. 
    
6. Selecione **Salvar**. 
    
    **Tip**: Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service. You should also disable any Blackberry devices for the user. Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user. 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>Bloquear o acesso de um antigo funcionário aos dados do Microsoft 365
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > Bloquear uma conta pode levar até 24 horas para entrar em vigor. Se você precisar evitar imediatamente o acesso de entrada de um usuário, deverá redefinir a [senha](reset-passwords.md) e, em seguida, iniciar um evento de ocorrência única que o desconectará das sessões do Microsoft 365 em todos os dispositivos. Confira [Sair agora!](#sign-out-now)
 

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Selecione o nome do funcionário que você deseja bloquear e, sob o nome do usuário, selecione o símbolo para **bloquear este usuário**.

3. Selecione **bloquear o usuário para entrar**e, em seguida, selecione **salvar**. 

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Selecione o funcionário que você deseja bloquear e, em seguida, selecione **bloqueio de entrada**.

3. Selecione **bloquear o usuário para entrar**e, em seguida, selecione **salvar**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Selecione o funcionário que você deseja bloquear e, em seguida, selecione **bloqueio de entrada**.

3. Selecione **bloquear o usuário para entrar**e, em seguida, selecione **salvar**. 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Bloquear o acesso de um ex-funcionário ao email (Exchange Online)
<a name="bkmk_block_email"> </a>

Se você tiver email como parte da sua assinatura do Microsoft 365, você precisará fazer logon no centro de administração do Exchange para executar estas etapas para impedir que seu funcionário anterior acesse seus emails.
  

1. Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.
     
2. No Centro de administração do Exchange, navegue até **Destinatários** \> **Caixas de Correio**. 
    
3. Clique duas vezes no usuário e vá para a página **recursos de caixa de correio** . Em **dispositivos móveis**, selecione **desabilitar o Exchange ActiveSync** e **desabilitar o OWA para dispositivos** e responda **Sim** para ambos quando solicitado. 
    
4. Em **conectividade de email**, selecione **desabilitar** e responder **Sim** quando solicitado. 
    
## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>Remover e excluir a licença do Microsoft 365 de um funcionário antigo
<a name="bkmk_remove"> </a>

Portanto, você não continua pagando por uma licença depois que alguém deixa sua organização, você precisa remover a licença do Microsoft 365 e excluí-la da sua assinatura. Se preferir não excluir a licença da assinatura, é possível atribuí-la a outro usuário.
  
Quando você remove a licença, todos os dados do usuário são mantidos por 30 dias. Você pode [acessar](get-access-to-and-back-up-a-former-user-s-data.md) os dados ou [restaurar](restore-user.md) a conta se o usuário retornar. Após 30 dias, todos os dados do usuário (exceto os documentos armazenados no SharePoint Online) são excluídos permanentemente do Microsoft 365 e não podem ser recuperados. 

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Selecione o nome do funcionário que você deseja bloquear e, em seguida, selecione a guia **licenças e aplicativos** .

4. Desmarque as caixas de seleção para as licenças que você deseja remover e, em seguida, selecione **salvar alterações**.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Selecione o funcionário que você deseja bloquear e, em seguida, ao lado de **licenças de produto**, selecione **Editar**.

3. Na página **licenças de produtos** , desative a (s) licença (s) que você deseja remover e, em seguida, selecione **salvar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Selecione o funcionário que você deseja bloquear e, em seguida, ao lado de **licenças de produto**, selecione **Editar**.

3. Na página **licenças de produtos** , desative a (s) licença (s) que você deseja remover e, em seguida, selecione **salvar**.

::: moniker-end


**Para reduzir o número de licenças que você está pagando** até contratar outra pessoa, faça o seguinte: 

::: moniker range="o365-worldwide"



1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.


::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Assinaturas</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Assinaturas</a>.

::: moniker-end
    
2. Selecione **Adicionar/remover licenças** para excluir a licença para não pagar por ela até contratar outra pessoa.

Ao [Adicionar](add-users.md) outra pessoa à sua empresa, você será solicitado a comprar uma licença ao mesmo tempo, com apenas uma etapa!
    
Para obter mais informações sobre o gerenciamento de licenças de usuário para o Microsoft 365 for Business, consulte [assign licenses to Users in microsoft 365 for Business](../manage/assign-licenses-to-users.md)e [Remove licenses from Users in Microsoft 365 for Business](../manage/remove-licenses-from-users.md).
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Como a conta de funcionário excluída afeta o Skype for Business
<a name="bkmk_remove"> </a>

When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.
  
If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue. 
  
## <a name="delete-a-former-employees-user-account"></a>Excluir a conta de usuário de um ex-funcionário
<a name="bkmk_delete"> </a>

Depois de salvar e acessar todos os dados de usuário do ex-funcionário, você pode excluir a conta do ex-funcionário.
  
Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Selecione o nome do funcionário que você deseja excluir.

3. Sob o nome do usuário, selecione o símbolo de **exclusão do usuário**. Escolha as opções desejadas para este usuário e, em seguida, selecione **excluir usuário**.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Selecione o nome do funcionário que você deseja excluir.

3. Na parte superior da página, selecione **excluir usuário**. Escolha as opções desejadas para este usuário e, em seguida, selecione **excluir usuário**.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Selecione o nome do funcionário que você deseja excluir.

3. Na parte superior da página, selecione **excluir usuário**. Escolha as opções desejadas para este usuário e, em seguida, selecione **excluir usuário**.

::: moniker-end

When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.
  
### <a name="does-your-organization-use-active-directory"></a>Sua organização usa o Active Directory?

Se sua organização sincronizar as contas de usuário para a Microsoft 365 a partir de um ambiente local do Active Directory, você deverá excluir e restaurar essas contas de usuário no serviço local do Active Directory. Não é possível excluí-las ou restaurá-las no Office 365.
  
Para obter instruções, consulte este artigo: [excluir uma conta de usuário](https://go.microsoft.com/fwlink/?linkid=841808).
  
Se estiver usando o Azure Active Directory, confira o cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) do PowerShell. 
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>O que você precisa saber sobre o encerramento da sessão de email de um funcionário
<a name="bkmk_session"> </a>

Aqui estão as informações sobre como excluir um funcionário do email (Exchange).
  
|||
|:-----|:-----|
|**O que você pode fazer** <br/> |**Como fazer isso** <br/> |
|Encerrar uma sessão (como o Outlook na Web, Outlook, Exchange Active Sync, etc.) e forçar a abertura de uma nova sessão  <br/> |Redefina a senha  <br/> |
|Encerrar uma sessão e bloquear o acesso a sessões futuras (para todos os protocolos)  <br/> |Disable the account. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Encerrar a sessão de um protocolo específico (como ActiveSync)  <br/> |Disable the protocol. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
As operações acima podem ser realizadas em três locais:
  
|||
|:-----|:-----|
|**Se você encerrar a sessão aqui** <br/> |**Quanto tempo demora** <br/> |
|No centro de administração do Exchange ou usando o PowerShell  <br/> |O atraso esperado é de 30 minutos  <br/> |
|No centro de administração do Azure Active Directory  <br/> |O atraso esperado é de 60 minutos  <br/> |
|Em um ambiente local  <br/> |O atraso esperado é de três horas ou mais  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>Como obter a resposta mais rapidamente para o encerramento da conta

 **Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync. 
  
 **Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync. 
  
## <a name="related-articles"></a>Artigos relacionados

[Restaurar um usuário](restore-user.md)
  
