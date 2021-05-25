---
title: Alterar o nome de exibição e o endereço de email de um usuário
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
description: 'Saiba como um administrador global do Microsoft 365 pode alterar o endereço de email e o nome de exibição de um usuário quando seu nome altera. '
ms.openlocfilehash: 1aa3fd3b67333937e64aab825e64533ccb09eea9
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52634215"
---
# <a name="change-a-user-name-and-email-address"></a>Alterar o nome de exibição e o endereço de email de um usuário

Talvez seja necessário alterar o endereço de email e o nome de exibição de uma pessoa se, por exemplo, ela se casar e mudar de sobrenome.

## <a name="watch-change-a-users-name-or-email-address"></a>Assista: alterar o nome ou o endereço de email de um usuário

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SJuc] 

Se você achou esse vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](../../business-video/index.yml).

Você terá de ser um [administrador global ](about-admin-roles.md) para executar estas etapas. 

## <a name="change-a-users-email-address"></a>Alterar o endereço de email de um usuário.

::: moniker range="o365-worldwide"
 
1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
    
2. Selecione o nome do usuário e, em seguida, na guia **Conta** selecione **Gerenciar nome de usuário**.
    
3. Na primeira caixa, digite a primeira parte do novo endereço de email. Se você adicionou seu próprio domínio ao Microsoft 365, escolha o domínio para o novo alias de email usando a lista suspensa. 

4. Selecione **Salvar alterações**.

   
::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.  

2. Selecione o usuário. No painel de atalho, ao lado de **Nome de usuário/ E-mail**, selecione **Editar**.

3. Na primeira caixa, digite a primeira parte do novo endereço de email. Se você adicionou seu próprio domínio ao Microsoft 365, é possível escolher o domínio para o novo alias de email usando a lista suspensa.

4. Selecione **Salvar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>. 

2. Selecione o usuário. No painel de atalho, ao lado de **Nome de usuário/ E-mail**, selecione **Editar**.

3. Na primeira caixa, digite a primeira parte do novo endereço de email. Se você adicionou seu próprio domínio ao Microsoft 365, é possível escolher o domínio para o novo alias de email usando a lista suspensa.

4. Selecione **Salvar**.

::: moniker-end

