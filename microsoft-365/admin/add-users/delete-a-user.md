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
description: Saiba como excluir uma conta de usuário e o que fazer com o email do usuário e OneDrive conteúdo e se deve manter a licença do produto.
ms.openlocfilehash: 43a57a69ce0d810af2b029f49c15d32d75a4dc33
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683134"
---
# <a name="delete-a-user-from-your-organization"></a>Excluir um usuário da sua organização
  
**Procurando como excluir sua *própria* conta de Microsoft 365 que você usa no trabalho ou na escola? Entre em contato com o suporte técnico em seu trabalho ou universidade para fazer estas etapas para você.**

## <a name="before-you-begin"></a>Antes de começar

- Somente as pessoas que [têm Microsoft 365 administrador global](about-admin-roles.md) ou permissões de gerenciamento de usuário para a empresa ou escola podem excluir contas de usuário.
- Você tem até 30 dias para [restaurar](restore-user.md) a conta, antes que os dados do usuário sejam excluídos permanentemente.
- Se você quiser manter os dados do usuário do OneDrive, mova-os para um local diferente. Você pode até mesmo mover os dados até 30 dias após a exclusão da conta. Veja [Obter acesso e realizar backup dos dados de um usuário anterior](get-access-to-and-back-up-a-former-user-s-data.md). Não é necessário mover os arquivos do SharePoint; você ainda terá acesso a eles.
- Se você deseja manter o email do usuário, **ANTES** de excluir a conta, mova o email para outro local. Se você excluiu a conta há menos de 30 dias, restaure-a, mova os dados de email e exclua-a. Confira [Obter acesso e realizar backup dos dados de um usuário anterior](get-access-to-and-back-up-a-former-user-s-data.md).
- Se você tiver uma assinatura Enterprise como Office 365 Enterprise E3, poderá preservar os dados de caixa de correio de uma conta de usuário excluída, transformando-a em uma caixa de correio *inativa.* Saiba mais em [Gerenciar as caixas de correio inativas no Exchange Online](../../compliance/inactive-mailboxes-in-office-365.md).

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Administrador global: exclua um usuário, pare de pagar por sua licença e escolha o que fazer com seus emails e OneDrive conteúdo

Se você for um administrador global, ao excluir um usuário, também poderá dar a outro usuário acesso ao email e escolher o que fazer com o conteúdo OneDrive usuário.

### <a name="things-to-consider"></a>Itens a considerar

Antes de começar, pense no que você deseja fazer com o email e o conteúdo OneDrive do usuário e se deseja manter a licença ou parar de pagar por ela.
  
|Item | Descrição |
|:-----|:-----|
|Licenças de produto  <br/> |Você pode remover a licença do usuário e removê-la de suas assinaturas para parar de pagar por essa licença. Se você selecionar essa opção, a licença será removida automaticamente de suas assinaturas.  <br/><br/> **Não é possível remover a licença se** a comprou por meio de um Licenciamento de Parceiro ou volume. Se você estiver pagando por um plano anual ou se estiver no meio de um ciclo de cobrança, não poderá remover a licença de sua assinatura até que seu compromisso seja concluído.  <br/> |
|OneDrive conteúdo  <br/> |Se o usuário salvou seus arquivos para OneDrive, você pode dar a outro usuário acesso a esses arquivos.  <br/><br/> Você precisará mover os arquivos que deseja manter dentro do período de retenção definido para OneDrive arquivos. **Por padrão, o período de retenção é de 30 dias.** Se você não mover os arquivos dentro do período de retenção após excluir o usuário, o OneDrive conteúdo será excluído permanentemente. Para aumentar o número de dias que você mantém OneDrive arquivos para contas excluídas, consulte Definir a retenção OneDrive [para usuários excluídos.](/onedrive/set-retention)  <br/><br/> **Importante!** Se o usuário excluído usou um computador pessoal para baixar arquivos de SharePoint e OneDrive, não há como apagar os arquivos armazenados no computador. Eles continuarão a ter acesso a todos os arquivos que foram sincronizados OneDrive.           |
|Email  <br/> | Dar acesso a outro usuário ao email do usuário excluído converterá a caixa de correio do usuário excluída em uma caixa de correio compartilhada. Em seguida, o novo proprietário da caixa de correio pode acessar a caixa de correio e monitorar novos emails. Você também terá as seguintes opções:  <br/>  <br/>Alterar o nome de exibição - Recomendamos alterar o nome de exibição para que seja fácil identificar a caixa de correio compartilhada na lista **usuários ativos.**  <br/>  Ativar respostas automáticas - Já escrevemos uma resposta automática educada para você. Você pode enviar respostas automáticas diferentes para pessoas de sua organização e pessoas de fora da sua organização.  <br/> <br/> Limpar aliases - Aliases são endereços de email adicionais para usuários. Algumas organizações não as usam, portanto, se você não tiver nenhuma, não precisará fazer mais nada aqui. Se o usuário tiver aliases, recomendamos removê-los para que você possa reutilizar esses endereços de email. Caso contrário, você não poderá reutilizar esses endereços de email até que o período de retenção das caixas de correio excluídas tenha passado. Por padrão, uma caixa de correio excluída pode ser recuperada por 30 dias. Para obter mais informações, [consulte Delete or restore user mailboxes in Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox). <br/> |
|Active Directory  <br/> |Se a sua empresa usa o **Active Directory** sincronizado com o Azure AD, é necessário excluir a conta de usuário do Active Directory. Não é possível fazê-lo no Office 365. Para obter instruções, consulte [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).  <br/> |

