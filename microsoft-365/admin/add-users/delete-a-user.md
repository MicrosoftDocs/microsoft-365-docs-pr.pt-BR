---
title: Excluir um usuário da sua organização
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Saiba como excluir uma conta de usuário. Decida o que fazer com o email do usuário, o conteúdo do OneDrive e se deseja manter a licença do produto ou parar de pagar por ela.
ms.openlocfilehash: 1d529627841c648684c8a9fe217a761b29749150
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43617243"
---
# <a name="delete-a-user-from-your-organization"></a>Excluir um usuário da sua organização
  
||
|:-----|
|**Procurando como excluir sua *própria* conta de usuário do Microsoft 365 que você usa no trabalho ou na escola? Entre em contato com o suporte técnico em seu trabalho ou universidade para executar estas etapas.**|
   
## <a name="what-you-need-to-know-about-deleting-users"></a>O que você precisa saber sobre a exclusão de usuários

- Somente as pessoas com permissões de gerenciamento de usuário ou [administrador global do Microsoft 365](about-admin-roles.md) para a empresa ou escola podem excluir contas de usuário. 
    
- Você tem até 30 dias para [restaurar](restore-user.md) a conta, antes que os dados do usuário sejam excluídos permanentemente. 
    
- Se você quiser manter os dados do usuário do OneDrive, mova-os para um local diferente. Você ainda pode fazer isso até 30 dias após a exclusão da conta. Veja [Obter acesso e realizar backup dos dados de um usuário anterior](get-access-to-and-back-up-a-former-user-s-data.md). Não é necessário mover os arquivos do SharePoint; você ainda terá acesso a eles.
    
- Se você deseja manter o email do usuário, **ANTES** de excluir a conta, mova o email para outro local. Se você excluiu a conta há menos de 30 dias, restaure-a, mova os dados de email e exclua-a. Confira [Obter acesso e realizar backup dos dados de um usuário anterior](get-access-to-and-back-up-a-former-user-s-data.md).
    