> [!IMPORTANT]
> Se você receber uma mensagem de erro, confira [Resolver mensagens de erro](#resolve-error-messages).

## <a name="set-the-primary-email-address"></a>Definir o endereço de email principal

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
    
2. Selecione o nome do usuário e, em seguida, na guia **Conta** selecione **Gerenciar alias de email**.

3. Escolha **Definir como Principal** para o endereço de e-mail que quer configurar como o principal para aquela pessoa. 
    
   > [!IMPORTANT]
   > Você não verá essa opção para Definir como Principal se tiver comprado o Microsoft 365 da GoDaddy ou outro serviço de Parceiro que forneça um console de gerenciamento. Em vez disso, entre no console de gerenciamento GoDaddy / parceiro para definir o alias principal. 
   >  
   > Além disso, você só verá essa opção se for um administrador global. Se não vir a opção, você não possui as permissões necessárias para alterar o nome e endereço de email principal do usuário.
  
4. Você verá um grande alerta amarelo informando que está prestes a alterar as informações de acesso.  Selecione **Salvar**, **Feche**.
    
5. Forneça à pessoa a seguinte informação:
 
   - Essa alteração pode demorar um pouco.
  
   - O novo nome de usuário. Será necessário para entrar no Microsoft 365.
    
   - Se eles estiverem usando o Skype for Business Online, será necessário reagendar todas as reuniões do Skype for Business Online que eles organizaram e pedir aos contatos externos que atualizem as informações de contato.

   - Se eles estiverem usando o OneDrive, a URL deste local foi alterada. Se eles tiverem blocos de anotações do OneNote no OneDrive, talvez precisem fechá-los e reabri-los no OneNote. Se eles tiverem arquivos compartilhados do OneDrive, os links para os arquivos poderão não funcionar, e o usuário poderá compartilhá-los novamente.    
  
   - Se a senha também tiver sido alterada, o utilizador precisará digitar a nova senha no dispositivo móvel ou eles não sincronizarão.
  
::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.  

2. Selecione o usuário. No painel de atalho, ao lado de **Nome de usuário/ E-mail**, selecione **Editar**.

3. Escolha **Definir como Principal** para o endereço de e-mail que quer configurar como o principal para aquela pessoa. 
    
   > [!IMPORTANT]
   > Você não verá essa opção para Definir como Principal se tiver comprado o Microsoft 365 da GoDaddy ou outro serviço de Parceiro que forneça um console de gerenciamento. Em vez disso, entre no console de gerenciamento GoDaddy / parceiro para definir o alias principal. 
   > 
   > Além disso, você só verá essa opção se for um administrador global. Se não vir a opção, você não possui as permissões necessárias para alterar o nome e endereço de email principal do usuário.
  
4. Você verá um grande alerta amarelo informando que está prestes a alterar as informações de acesso.  Selecione **Salvar**, **Feche**.
    
5. Repasse a seguinte informação à pessoa:
 
   - Essa alteração pode demorar um pouco para entrar em vigor.
  
   - Informe o novo nome de usuário. Ele será necessário para entrar no Microsoft 365.
    
   - Se ele estiver usando o Skype for Business Online, informe que ela deverá reagendar todas as reuniões do Skype for Business Online que organizou e que será preciso pedir aos contatos externos que atualizem as antigas informações de contato.

   - Se eles estiverem usando o OneDrive, informe-os de que a URL deste local foi alterada. Se eles tiverem blocos de anotações do OneNote no OneDrive, talvez precisem fechá-los e reabri-los no OneNote. Se eles tiverem arquivos compartilhados do OneDrive, os links para os arquivos poderão não funcionar, e o usuário poderá compartilhá-los novamente.    
  
   - Se a senha dela também tiver sido alterada, informe que ela precisará digitar a nova senha no dispositivo móvel para fazer a sincronização.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>. 

2. Selecione o usuário. No painel de atalho, ao lado de **Nome de usuário/ E-mail**, selecione **Editar**.

3. Escolha **Definir como Principal** para o endereço de e-mail que quer configurar como o principal para aquela pessoa. 
    
   > [!IMPORTANT]
   > Você não verá essa opção para Definir como Principal se tiver comprado o Microsoft 365 da GoDaddy ou outro serviço de Parceiro que forneça um console de gerenciamento. Em vez disso, entre no console de gerenciamento GoDaddy / parceiro para definir o alias principal. 
   >  
   > Além disso, você só verá essa opção se for um administrador global. Se não vir a opção, você não possui as permissões necessárias para alterar o nome e endereço de email principal do usuário.
  
4. Você verá um grande alerta amarelo informando que está prestes a alterar as informações de acesso.  Selecione **Salvar**, **Feche**.
    
5. Repasse a seguinte informação à pessoa:
 
   - Essa alteração pode demorar um pouco para entrar em vigor.
  
   - Informe o novo nome de usuário. Ele será necessário para entrar no Microsoft 365.
    
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

Pode levar até 24 horas para que essa alteração entre em vigor em todos os serviços. Depois que isso acontecer, a pessoa deverá entrar no Outlook, no Skype for Business e no SharePoint com o novo nome de usuário.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.  

2. Selecione o usuário. No painel de atalho, ao lado de **Informações de contato**, selecione **Editar**.

3. Na caixa **Nome de exibição**, digite um novo nome para a pessoa e, em seguida, selecione **Salvar**.

   Se você receber a mensagem de erro "**Infelizmente o usuário não pôde ser editado, examine as informações do usuário e tente novamente**. Confira [Resolver mensagens de erro](#resolve-error-messages).

Pode levar até 24 horas para que essa alteração entre em vigor em todos os serviços. Depois que isso acontecer, a pessoa deverá entrar no Outlook, no Skype for Business e no SharePoint com o novo nome de usuário. Por isso, avise sobre essa alteração.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>. 

2. Selecione o usuário. No painel de atalho, ao lado de **Informações de contato**, selecione **Editar**.

3. Na caixa **Nome de exibição**, digite um novo nome para a pessoa e, em seguida, selecione **Salvar**.

   Se você receber a mensagem de erro "**Infelizmente o usuário não pôde ser editado, examine as informações do usuário e tente novamente**. Confira [Resolver mensagens de erro](#resolve-error-messages).

Pode levar até 24 horas para que essa alteração entre em vigor em todos os serviços. Depois que isso acontecer, a pessoa deverá entrar no Outlook, no Skype for Business e no SharePoint com o novo nome de usuário. Por isso, avise sobre essa alteração.

::: moniker-end

## <a name="resolve-error-messages"></a>Resolver mensagens de erro

### <a name="a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"Não é possível localizar um parâmetro que coincida com o nome de parâmetro 'EmailAddresses'"

Se você receber a mensagem de erro " **Não foi encontrado um parâmetro que corresponda ao nome do parâmetro 'EmailAddresses**", significa que está demorando um pouco mais para concluir a configuração do seu locatário ou do seu domínio personalizado, caso você tenha adicionado um recentemente. O processo de configuração pode levar até 4 horas para ser concluído. Espere um pouco para que o processo de configuração tenha tempo de terminar e tente novamente. Se o problema persistir, ligue para o [suporte](../../business-video/get-help-support.md) e peça para fazer uma sincronização completa para você.
  
### <a name="were-sorry-the-user-couldnt-be-edited-review-the-user-information-and-try-again"></a>"O usuário não pôde ser editado. Revise as informações do usuário e tente novamente"

Se você receber a mensagem "**Não foi possível editar o usuário. Examine as informações de usuário e tente novamente**." Isso significa que você não é um administrador global e não tem as permissões necessárias para alterar o nome de usuário. Localize o administrador global em sua empresa e peça para ele fazer a alteração.


## <a name="what-to-do-with-old-email-addresses"></a>O que fazer com endereços de e-mail antigos

O antigo endereço de email principal de uma pessoa é mantido como um endereço de email adicional. **É altamente recomendável que você não remova o endereço de email antigo.**
  
É provável que algumas pessoas continuem a enviar emails para o antigo endereço de email da pessoa, e excluí-lo pode resultar em uma notificação de falha na entrega. A Microsoft os direcionará automaticamente para o novo endereço. Além disso, não reutilize antigos endereços de email SMTP e aplique-os a novas contas. Isso também pode causar notificações de falha na entrega ou a entrega em uma caixa de correio indesejada.
   
## <a name="what-if-the-persons-offline-address-book-wont-sync-with-the-global-address-list"></a>O que acontece se o catálogo de endereços offline de uma pessoa não estiver sincronizando com a Lista de Endereços Global?

Se eles estiverem usando o Exchange Online ou se a conta estiver vinculada ao ambiente Exchange local da sua organização, você poderá ver este erro quando tentar alterar um nome de usuário e endereço de email: "Este usuário está sincronizado com o seu Active Directory local. Alguns detalhes somente podem ser editados por meio do seu Active Directory local".
  
Isso se deve ao MOERA (Endereço de Roteamento de Email do Microsoft Online). O MOERA é construído por meio do atributo  _userPrincipalName_ da pessoa no Active Directory e é atribuído automaticamente à conta na nuvem durante a sincronização inicial. Depois de criado, não pode ser modificado ou removido no Microsoft 365. Posteriormente, é possível alterar o nome de usuário no Active Directory, mas isso não modificará o MOERA, e você poderá encontrar problemas com a exibição do novo nome na Lista de Endereços Global. 
  
Para corrigir isso, faça logon no [Módulo Azure Active Directory para PowerShell]( https://go.microsoft.com/fwlink/?LinkId=823193) com suas credenciais de administrador do Microsoft 365. e use a seguinte sintaxe: 
  
```powershell
Set-MsolUserPrincipalName -UserPrincipalName anne.wallace@contoso.onmicrosoft.com -NewUserPrincipalName anne.jones@contoso.com
```

> [!TIP]
> Isso modifica o atributo **userPrincipalName** da pessoa e não tem influência no Endereço de roteamento de e-mail online da Microsoft (MOERA) dela. Contudo, é uma boa prática que o UPN de logon corresponda ao endereço SMTP principal. 
  
Para saber como alterar um nome de usuário no Active Directory no Windows Server 2003 e em versões anteriores, confira [Alterar um nome de conta de usuário](/previous-versions/windows/it-pro/windows-server-2003/cc772952(v=ws.10))
  
## <a name="related-content"></a>Conteúdo relacionado

[Administradores: redefinir uma senha para um ou mais usuários](reset-passwords.md) (artigo)\
[Adicionar outro endereço de email a um usuário](../email/add-another-email-alias-for-a-user.md) (artigo)\
[Criar uma caixa de correio compartilhada](../email/create-a-shared-mailbox.md) (artigo)