### <a name="get-started"></a>Introdução

Como a experiência guiada percorre as etapas para excluir um usuário, veja como começar.

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

::: moniker-end

2. Selecione o usuário que você deseja excluir e selecione **Excluir usuário**.

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Administrador de gerenciamento de usuários: exclua um ou mais usuários do Office 365

> [!IMPORTANT]
> Não exclua a conta de um [](../email/convert-user-mailbox-to-shared-mailbox.md) usuário se você a converteu em uma caixa de correio compartilhada ou se você definiu o encaminhamento de email na conta. Essas funções ainda precisam da conta. Uma caixa de correio compartilhada não exige uma licença. Se você tiver convertido a conta em uma caixa de correio compartilhada, poderá [parar de pagar pela licença](#stop-paying-for-the-license). Se você configurar o encaminhamento de email na conta, não poderá remover a licença. Isso interromperá o encaminhamento de email e desativará a caixa de correio.
  
::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.  

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

::: moniker-end

2. Selecione os nomes dos usuários que você deseja excluir, selecione os três pontos (mais ações) e escolha  **Excluir usuário**.

   Embora você tenha excluído a conta do usuário, **você ainda está pagando pela licença**. Consulte o próximo procedimento para parar de pagar a licença.  Ou você pode atribuir a licença a outro usuário. Ele não será atribuído a alguém automaticamente.

### <a name="stop-paying-for-the-license"></a>Parar de pagar pela licença

Reduzir o número de licenças é uma etapa separada que só pode ser executada pelo administrador global ou pelo administrador de cobrança.
  
::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.
::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Seus produtos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Seus produtos</a>.
::: moniker-end

2. Na guia **Produtos,** selecione a assinatura para a que você deseja remover licenças.

3. Na página de detalhes da assinatura, selecione **Remover licenças**.

4. No painel **Remover licenças,** em **Nova quantidade**, na caixa Total de **licenças,** insira o número total de licenças que você deseja para essa assinatura. Por exemplo, se você tiver 100 licenças e quiser remover cinco delas, digite 95.

5. Selecione **Salvar**.

Mais tarde, quando você passar pelas etapas para adicionar outra pessoa à sua empresa, você será solicitado a comprar uma licença ao mesmo tempo, com apenas uma etapa!

## <a name="delete-many-users-at-the-same-time"></a>Excluir muitos usuários ao mesmo tempo

Consulte o cmdlet [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell.

## <a name="fix-issues-with-deleting-a-user"></a>Corrigir problemas na exclusão de um usuário

Aqui estão os problemas mais comuns que as pessoas encontram ao excluir um usuário:
  
- **Você recebeu uma mensagem de erro ao longo das linhas de "O usuário não pode ser excluído. Tente novamente mais tarde."** Verifique se a conta tem o encaminhamento de email definido nele ou se ela foi convertida em uma caixa de correio compartilhada. Ambos causarão esse erro. Não exclua a conta se ela tiver encaminhamento de email ou se tiver sido convertida em uma caixa de correio compartilhada.

- **Você não tem as permissões adequadas para excluir um usuário**. Somente as pessoas que Microsoft 365 [administradores globais ou administradores de](about-admin-roles.md) gerenciamento de usuários podem excluir usuários. Normalmente, esse é o suporte técnico disponível em sua escola ou empresa.

- **Você exclui o usuário, mas o nome dele continua aparecendo no catálogo de endereços global**. Isso acontece quando uma empresa está usando o Active Directory. Você deve excluir a conta de usuários do Active Directory. Para obter instruções, consulte [Excluir uma conta de usuário.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

**Deseja excluir o Microsoft 365 do computador? Vá para [Cancelar sua assinatura](../../commerce/subscriptions/cancel-your-subscription.md).**

## <a name="related-content"></a>Conteúdo relacionado

[Restaurar um usuário](restore-user.md) (artigo)\
[Excluir permanentemente uma caixa de](/exchange/permanently-delete-a-mailbox-exchange-2013-help) correio (artigo)\
[Remover um ex-funcionário do Office 365](remove-former-employee.md) (artigo)\
[Adicionar um novo funcionário ao Office 365](add-new-employee.md) (artigo)\
[Excluir uma Conta de Usuário](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)): Use estas instruções se sua empresa usar o Active **Directory** que está sincronizando com o Azure AD. Não é possível fazê-lo no Office 365. (artigo)