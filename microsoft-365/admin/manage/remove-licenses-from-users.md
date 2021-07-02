---
title: Cancelar a atribuição de licenças de usuários
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: O método que você usa para desasignar licenças de produto depende se você desa desa desemarcar licenças de usuários específicos ou de um produto específico.
ms.date: 06/07/2021
ms.openlocfilehash: 6220ddc15e7b3381da1d78ad3ac4f3c2204bda78
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256826"
---
# <a name="unassign-licenses-from-users"></a>Cancelar a atribuição de licenças de usuários

Você pode desasignar licenças  de usuários na página Usuários ativos ou na página **Licenças.** O método usado depende se você deseja desasincar licenças de produtos de usuários específicos ou desasincar licenças de usuários de um produto específico.

> [!NOTE]
> Como administrador, você não pode atribuir ou cancelar a atribuição de licenças para uma assinatura de compra de autoatendimento comprada por um usuário em sua organização. Você pode [assumir uma assinatura de compra de autoatendimento](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), e, em seguida, atribuir ou cancelar a atribuição de licenças.

## <a name="before-you-begin"></a>Antes de começar

- Você deve ser um administrador global, licença, usuário para desasincar licenças. Para obter mais informações, consulte [Sobre as funções de administrador do Microsoft 365](../add-users/about-admin-roles.md).
- Você pode [remover licenças a contas de usuário com o Office 365 PowerShell](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).
- Você também pode [excluir contas de usuário](../add-users/delete-a-user.md) que foram atribuídas a uma licença para disponibilizar sua licença para outros usuários. Quando você exclui uma conta de usuário, sua licença está disponível imediatamente para atribuir a outra pessoa.

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Usar a página Licenças para desasincar licenças

Quando você usa a página **Licenças** para desasincar licenças, desaigna licenças para um produto específico para até 20 usuários.

::: moniker range="o365-worldwide"

1. No centro de administração, acesse a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. No centro de administração, acesse a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenças</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. No centro de administração, acesse a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenças</a>.

::: moniker-end

2. Selecione o produto para o qual você deseja desasincar licenças.
3. Selecione os usuários para os quais você deseja desasincar licenças.
4. Selecione **Unassign licenses**.
5. Na caixa **Licenças não assinadas,** selecione **Unassign**.

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Usar a página Usuários ativos para desasinalhar licenças

Quando você usa a **página Usuários ativos** para desaignar licenças, você desaigna licenças de produtos de usuários.

### <a name="unassign-licenses-from-one-user"></a>Unassign licenses from one user

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

::: moniker-end

2. Selecione a linha do usuário para o que você deseja desaignar uma licença.
3. No painel direito, selecione **Licenças e Aplicativos**.
4. Expanda **a seção Licenças,** limpe as caixas das licenças que você deseja desasinalhar e selecione **Salvar alterações**.

### <a name="unassign-licenses-from-multiple-users"></a>Unassign licenses from multiple users

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

::: moniker-end

2. Selecione os círculos ao lado dos nomes dos usuários para os que você deseja desasinalhar licenças.
3. Na parte superior, selecione **Gerenciar licenças de produtos**.
4. No painel **Gerenciar licenças de** produto, selecione **Unassign all** Save  >  **changes**.
5. Na parte inferior do painel, selecione **Feito**.  

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>O que acontece com os dados de um usuário ao remover a licença?

- Quando uma licença é removida de um usuário, Exchange dados online associados a essa conta são mantidos por 30 dias. Após o período de carência de 30 dias, os dados são excluídos e não podem ser recuperados.
- Os arquivos salvos OneDrive for Business não são excluídos, a menos que o usuário seja excluído do Centro de administração do Microsoft 365 ou seja removido por meio da sincronização do Active Directory. Para obter mais informações, [consulte OneDrive retenção e exclusão.](/onedrive/retention-and-deletion)
- Quando a licença é removida, a caixa de correio do usuário não é mais pesquisável usando uma ferramenta de Descoberta Eletrônico, como Pesquisa de Conteúdo ou Advanced eDiscovery. Para obter mais informações, consulte "Pesquisar caixas de correio desconectadas ou des licenciadas" em Pesquisa de [Conteúdo em Microsoft 365](../../compliance/content-search.md).
- Se você tiver uma assinatura Enterprise, como Office 365 Enterprise E3, Exchange Online permite preservar os dados de caixa de correio de uma conta de usuário excluída usando caixas de correio [inativas](../../compliance/inactive-mailboxes-in-office-365.md). Para obter mais informações, [consulte Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).
- Para saber como bloquear o acesso de um usuário a Microsoft 365 dados após a remoção da licença e como obter acesso aos dados posteriormente, consulte [Remove a former employee](../add-users/remove-former-employee.md).
- Se você remover a licença de um usuário e eles ainda Office [aplicativos instalados,](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) eles verão erros de ativação e produto não licenciado no Office quando eles usam Office aplicativos.

## <a name="next-steps"></a>Próximas etapas

Se você não vai reatribuir as [licenças](../../managed-desktop/get-started/assign-licenses.md)nãousadas para outros usuários , considere remover as [licenças](../../commerce/licenses/buy-licenses.md) da sua assinatura para que você não esteja pagando por mais licenças do que precisa.

## <a name="related-content"></a>Conteúdo relacionado

[Remover licenças de sua assinatura](../../commerce/licenses/buy-licenses.md) (artigo)\
[Atribuir licenças aos usuários](assign-licenses-to-users.md) (artigo) \
[Compreender assinaturas e licenças no Microsoft 365 para empresas](../../commerce/licenses/subscriptions-and-licenses.md) (artigo)
