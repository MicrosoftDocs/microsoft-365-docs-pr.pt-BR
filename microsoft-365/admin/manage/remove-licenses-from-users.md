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
description: Saiba como desaignar licenças de contas de usuário.
ms.date: 07/01/2020
ms.openlocfilehash: 858daaf0069ecba3e6ff65ce957462764b45c22c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915189"
---
# <a name="unassign-licenses-from-users"></a>Cancelar a atribuição de licenças de usuários

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

Você pode desasignar licenças  de usuários na página Usuários ativos ou na página **Licenças.** O método usado depende se você deseja desasincar licenças de produtos de usuários específicos ou desasincar licenças de usuários de um produto específico.

::: moniker-end

## <a name="before-you-begin"></a>Antes de começar

- Você deve ser um administrador global, licença, usuário para desasincar licenças. Para obter mais informações, consulte [Sobre as funções de administrador do Microsoft 365](../add-users/about-admin-roles.md).
- Você pode [remover licenças a contas de usuário com o Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).
- Você também pode [excluir contas de usuário](../add-users/delete-a-user.md) que foram atribuídas a uma licença para disponibilizar sua licença para outros usuários. Quando você exclui uma conta de usuário, sua licença está disponível imediatamente para atribuir a outra pessoa.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Usar a página Licenças para desasincar licenças

Quando você usa a página **Licenças** para desasincar licenças, desaigna licenças para um produto específico para até 20 usuários.

1. No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.
2. Selecione o produto para o qual você deseja desasincar licenças.
3. Selecione os usuários para os quais você deseja desasincar licenças.
4. Selecione **Unassign licenses**.
5. Na caixa **Licenças não assinadas,** selecione **Unassign**.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Usar a página Usuários ativos para desasinalhar licenças

Quando você usa a **página Usuários ativos** para desaignar licenças, você desaigna licenças de produtos de usuários.

### <a name="unassign-licenses-from-one-user"></a>Unassign licenses from one user
  
1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione a linha do usuário para o que você deseja desaignar uma licença.
3. No painel direito, selecione **Licenças e Aplicativos**.
4. Expanda **a seção Licenças,** limpe as caixas das licenças que você deseja desasinalhar e selecione **Salvar alterações**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Unassign licenses from one user

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.
2. Escolha o usuário para o que você deseja desaignar a licença.
3. À direita, na linha **Licenças do** produto, selecione **Editar**.
4. No painel **Licenças de** produto, alterne  a alternância para a posição Off da licença que você deseja desasinchar para o usuário. Por exemplo, se você desligar a licença do Office 365 Enterprise E3, ela desaigna essa licença e todos os serviços sob essa licença para esse usuário.
5. Na parte inferior do painel **Licenças de produto**, escolha **Salvar** \> **Fechar** \> **Fechar**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Unassign licenses from one user

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.
2. Escolha o usuário para o que você deseja desaignar a licença.
3. À direita, na linha **Licenças do** produto, selecione **Editar**.
4. No painel **Licenças de** produto, alterne  a alternância para a posição Off da licença que você deseja desasinchar para o usuário. Por exemplo, se você desligar a licença do Office 365 Enterprise E3, ela desaigna essa licença e todos os serviços sob essa licença para esse usuário.
5. Na parte inferior do painel **Licenças de produto**, escolha **Salvar** \> **Fechar** \> **Fechar**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Unassign licenses from multiple users

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione os círculos ao lado dos nomes dos usuários para os que você deseja desasinalhar licenças.
3. Na parte superior, selecione **mais opções (...)**, em seguida, selecione **Gerenciar licenças de produtos**.
4. No painel **Gerenciar licenças de produtos**, selecione **Substituir atribuições de licença de produto existentes** \> **Avançar**.
5. Na parte inferior do painel **Substituir produtos** existentes, marque a caixa de seleção Remover todas **as licenças** de produto da caixa de seleção Usuários e, em seguida, selecione **Substituir** \> **Fechar**.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Unassign licenses from multiple users

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.
2. Selecione as caixas ao lado dos nomes dos usuários para os que você deseja desaignar todas as licenças.
3. No painel **Ações em massa**, escolha **Editar licenças de produto**.
4. No painel **Substituir produtos existentes**, escolha **Substituir atribuições de licenças de produtos existentes** \> **Avançar**.
5. Na parte inferior do painel Substituir **produtos** existentes, marque a caixa de seleção Remover todas as **licenças** de produto da caixa de seleção usuários e, em seguida, selecione **Substituir** \> **Fechar** \> **Fechar.**

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Unassign licenses from multiple users
  
1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.
2. Selecione as caixas ao lado dos nomes dos usuários para os que você deseja desaignar todas as licenças.
3. No painel **Ações em massa**, escolha **Editar licenças de produto**.
4. No painel **Substituir produtos existentes**, escolha **Substituir atribuições de licenças de produtos existentes** \> **Avançar**.
5. Na parte inferior do painel Substituir **produtos** existentes, marque a caixa de seleção Remover todas as **licenças** de produto da caixa de seleção usuários e, em seguida, selecione **Substituir** \> **Fechar** \> **Fechar.**

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>O que acontece com os dados de um usuário ao remover a licença?

- Quando uma licença é removida de um usuário, os dados associados a essa conta são mantidos por 30 dias. Após o período de carência de 30 dias, os dados são excluídos e não podem ser recuperados.
- Os arquivos salvos no OneDrive for Business não são excluídos, a menos que o usuário seja excluído do centro de administração do Microsoft 365 ou seja removido por meio da sincronização do Active Directory. Para obter mais informações, consulte Retenção e exclusão do [OneDrive.](/onedrive/retention-and-deletion)
- Quando a licença é removida, a caixa de correio do usuário não é mais pesquisável usando uma ferramenta de Descoberta Eletrônico, como Pesquisa de Conteúdo ou Descoberta Avançada. Para obter mais informações, consulte "Pesquisar caixas de correio desconectadas ou des licenciadas" na Pesquisa de [Conteúdo no Microsoft 365](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes).
- Se você tiver uma assinatura enterprise, como o Office 365 Enterprise E3, o Exchange Online permitirá que você preserve os dados de caixa de correio de uma conta de usuário excluída usando caixas de correio [inativas](../../compliance/inactive-mailboxes-in-office-365.md). Para obter mais informações, [consulte Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).
- Para saber como bloquear o acesso de um usuário aos dados do Microsoft 365 após a remoção da licença e como obter acesso aos dados posteriormente, consulte [Remove a former employee](../add-users/remove-former-employee.md).
- Se você remover a licença de um usuário e eles ainda têm aplicativos do Office [instalados,](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) eles verão Erros de ativação e produto não licenciado no Office quando eles usam aplicativos do Office.

## <a name="next-steps"></a>Próximas etapas

Se você não vai reatribuir as [licenças](../../managed-desktop/get-started/assign-licenses.md)nãousadas para outros usuários , considere remover as [licenças](../../commerce/licenses/buy-licenses.md) da sua assinatura para que você não esteja pagando por mais licenças do que precisa.

## <a name="related-content"></a>Conteúdo relacionado

[Remover licenças de sua assinatura](../../commerce/licenses/buy-licenses.md) (artigo)\
[Atribuir licenças aos usuários](assign-licenses-to-users.md) (artigo) \
[Compreender assinaturas e licenças no Microsoft 365 para empresas](../../commerce/licenses/subscriptions-and-licenses.md) (artigo)