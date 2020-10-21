---
title: Cancelar a atribuição de licenças de usuários
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Saiba como cancelar a atribuição de licenças de contas de usuário.
ms.date: 07/01/2020
ms.openlocfilehash: 455348e7dba20913e54e5a4059755f9391644e03
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645090"
---
# <a name="unassign-licenses-from-users"></a>Cancelar a atribuição de licenças de usuários

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

Você pode cancelar a atribuição de licenças de usuários na página **usuários ativos** ou na página **licenças** . O método a ser usado depende se você deseja cancelar a atribuição de licenças de produto de usuários específicos ou cancelar a atribuição de licenças de usuários de um produto específico.

::: moniker-end

## <a name="before-you-begin"></a>Antes de começar

- Você deve ser um administrador global, de licença, de usuário para cancelar a atribuição de licenças. Para obter mais informações, consulte [Sobre as funções de administrador do Microsoft 365](../add-users/about-admin-roles.md).
- Você pode [remover licenças a contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).
- Você também pode [excluir contas de usuário](../add-users/delete-a-user.md) que receberam uma licença para disponibilizar sua licença para outros usuários. Quando você exclui uma conta de usuário, sua licença fica imediatamente disponível para ser atribuída a outra pessoa.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Usar a página licenças para cancelar a atribuição de licenças

Quando você usa a página **licenças** para cancelar a atribuição de licenças, você não atribui licenças de um produto específico para até 20 usuários.

1. No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.
2. Selecione o produto para o qual você deseja cancelar a atribuição de licenças.
3. Selecione os usuários para os quais você deseja cancelar a atribuição de licenças.
4. Selecione cancelar a **atribuição de licenças**.
5. Na caixa cancelar **atribuição de licenças** , selecione Cancelar **atribuição**.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Usar a página usuários ativos para cancelar a atribuição de licenças

Quando você usa a página **usuários ativos** para cancelar a atribuição de licenças, você não atribui licenças de produto dos usuários.

### <a name="unassign-licenses-from-one-user"></a>Cancelar a atribuição de licenças de um usuário
  
1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione a linha do usuário para a qual você deseja cancelar a atribuição de uma licença.
3. No painel direito, selecione **Licenças e Aplicativos**.
4. Expanda a seção **licenças** , desmarque as caixas das licenças que você deseja cancelar a atribuição e, em seguida, selecione **salvar alterações**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Cancelar a atribuição de licenças de um usuário

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.
2. Selecione o usuário para o qual você deseja cancelar a atribuição da licença.
3. No lado direito, na linha **licenças de produto** , selecione **Editar**.
4. No painel **licenças de produto** , alterne a opção para a posição **desativado** da licença que você deseja cancelar a atribuição para o usuário. Por exemplo, se você desativar a licença do Office 365 Enterprise E3, ela cancelará a atribuição dessa licença e de todos os serviços sob essa licença para o usuário.
5. Na parte inferior do painel **Licenças de produto**, escolha **Salvar** \> **Fechar** \> **Fechar**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Cancelar a atribuição de licenças de um usuário

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.
2. Selecione o usuário para o qual você deseja cancelar a atribuição da licença.
3. No lado direito, na linha **licenças de produto** , selecione **Editar**.
4. No painel **licenças de produto** , alterne a opção para a posição **desativado** da licença que você deseja cancelar a atribuição para o usuário. Por exemplo, se você desativar a licença do Office 365 Enterprise E3, ela cancelará a atribuição dessa licença e de todos os serviços sob essa licença para o usuário.
5. Na parte inferior do painel **Licenças de produto**, escolha **Salvar** \> **Fechar** \> **Fechar**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Cancelar a atribuição de licenças de vários usuários

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione os círculos ao lado dos nomes dos usuários aos quais você deseja cancelar a atribuição de licenças.
3. Na parte superior, selecione **mais opções (...)**, em seguida, selecione **Gerenciar licenças de produtos**.
4. No painel **Gerenciar licenças de produtos**, selecione **Substituir atribuições de licença de produto existentes** \> **Avançar**.
5. Na parte inferior do painel **substituir produtos existentes** , marque a caixa de seleção **remover todas as licenças de produtos dos usuários selecionados** e, em seguida, selecione **substituir** \> **fechar**.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Cancelar a atribuição de licenças de vários usuários

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.
2. Selecione as caixas ao lado dos nomes dos usuários aos quais você deseja cancelar a atribuição de todas as licenças.
3. No painel **Ações em massa**, escolha **Editar licenças de produto**.
4. No painel **Substituir produtos existentes**, escolha **Substituir atribuições de licenças de produtos existentes** \> **Avançar**.
5. Na parte inferior do painel **substituir produtos existentes** , marque a caixa de seleção **remover todas as licenças de produtos dos usuários selecionados** e, em seguida, selecione **substituir** \> **fechar** \> **fechar**.

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Cancelar a atribuição de licenças de vários usuários
  
