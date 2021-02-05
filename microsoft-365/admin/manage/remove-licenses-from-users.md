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
description: Saiba como desa designar licenças de contas de usuário.
ms.date: 07/01/2020
ms.openlocfilehash: 6fb07883fdfd4f4a837890e3e8c4c04b2411772b
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114472"
---
# <a name="unassign-licenses-from-users"></a>Cancelar a atribuição de licenças de usuários

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

::: moniker range="o365-worldwide"

Você pode desa designar licenças de usuários na página Usuários **ativos** ou **na página Licenças.** O método usado depende se você deseja desa designar licenças de produto de usuários específicos ou desa designar licenças de usuários de um produto específico.

::: moniker-end

## <a name="before-you-begin"></a>Antes de começar

- Você deve ser um administrador global, de licença, de usuário para desa designar licenças. Para obter mais informações, consulte [Sobre as funções de administrador do Microsoft 365](../add-users/about-admin-roles.md).
- Você pode [remover licenças a contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).
- Você também pode [excluir contas de usuário](../add-users/delete-a-user.md) que foram atribuídas a uma licença para disponibilizar sua licença para outros usuários. Quando você exclui uma conta de usuário, a licença fica imediatamente disponível para ser atribuído a outra pessoa.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Usar a página Licenças para desa designar licenças

Ao usar a **página Licenças** para desa designar licenças, você desafere licenças para um produto específico para até 20 usuários.

1. No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.
2. Selecione o produto para o qual você deseja desaignar licenças.
3. Selecione os usuários para os quais você deseja desaignar licenças.
4. Selecione **Unassign licenses**.
5. In the **Unassign licenses** box, select **Unassign**.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Usar a página Usuários ativos para desa designar licenças

Ao usar a página **Usuários ativos** para desa designar licenças, você desafere licenças de produto dos usuários.

### <a name="unassign-licenses-from-one-user"></a>Desa designar licenças de um usuário
  
1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione a linha do usuário para o que você deseja desa designar uma licença.
3. No painel direito, selecione **Licenças e Aplicativos**.
4. Expanda **a seção Licenças,** des clear the boxes for the licenses that you want to unasign, then select **Save changes**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Desa designar licenças de um usuário

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.
2. Escolha o usuário para o que você deseja retirar a licença.
3. À direita, na linha **Licenças de** produto, selecione **Editar**.
4. No painel **Licenças de** produto, alterne  o botão para a posição Desligado para a licença que você deseja desa designar para o usuário. Por exemplo, se você desligar a licença do Office 365 Enterprise E3, ela desa designa essa licença e todos os serviços sob essa licença para esse usuário.
5. Na parte inferior do painel **Licenças de produto**, escolha **Salvar** \> **Fechar** \> **Fechar**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Desa designar licenças de um usuário

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.
2. Escolha o usuário para o que você deseja retirar a licença.
3. À direita, na linha **Licenças de** produto, selecione **Editar**.
4. No painel **Licenças de** produto, alterne  o botão para a posição Desligado para a licença que você deseja desa designar para o usuário. Por exemplo, se você desligar a licença do Office 365 Enterprise E3, ela desa designa essa licença e todos os serviços sob essa licença para esse usuário.
5. Na parte inferior do painel **Licenças de produto**, escolha **Salvar** \> **Fechar** \> **Fechar**.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Desa designar licenças de vários usuários

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione os círculos ao lado dos nomes dos usuários para os quem você deseja rea designar licenças.
3. Na parte superior, selecione **mais opções (...)**, em seguida, selecione **Gerenciar licenças de produtos**.
4. No painel **Gerenciar licenças de produtos**, selecione **Substituir atribuições de licença de produto existentes** \> **Avançar**.
5. At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close**.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Desa designar licenças de vários usuários

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.
2. Selecione as caixas ao lado dos nomes dos usuários para os que você deseja desa designar todas as licenças.
3. No painel **Ações em massa**, escolha **Editar licenças de produto**.
4. No painel **Substituir produtos existentes**, escolha **Substituir atribuições de licenças de produtos existentes** \> **Avançar**.
5. At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Desa designar licenças de vários usuários
  
1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.
2. Selecione as caixas ao lado dos nomes dos usuários para os que você deseja desa designar todas as licenças.
3. No painel **Ações em massa**, escolha **Editar licenças de produto**.
4. No painel **Substituir produtos existentes**, escolha **Substituir atribuições de licenças de produtos existentes** \> **Avançar**.
5. At the bottom of the **Replace existing products** pane, select the **Remove all product licenses from the selected users** check box, then select **Replace** \> **Close** \> **Close**.

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>O que acontece com os dados de um usuário quando você remove a licença dele?

- Quando uma licença é removida de um usuário, os dados associados a essa conta são mantidos por 30 dias. Após o período de carência de 30 dias, os dados são excluídos e não podem ser recuperados.
- Os arquivos salvos no OneDrive for Business não são excluídos, a menos que o usuário seja excluído do centro de administração do Microsoft 365 ou seja removido por meio da sincronização do Active Directory. Para saber mais, confira a retenção e [a exclusão do OneDrive.](https://docs.microsoft.com/onedrive/retention-and-deletion)
- Quando a licença é removida, a caixa de correio do usuário não é mais pesquisável usando uma ferramenta de Descoberta Eletrônico, como Pesquisa de Conteúdo ou Descoberta Avançada. Para obter mais informações, consulte "Pesquisar caixas de correio desconectadas ou sem licença" na Pesquisa de [Conteúdo no Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)
- Se você tiver uma assinatura Enterprise, como o Office 365 Enterprise E3, o Exchange Online permite preservar os dados da caixa de correio de uma conta de usuário excluída usando caixas de correio [inativas.](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365) Para obter mais informações, consulte Criar e gerenciar caixas de correio [inativas no Exchange Online.](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)
- Para saber como bloquear o acesso de um usuário aos dados do Microsoft 365 após a remoção da licença e como obter acesso aos dados posteriormente, confira Remover um [ex-funcionário.](../add-users/remove-former-employee.md)
- Se você remover a licença de um usuário e ele ainda tiver aplicativos do Office [instalados,](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) ele verá erros de ativação e produto não licenciamento no Office ao usar os aplicativos do Office.

## <a name="next-steps"></a>Próximas etapas

Se você não for reatribuir as [licenças](../../managed-desktop/get-started/assign-licenses.md)nãoutiladas a outros usuários, considere remover as [licenças](../../commerce/licenses/buy-licenses.md) da sua assinatura para que você não esteja pagando por mais licenças do que precisa.

## <a name="related-content"></a>Conteúdo relacionado

[Remover licenças da sua assinatura](../../commerce/licenses/remove-licenses-from-subscription.md) (artigo)\
[Atribuir licenças a usuários](assign-licenses-to-users.md) (artigo)\
[Compreender assinaturas e licenças no Microsoft 365 para empresas](../../commerce/licenses/subscriptions-and-licenses.md) (artigo)