- Se você tiver uma assinatura corporativa como o Office 365 Enterprise E3, poderá preservar os dados da caixa de correio de uma conta de usuário excluída *transformando*-o em uma caixa de correio inativa. Saiba mais em [Gerenciar as caixas de correio inativas no Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Administração Global: excluir um usuário, parar de pagar por sua licença e escolher o que fazer com seus emails e conteúdo do OneDrive

Se você for um administrador global, quando excluir um usuário, também poderá conceder a outro usuário acesso ao seu email e escolher o que fazer com o conteúdo do OneDrive. 

  
### <a name="things-to-consider"></a>Coisas a considerar...

Antes de começar, pense no que você deseja fazer com o conteúdo do usuário e do OneDrive, e se você deseja manter a licença ou parar de pagar por ela.
  
|||
|:-----|:-----|
|Licenças de produto  <br/> |Você pode remover a licença do usuário e removê-la das assinaturas para parar de pagar pela licença. Se você selecionar essa opção, a licença será removida automaticamente de suas assinaturas.  <br/><br/> **Você não pode remover a licença** se a comprou por meio de um parceiro ou de um licenciamento por volume. Se você estiver pagando um plano anual ou se estiver no meio de um ciclo de cobrança, não será possível remover a licença da sua assinatura até que o compromisso seja concluído.  <br/> |
|Conteúdo do OneDrive  <br/> |Se o usuário salvou seus arquivos no OneDrive, você pode dar a outro usuário acesso a esses arquivos.  <br/><br/> Você precisará mover os arquivos que deseja manter dentro do período de retenção definido para arquivos do OneDrive. **Por padrão, o período de retenção é de 30 dias.** Se você não mover os arquivos dentro do período de retenção após excluir o usuário, o conteúdo do OneDrive será excluído permanentemente. Para aumentar o número de dias que você retém arquivos do OneDrive para contas excluídas, consulte [set the onedrive Retention for Deleted Users](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).  <br/><br/> **Importante!** Se o usuário excluído utilizou um computador pessoal para baixar arquivos do SharePoint e do OneDrive, não há como apagar os arquivos armazenados no computador. Eles continuarão a ter acesso a todos os arquivos que foram sincronizados a partir do OneDrive.           |
|Email  <br/> | Conceder a outro usuário acesso ao email do usuário excluído converterá a caixa de correio do usuário excluído em uma caixa de correio compartilhada. O novo proprietário da caixa de correio pode acessar a caixa de correio e monitorar novos emails. Você também terá as seguintes opções:  <br/>  <br/>Alterar o nome para exibição-recomendamos alterar o nome de exibição para que seja fácil identificar a caixa de correio compartilhada na lista de usuários ativos.  <br/>  Ativar respostas automáticas – já escrevemos uma resposta de educador automática para você. Você pode enviar respostas automáticas diferentes para pessoas dentro da sua organização e pessoas de fora da organização.  <br/> <br/> Limpar aliases-os aliases são endereços de email adicionais para os usuários. Algumas organizações não as usam, portanto, se você não tiver nenhum, não será necessário fazer nada mais aqui. Se o usuário tiver aliases, recomendamos removê-los para que você possa reutilizar esses endereços de email. Caso contrário, você não poderá usar novamente esses endereços de email até que o período de retenção de caixas de correio excluídas tenha passado. Por padrão, uma caixa de correio excluída é recuperável por 30 dias. Para obter mais informações, consulte [excluir ou restaurar caixas de correio do usuário no Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox). <br/> |
|Active Directory  <br/> |Se a sua empresa usa o **Active Directory** sincronizado com o Azure AD, é necessário excluir a conta de usuário do Active Directory. Não é possível fazê-lo no Office 365. Para obter instruções, consulte [excluir uma conta de usuário](https://go.microsoft.com/fwlink/p/?linkid=841808).  <br/> |
   
### <a name="get-started"></a>Introdução

::: moniker range="o365-worldwide"

> [!NOTE]
> Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.

::: moniker-end

Como a experiência orientada percorre as etapas para excluir um usuário, veja aqui como começar.

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

::: moniker-end

2. Selecione o usuário que você deseja excluir e, em seguida, selecione **excluir usuário**.

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Administração de gerenciamento de usuários: excluir um ou mais usuários do Office 365


> [!IMPORTANT]
> Não exclua a conta de um usuário se [a tiver convertido em uma caixa de correio compartilhada](../email/convert-user-mailbox-to-shared-mailbox.md) ou se você tiver configurado o encaminhamento de emails na conta. Essas funções ainda precisam da conta. Uma caixa de correio compartilhada não requer uma licença. Se você converteu a conta em uma caixa de correio compartilhada, pode [parar de pagar pela licença](#stop-paying-for-the-license). Se você configurou o encaminhamento de emails na conta, não é possível remover a licença. Isso interromperá o encaminhamento de emails e a desativação da caixa de correio.
  
::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.  

2. Selecione os nomes dos usuários que você deseja excluir, selecione **mais opções** (**...**) e, em seguida, escolha **excluir usuário**.

   Embora você tenha excluído a conta do usuário, **ainda está pagando pela licença**. Consulte o procedimento a seguir para interromper o pagamento da licença.  Ou você pode atribuir a licença a outro usuário. Ele não será atribuído a alguém automaticamente.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Selecione os nomes dos usuários que você deseja excluir e, no painel **ações em massa** , escolha **excluir usuários**.

   Embora você tenha excluído a conta do usuário, **ainda está pagando pela licença**. Consulte o procedimento a seguir para interromper o pagamento da licença.  Ou você pode atribuir a licença a outro usuário. Ele não será atribuído a alguém automaticamente.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Selecione os nomes dos usuários que você deseja excluir e, no painel **ações em massa** , escolha **excluir usuários**.

   Embora você tenha excluído a conta do usuário, **ainda está pagando pela licença**. Consulte o procedimento a seguir para interromper o pagamento da licença.  Ou você pode atribuir a licença a outro usuário. Ele não será atribuído a alguém automaticamente.

::: moniker-end

### <a name="stop-paying-for-the-license"></a>Parar de pagar pela licença

Reduzir o número de licenças é uma etapa separada que só pode ser realizada pelo administrador global ou administrador de cobrança. 
  
::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Produtos e serviços</a>. Se você não vir essa opção, você não é um administrador global ou de cobrança e não pode executar esta etapa.

2. Selecione a assinatura (se você tiver mais de uma) e, em seguida, selecione **Adicionar/remover licenças** para excluir a licença para não pagar por ela até contratar outra pessoa.  

   Mais tarde, quando você passar pelas etapas para adicionar outra pessoa à sua empresa, você será solicitado a comprar uma licença ao mesmo tempo, com apenas uma etapa!

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Assinaturas</a>. Se você não vir essa opção, você não é um administrador global ou de cobrança e não pode executar esta etapa.

2. Selecione a assinatura (se você tiver mais de uma) e, em seguida, selecione **Adicionar/remover licenças** para excluir a licença para não pagar por ela até contratar outra pessoa.  

   Mais tarde, quando você passar pelas etapas para adicionar outra pessoa à sua empresa, você será solicitado a comprar uma licença ao mesmo tempo, com apenas uma etapa!

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Assinaturas</a>. Se você não vir essa opção, você não é um administrador global ou de cobrança e não pode executar esta etapa.

2. Selecione a assinatura (se você tiver mais de uma) e, em seguida, selecione **Adicionar/remover licenças** para excluir a licença para não pagar por ela até contratar outra pessoa.  

   Mais tarde, quando você passar pelas etapas para adicionar outra pessoa à sua empresa, você será solicitado a comprar uma licença ao mesmo tempo, com apenas uma etapa!

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a>Excluir muitos usuários ao mesmo tempo

Consulte o cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) do PowerShell.

## <a name="fix-issues-with-deleting-a-user"></a>Corrigir problemas na exclusão de um usuário

Aqui estão os problemas mais comuns que as pessoas encontram ao excluir um usuário:
  
- **Você recebe uma mensagem de erro ao longo das linhas de "o usuário não pode ser excluído. Tente novamente mais tarde. "** Verifique se a conta do encaminhamento de emails foi configurada ou se foi convertida em uma caixa de correio compartilhada. Ambos causarão esse erro. Não exclua a conta se tiver encaminhamento de email ou se ele tiver sido convertido em uma caixa de correio compartilhada.

- **Você não tem as permissões adequadas para excluir um usuário**. Somente as pessoas que são administradores [globais ou administradores de gerenciamento de usuários do Microsoft 365](about-admin-roles.md) podem excluir usuários. Normalmente, esse é o suporte técnico disponível em sua escola ou empresa.

- **Você exclui o usuário, mas o nome dele continua aparecendo no catálogo de endereços global**. Isso acontece quando uma empresa está usando o Active Directory. Você precisa excluir a conta de usuário do Active Directory. Confira as instruções neste artigo do TechNet: [Excluir uma conta de usuário.](https://go.microsoft.com/fwlink/p/?linkid=841808)

||
|:-----|
|**Você deseja excluir o Microsoft 365 do seu computador? Vá para [cancelar sua assinatura](../../commerce/subscriptions/cancel-your-subscription.md).**|
   
## <a name="related-articles"></a>Artigos relacionados

[Restaurar um usuário](restore-user.md)
  
[Excluir permanentemente uma caixa de correio](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[Remover um ex-funcionário do Office 365](remove-former-employee.md)

[Adicionar um novo funcionário ao Office 365](add-new-employee.md)

[Excluir uma conta de usuário](https://go.microsoft.com/fwlink/p/?linkid=841808): Use estas instruções se a sua empresa usa o **Active Directory** que está sincronizando com o Azure AD. Não é possível fazê-lo no Office 365.