1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.
2. Selecione as caixas ao lado dos nomes dos usuários aos quais você deseja cancelar a atribuição de todas as licenças.
3. No painel **Ações em massa**, escolha **Editar licenças de produto**.
4. No painel **Substituir produtos existentes**, escolha **Substituir atribuições de licenças de produtos existentes** \> **Avançar**.
5. Na parte inferior do painel **substituir produtos existentes** , marque a caixa de seleção **remover todas as licenças de produtos dos usuários selecionados** e, em seguida, selecione **substituir** \> **fechar** \> **fechar**.

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>O que acontece com os dados de um usuário quando você remove sua licença?

- Quando uma licença é removida de um usuário, os dados associados a essa conta são mantidos por 30 dias. Após o período de cortesia de 30 dias, os dados são excluídos e não podem ser recuperados.
- Arquivos salvos no OneDrive for Business não são excluídos, a menos que o usuário seja excluído do centro de administração do Microsoft 365 ou seja removido por meio da sincronização do Active Directory. Para obter mais informações, consulte [retenção e exclusão do onedrive](https://docs.microsoft.com/onedrive/retention-and-deletion).
- Quando a licença for removida, a caixa de correio do usuário não poderá mais ser pesquisada usando uma ferramenta de descoberta eletrônica, como pesquisa de conteúdo ou descoberta eletrônica avançada. Para obter mais informações, consulte "pesquisando caixas de correio desconectadas ou deslicenciadas" em [pesquisa de conteúdo no Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).
- Se você tiver uma assinatura corporativa, como o Office 365 Enterprise E3, o Exchange Online permite preservar os dados da caixa de correio de uma conta de usuário excluída usando [caixas de correio inativas](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365). Para obter mais informações, consulte [criar e gerenciar caixas de correio inativas no Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).
- Para saber como bloquear o acesso de um usuário aos dados do Microsoft 365 depois que a licença for removida e como obter acesso aos dados posteriormente, confira [remover um funcionário antigo](../add-users/remove-former-employee.md).
- Se você remover a licença de um usuário e ele ainda tiver aplicativos do Office instalados, eles verão [erros de ativação e de produto não licenciado no Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) quando usarem aplicativos do Office.

## <a name="next-steps"></a>Próximas etapas

Se você não pretende [reatribuir as licenças não usadas a outros usuários](../../managed-desktop/get-started/assign-licenses.md), considere [remover as licenças da sua assinatura](../../commerce/licenses/buy-licenses.md) para que não esteja pagando por mais licenças do que você precisa.

## <a name="related-content"></a>Conteúdo relacionado

[Remover licenças da sua assinatura](../../commerce/licenses/remove-licenses-from-subscription.md) (artigo) \
[Atribuir licenças aos usuários](assign-licenses-to-users.md) (artigo) \
[Entender assinaturas e licenças no Microsoft 365 for Business](../../commerce/licenses/subscriptions-and-licenses.md) (artigo)