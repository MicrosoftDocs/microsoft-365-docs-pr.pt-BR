---
title: Alterar o nome de exibição e o endereço de email de um usuário
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb5ac074-e203-4e1f-9843-b9d1a3e03297
description: 'Saiba como um administrador global pode alterar o endereço de e-mail e o nome de exibição de um usuário. '
ms.openlocfilehash: 76a2124c7fc73e40650a18985a5aa10acf57737a
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780620"
---
# <a name="change-a-user-name-and-email-address"></a>Alterar o nome de exibição e o endereço de email de um usuário

Talvez seja necessário alterar o endereço de email e o nome de exibição de uma pessoa se, por exemplo, ela se casar e mudar de sobrenome.

Assista a um vídeo curto sobre como alterar o endereço de e-mail de um usuário. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SJuc] 

Se você achou esse vídeo útil, Confira as [ séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="change-a-users-email-address"></a>Alterar o endereço de email de um usuário.

Você terá de ser um [administrador global ](about-admin-roles.md) para executar estas etapas. 

::: moniker range="o365-worldwide"
 
1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
    
2. Selecione o nome do usuário e, em seguida, na guia **Conta** selecione **Gerenciar nome de usuário**.
    
3. Na primeira caixa, digite a primeira parte do novo endereço de email. Se você adicionou seu próprio domínio ao Office 365, será possível escolher o domínio para o novo alias de email usando a lista suspensa. 

4. Selecione **Salvar alterações**.

   
::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.  

2. Selecione o usuário. No painel de atalho, ao lado de **Nome de usuário/ E-mail**, selecione **Editar**.

3. Na primeira caixa, digite a primeira parte do novo endereço de email. Se você adicionou seu próprio domínio ao Office 365, será possível escolher o domínio para o novo alias de email usando a lista suspensa.

4. Selecione **Salvar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>. 

2. Selecione o usuário. No painel de atalho, ao lado de **Nome de usuário/ E-mail**, selecione **Editar**.

3. Na primeira caixa, digite a primeira parte do novo endereço de email. Se você adicionou seu próprio domínio ao Office 365, será possível escolher o domínio para o novo alias de email usando a lista suspensa.

4. Selecione **Salvar**.

::: moniker-end

**IMPORTANTE**: se você receber uma mensagem de erro, confira [Resolver mensagens de erro](#resolve-error-messages).

## <a name="set-the-primary-email-address"></a>Definir o endereço de email principal

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
    
2. Selecione o nome do usuário e, em seguida, na guia **Conta** selecione **Gerenciar alias de email**.

3. Escolha **Definir como Principal** para o endereço de e-mail que quer configurar como o principal para aquela pessoa. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Além disso, você só verá essa opção se for um administrador global. Se não vir a opção, você não possui as permissões necessárias para alterar o nome e endereço de email principal do usuário.
  
4. Você verá um grande alerta amarelo informando que está prestes a alterar as informações de acesso.  Selecione **Salvar**, **Feche**.
    
5. Repasse a seguinte informação à pessoa:
 
  - Essa alteração pode demorar um pouco para entrar em vigor.
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - Se ele estiver usando o Skype for Business Online, informe que ela deverá reagendar todas as reuniões do Skype for Business Online que organizou e que será preciso pedir aos contatos externos que atualizem as antigas informações de contato.

  - Se eles estiverem usando o OneDrive, informe-os de que a URL deste local foi alterada. Se eles tiverem blocos de anotações do OneNote no OneDrive, talvez precisem fechá-los e reabri-los no OneNote. Se eles tiverem arquivos compartilhados do OneDrive, os links para os arquivos poderão não funcionar, e o usuário poderá compartilhá-los novamente.    
  
  - Se a senha dela também tiver sido alterada, informe que ela precisará digitar a nova senha no dispositivo móvel para fazer a sincronização.
  
::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.  

2. Selecione o usuário. No painel de atalho, ao lado de **Nome de usuário/ E-mail**, selecione **Editar**.

3. Escolha **Definir como Principal** para o endereço de e-mail que quer configurar como o principal para aquela pessoa. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Além disso, você só verá essa opção se for um administrador global. Se não vir a opção, você não possui as permissões necessárias para alterar o nome e endereço de email principal do usuário.
  
4. Você verá um grande alerta amarelo informando que está prestes a alterar as informações de acesso.  Selecione **Salvar**, **Feche**.
    
5. Repasse a seguinte informação à pessoa:
 
  - Essa alteração pode demorar um pouco para entrar em vigor.
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - Se ele estiver usando o Skype for Business Online, informe que ela deverá reagendar todas as reuniões do Skype for Business Online que organizou e que será preciso pedir aos contatos externos que atualizem as antigas informações de contato.

  - Se eles estiverem usando o OneDrive, informe-os de que a URL deste local foi alterada. Se eles tiverem blocos de anotações do OneNote no OneDrive, talvez precisem fechá-los e reabri-los no OneNote. Se eles tiverem arquivos compartilhados do OneDrive, os links para os arquivos poderão não funcionar, e o usuário poderá compartilhá-los novamente.    
  
  - Se a senha dela também tiver sido alterada, informe que ela precisará digitar a nova senha no dispositivo móvel para fazer a sincronização.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>. 

2. Selecione o usuário. No painel de atalho, ao lado de **Nome de usuário/ E-mail**, selecione **Editar**.

3. Escolha **Definir como Principal** para o endereço de e-mail que quer configurar como o principal para aquela pessoa. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Além disso, você só verá essa opção se for um administrador global. Se não vir a opção, você não possui as permissões necessárias para alterar o nome e endereço de email principal do usuário.
  
4. Você verá um grande alerta amarelo informando que está prestes a alterar as informações de acesso.  Selecione **Salvar**, **Feche**.
    
5. Repasse a seguinte informação à pessoa:
 
  - Essa alteração pode demorar um pouco para entrar em vigor.
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - Se ele estiver usando o Skype for Business Online, informe que ela deverá reagendar todas as reuniões do Skype for Business Online que organizou e que será preciso pedir aos contatos externos que atualizem as antigas informações de contato.

  - Se eles estiverem usando o OneDrive, informe-os de que a URL deste local foi alterada. Se eles tiverem blocos de anotações do OneNote no OneDrive, talvez precisem fechá-los e reabri-los no OneNote. Se eles tiverem arquivos compartilhados do OneDrive, os links para os arquivos poderão não funcionar, e o usuário poderá compartilhá-los novamente.    
  
  - Se a senha dela também tiver sido alterada, informe que ela precisará digitar a nova senha no dispositivo móvel para fazer a sincronização.

::: moniker-end
  
## <a name="change-a-users-display-name"></a>Alterar nome de exibição de um usuário

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Selecione o nome do usuário e, em seguida, na guia **Conta** selecione **Gerenciar informações de contato**.

3. Na caixa **Nome de exibição**, digite um novo nome para a pessoa e, em seguida, selecione **Salvar**.

    Se você receber a mensagem de erro "**Infelizmente o usuário não pôde ser editado, examine as informações do usuário e tente novamente**. Confira [Resolver mensagens de erro](#resolve-error-messages).

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.  

2. Selecione o usuário. No painel de atalho, ao lado de **Informações de contato**, selecione **Editar**.

3. Na caixa **Nome de exibição**, digite um novo nome para a pessoa e, em seguida, selecione **Salvar**.

    Se você receber a mensagem de erro "**Infelizmente o usuário não pôde ser editado, examine as informações do usuário e tente novamente**. Confira [Resolver mensagens de erro](#resolve-error-messages).

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>. 

2. Selecione o usuário. No painel de atalho, ao lado de **Informações de contato**, selecione **Editar**.

3. Na caixa **Nome de exibição**, digite um novo nome para a pessoa e, em seguida, selecione **Salvar**.

    Se você receber a mensagem de erro "**Infelizmente o usuário não pôde ser editado, examine as informações do usuário e tente novamente**. Confira [Resolver mensagens de erro](#resolve-error-messages).

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

## <a name="resolve-error-messages"></a>Resolver mensagens de erro

### <a name="a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"Não é possível localizar um parâmetro que coincida com o nome de parâmetro 'EmailAddresses'"

If you get the error message " **A parameter cannot be found that matches parameter name 'EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one. The setup process can take up to 4 hours to complete. Wait a while so the set up process has time to finish, and then try again. If the problem persists, call Support and they will do a full sync for you.
  
### <a name="were-sorry-the-user-couldnt-be-edited-review-the-user-information-and-try-again"></a>"Não foi possível editar o usuário. Examine as informações de usuário e tente novamente"

Se você receber a mensagem "**Não foi possível editar o usuário. Examine as informações de usuário e tente novamente**." Isso significa que você não é um administrador global e não tem as permissões necessárias para alterar o nome de usuário. Localize o administrador global em sua empresa e peça para ele fazer a alteração.


## <a name="what-to-do-with-old-email-addresses"></a>O que fazer com endereços de e-mail antigos

A person's previous primary email address is retained as an additional email address. **We strongly recommend that you don't remove the old email address.**
  
Some people will likely continue to send email to the person's old email address and deleting it may result in NDR failures. Microsoft will automatically route it to the new one. Also, do not reuse old SMTP email addresses and apply them to new accounts. This can also cause NDR failures or delivery to an unintended mailbox.
   
## <a name="what-if-the-persons-offline-address-book-wont-sync-with-the-global-address-list"></a>O que acontece se o catálogo de endereços offline de uma pessoa não estiver sincronizando com a Lista de Endereços Global?

If they are using Exchange Online or if their account is linked with your organization's on-premises Exchange environment, you may see this error when you try to change a username and email address: "This user is synchronized with your local Active Directory. Some details can be edited only through your local Active Directory."
  
This is due to the Microsoft Online Email Routing Address (MOERA). The MOERA is constructed from the person's  _userPrincipalName_ attribute in Active Directory and is automatically assigned to the cloud account during the initial sync and once created, it cannot be modified or removed in Office 365. You can subsequently change the username in the Active Directory, but it will not change the MOERA and you may run into issues displaying the newly changed name in the Global Address List. 
  
Para corrigir isso, faça logon no [Módulo Azure Active Directory para PowerShell]( https://go.microsoft.com/fwlink/?LinkId=823193) com suas credenciais de administrador do Microsoft 365. e use a seguinte sintaxe: 
  
```powershell
Set-MsolUserPrincipalName -UserPrincipalName anne.wallace@contoso.onmicrosoft.com -NewUserPrincipalName anne.jones@contoso.com
```

> [!TIP]
> Isso modifica o atributo **userPrincipalName** da pessoa e não tem influência no Endereço de roteamento de e-mail online da Microsoft (MOERA) dela. Contudo, é uma boa prática que o UPN de logon corresponda ao endereço SMTP principal. 
  
Para saber como alterar um nome de usuário no Active Directory no Windows Server 2003 e em versões anteriores, confira [Alterar um nome de conta de usuário](https://go.microsoft.com/fwlink/?LinkId=809091)
  
## <a name="related-articles"></a>Artigos relacionados

[Administradores: Redefinir uma senha para um ou mais usuários](reset-passwords.md)
  
[Adicionar outro endereço de e-mail para um usuário](../email/add-another-email-alias-for-a-user.md)
