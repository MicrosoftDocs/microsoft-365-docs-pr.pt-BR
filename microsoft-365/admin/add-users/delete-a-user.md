---
title: Excluir um usuário da sua organização
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
- AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Saiba como excluir uma conta de usuário. Decida o que fazer com o email do usuário e o conteúdo do OneDrive. E decida se deve manter a licença do produto ou parar de pagar por ela.
ms.openlocfilehash: 45cf8b9173a3a4260fe664b809f47ab14b57d9fe
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551371"
---
# <a name="delete-a-user-from-your-organization"></a>Excluir um usuário da sua organização
  
**Procurando como excluir sua *própria* conta de usuário do Microsoft 365 que você usa no trabalho ou na escola? Entre em contato com o suporte técnico do seu trabalho ou universidade para seguir estas etapas para você.**

## <a name="what-you-need-to-know-about-deleting-users"></a>O que você precisa saber sobre a exclusão de usuários

- Somente as pessoas que têm permissões de administrador global do [Microsoft 365](about-admin-roles.md) ou gerenciamento de usuários para a empresa ou escola podem excluir contas de usuário.
- Você tem até 30 dias para [restaurar](restore-user.md) a conta, antes que os dados do usuário sejam excluídos permanentemente.
- Se você quiser manter os dados do usuário do OneDrive, mova-os para um local diferente. Você pode até mover os dados até 30 dias após a exclusão da conta. Veja [Obter acesso e realizar backup dos dados de um usuário anterior](get-access-to-and-back-up-a-former-user-s-data.md). Não é necessário mover os arquivos do SharePoint; você ainda terá acesso a eles.
- Se você deseja manter o email do usuário, **ANTES** de excluir a conta, mova o email para outro local. Se você excluiu a conta há menos de 30 dias, restaure-a, mova os dados de email e exclua-a. Confira [Obter acesso e realizar backup dos dados de um usuário anterior](get-access-to-and-back-up-a-former-user-s-data.md).
- Se você tiver uma assinatura Enterprise como o Office 365 Enterprise E3, poderá preservar os dados da caixa de correio de uma conta de usuário excluída, transformando-a em uma caixa de correio *inativa.* Saiba mais em [Gerenciar as caixas de correio inativas no Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Administrador global: exclua um usuário, pare de pagar por sua licença e escolha o que fazer com o email e o conteúdo do OneDrive

Se você for um administrador global, ao excluir um usuário, também poderá dar a outro usuário acesso ao email dele e escolher o que fazer com o conteúdo do OneDrive.

### <a name="things-to-consider"></a>Coisas a considerar...

Antes de começar, pense no que você deseja fazer com o email do usuário e o conteúdo do OneDrive e se deseja manter a licença ou parar de pagar por ela.
  
|Item | Descrição |
|:-----|:-----|
|Licenças de produto  <br/> |Você pode remover a licença do usuário e removê-la de suas assinaturas para deixar de pagar por essa licença. Se você selecionar essa opção, a licença será removida automaticamente de suas assinaturas.  <br/><br/> **Você não pode remover a licença se a** comprou por meio de um parceiro ou licenciamento por volume. Se você estiver pagando por um plano anual ou se estiver no meio de um ciclo de cobrança, não poderá remover a licença da sua assinatura até que o compromisso seja concluído.  <br/> |
|Conteúdo do OneDrive  <br/> |Se o usuário salvou seus arquivos no OneDrive, você pode dar a outro usuário acesso a esses arquivos.  <br/><br/> Você precisará mover os arquivos que deseja manter dentro do período de retenção definido para arquivos do OneDrive. **Por padrão, o período de retenção é de 30 dias.** Se você não mover os arquivos dentro do período de retenção após excluir o usuário, o conteúdo do OneDrive será excluído permanentemente. Para aumentar o número de dias que você mantém os arquivos do OneDrive para contas excluídas, confira Definir a retenção do [OneDrive para usuários excluídos.](https://docs.microsoft.com/onedrive/set-retention)  <br/><br/> **Importante!** Se o usuário excluído usou um computador pessoal para baixar arquivos do SharePoint e do OneDrive, não é possível apagar os arquivos armazenados no computador. Eles continuarão a ter acesso a todos os arquivos que foram sincronizados do OneDrive.           |
|Email  <br/> | Dar a outro usuário acesso ao email do usuário excluído converterá a caixa de correio do usuário excluído em uma caixa de correio compartilhada. O novo proprietário da caixa de correio pode acessar a caixa de correio e monitorar novos emails. Você também terá as seguintes opções:  <br/>  <br/>Alterar o nome de exibição - Recomendamos alterar o nome de exibição para que seja fácil identificar a caixa de correio compartilhada na **lista de usuários** ativos.  <br/>  Ativar respostas automáticas - Já escrevemos uma resposta automática para você. Você pode enviar respostas automáticas diferentes para pessoas de dentro da sua organização e pessoas de fora da sua organização.  <br/> <br/> Limpar aliases - Aliases são endereços de email adicionais para os usuários. Algumas organizações não as usam, portanto, se você não tiver nenhuma, não precisará fazer nada mais aqui. Se o usuário tiver aliases, recomendamos removê-los para que você possa reutilizar esses endereços de email. Caso contrário, você não poderá reutilizar esses endereços de email até que o período de retenção das caixas de correio excluídas tenha passado. Por padrão, uma caixa de correio excluída pode ser recuperada por 30 dias. Para obter mais informações, consulte [Excluir ou restaurar caixas de correio do usuário no Exchange Online.](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox) <br/> |
|Active Directory  <br/> |Se a sua empresa usa o **Active Directory** sincronizado com o Azure AD, é necessário excluir a conta de usuário do Active Directory. Não é possível fazê-lo no Office 365. Para obter instruções, [consulte Excluir uma conta de usuário.](https://go.microsoft.com/fwlink/p/?linkid=841808)  <br/> |

### <a name="get-started"></a>Introdução

Como a experiência guiada percorre as etapas para excluir um usuário, veja como começar.

::: moniker range="o365-worldwide"
1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
::: moniker-end

::: moniker range="o365-germany"
1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.
::: moniker-end

::: moniker range="o365-21vianet"
1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.
::: moniker-end

2. Selecione o usuário que você deseja excluir e, em seguida, selecione **Excluir usuário**.

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Administrador de gerenciamento de usuários: excluir um ou mais usuários do Office 365

> [!IMPORTANT]
> Não exclua a conta de um [](../email/convert-user-mailbox-to-shared-mailbox.md) usuário se você a tiver convertido em uma caixa de correio compartilhada ou se tiver definido o encaminhamento de email na conta. Essas funções ainda precisam da conta. Uma caixa de correio compartilhada não exige uma licença. Se você tiver convertido a conta em uma caixa de correio compartilhada, poderá parar [de pagar pela licença.](#stop-paying-for-the-license) Se você tiver definido o encaminhamento de email na conta, não poderá remover a licença. Isso interromperá o encaminhamento de emails e desativará a caixa de correio.
  
::: moniker range="o365-worldwide"

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.  

2. Selecione os nomes dos usuários que você deseja excluir, selecione **Mais** opções (**...**) e escolha  **Excluir usuário**.

   Embora você tenha excluído a conta do usuário, **ainda está pagando pela licença.** Consulte o próximo procedimento para parar de pagar pela licença.  Ou você pode atribuir a licença a outro usuário. Ele não será atribuído a alguém automaticamente.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Selecione os nomes dos usuários que você deseja  excluir e, no painel de ações em massa, escolha **Excluir usuários**.

   Embora você tenha excluído a conta do usuário, **ainda está pagando pela licença.** Consulte o próximo procedimento para parar de pagar pela licença.  Ou você pode atribuir a licença a outro usuário. Ele não será atribuído a alguém automaticamente.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Selecione os nomes dos usuários que você deseja  excluir e, no painel de ações em massa, escolha **Excluir usuários**.

   Embora você tenha excluído a conta do usuário, **ainda está pagando pela licença.** Consulte o próximo procedimento para parar de pagar pela licença.  Ou você pode atribuir a licença a outro usuário. Ele não será atribuído a alguém automaticamente.

::: moniker-end

### <a name="stop-paying-for-the-license"></a>Parar de pagar pela licença

Reduzir o número de licenças é uma etapa separada que só pode ser executada pelo administrador global ou pelo administrador de cobrança.
  
::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>. Se você não vir essa opção, não será um administrador global ou administrador de cobrança e não poderá fazer esta etapa.

2. Na guia **Produtos,** selecione a assinatura para a que você deseja remover licenças.

3. Na página de detalhes da assinatura, selecione **Remover licenças.**

4. No painel **Remover licenças,** em Nova **quantidade,** na caixa Total de **licenças,** insira o número total de licenças que você deseja para essa assinatura. Por exemplo, se você tiver 100 licenças e quiser remover cinco delas, digite 95.

5. Selecione **Salvar**.

Mais tarde, ao passar pelas etapas para adicionar outra pessoa à sua empresa, você será solicitado a comprar uma licença ao mesmo tempo, com apenas uma etapa!

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Assinaturas</a>. Se você não vir essa opção, não será um administrador global ou administrador de cobrança e não poderá fazer esta etapa.

2. Selecione a assinatura (se você tiver mais de uma) e, em seguida, selecione **Adicionar/Remover licenças** para excluir a licença para não pagar por ela até contratar outra pessoa.  

   Mais tarde, ao passar pelas etapas para adicionar outra pessoa à sua empresa, você será solicitado a comprar uma licença ao mesmo tempo, com apenas uma etapa!

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Assinaturas</a>. Se você não vir essa opção, não será um administrador global ou administrador de cobrança e não poderá fazer esta etapa.

2. Selecione a assinatura (se você tiver mais de uma) e, em seguida, selecione **Adicionar/Remover licenças** para excluir a licença para não pagar por ela até contratar outra pessoa.  

   Mais tarde, ao passar pelas etapas para adicionar outra pessoa à sua empresa, você será solicitado a comprar uma licença ao mesmo tempo, com apenas uma etapa!

::: moniker-end

## <a name="delete-many-users-at-the-same-time"></a>Excluir muitos usuários ao mesmo tempo

Consulte o cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell.

## <a name="fix-issues-with-deleting-a-user"></a>Corrigir problemas na exclusão de um usuário

Aqui estão os problemas mais comuns que as pessoas encontram ao excluir um usuário:
  
- **Você pode receber uma mensagem de erro nas linhas "O usuário não pode ser excluído. Tente novamente mais tarde."** Verifique se a conta tem o encaminhamento de email definido ou se ela foi convertida em uma caixa de correio compartilhada. Ambos causarão esse erro. Não exclua a conta se ela tiver encaminhamento de email ou se tiver sido convertida em uma caixa de correio compartilhada.

- **Você não tem as permissões adequadas para excluir um usuário**. Somente as pessoas que são [administradores globais do Microsoft 365 ou administradores de gerenciamento](about-admin-roles.md) de usuários podem excluir usuários. Normalmente, esse é o suporte técnico disponível em sua escola ou empresa.

- **Você exclui o usuário, mas o nome dele continua aparecendo no catálogo de endereços global**. Isso acontece quando uma empresa está usando o Active Directory. Você deve excluir a conta de usuários do Active Directory. Para obter instruções, consulte [Excluir uma conta de usuário.](https://go.microsoft.com/fwlink/p/?linkid=841808)

**Você deseja excluir o Microsoft 365 do seu computador? Vá para [Cancelar sua assinatura.](../../commerce/subscriptions/cancel-your-subscription.md)**

## <a name="related-articles"></a>Artigos relacionados

[Restaurar um usuário](restore-user.md)
  
[Excluir permanentemente uma caixa de correio](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[Remover um ex-funcionário do Office 365](remove-former-employee.md)

[Adicionar um novo funcionário ao Office 365](add-new-employee.md)

[Excluir uma conta de](https://go.microsoft.com/fwlink/p/?linkid=841808)usuário: use estas instruções se sua empresa usa **o Active Directory** que está sincronizando com o Azure AD. Não é possível fazê-lo no Office 365.