---
title: Atribuir licenças aos usuários
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Aprenda a atribuir licenças aos usuários.
ms.date: 08/14/2020
ms.openlocfilehash: 9f044f29cabf4976d5fbf17b22777da62e4414c5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915489"
---
# <a name="assign-licenses-to-users"></a>Atribuir licenças aos usuários

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

Você pode atribuir licenças a usuários na página **Usuários ativos** ou na página **Licenças**. O método usado depende de você querer atribuir licenças do produto a usuários específicos ou atribuir licenças de usuários a um produto específico.

::: moniker-end

[Aprenda como adicionar um usuário e atribuir uma licença ao mesmo tempo](../add-users/add-users.md).

## <a name="before-you-begin"></a>Antes de começar

- Você deve ser um administrador global, de licença ou de usuário para atribuir licenças. Para obter mais informações, consulte [Sobre as funções de administrador do Microsoft 365](../add-users/about-admin-roles.md).
- Você pode [atribuir licenças às contas de usuários com o Office 365 PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).
- Para obter mais instruções do licenciamento baseado em grupo, consulte [Atribuir licenças a usuários por membro de grupo no Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).
- Alguns serviços, como o Sway, são atribuídos automaticamente aos usuários e não precisam ser atribuídos individualmente.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>Use a página Licenças para atribuir licenças aos usuários

Ao usar a página **Licenças** para atribuir licenças, você atribui licenças de um produto específico para até 20 usuários. Na página **Licenças**, você verá uma lista de todos os produtos que você possui assinaturas. Você também verá o número total de licenças de cada produto, quantas licenças são atribuídas e quantas estão disponíveis.

1. No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.
2. Selecione um produto.
3. Na página de detalhes do produto, selecione **Atribuir licenças**.
4. No painel **Atribuir licenças a usuários**, comece a digitar um nome e, em seguida, selecione-o nos resultados para adicioná-lo à lista. É possível selecionar até 20 usuários de cada vez.
5. Selecione **Ativar ou desativar os aplicativos e serviços** para atribuir ou remover o acesso a itens específicos.
6. Quando tiver terminado, clique em **Atribuir** e depois em **Fechar**.

Se houver um conflito, será exibida uma mensagem informando qual é o problema e como corrigi-lo. Por exemplo, se você selecionou licenças que contêm serviços conflitantes, a mensagem de erro indicará revisar os serviços incluídos em cada licença e tentar novamente.

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>Para alterar os aplicativos e serviços que o usuário tem acesso:

1. No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.
2. Na página **Licenças**, selecione a linha de um usuário específico.
3. No painel direito, marque ou desmarque os aplicativos e serviços aos quais você deseja conceder acesso ou remover o acesso.
4. Quando tiver terminado, selecione **Salvar**, e então selecione **Fechar**.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a>Use a página Usuários ativos para atribuir licenças

Ao usar a página **Usuários ativos** para atribuir licenças, você atribui licenças de usuários a produtos.

### <a name="assign-licenses-to-multiple-users"></a>Atribuir licenças a vários usuários

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione os círculos ao lado dos nomes dos usuários aos quais você quer atribuir licenças.
3. Na parte superior, selecione **mais opções (...)**, em seguida, selecione **Gerenciar licenças de produtos**.
4. No painel **Gerenciar licenças de produtos**, selecione **Adicionar a atribuições de licença de produto existentes** \> **.Avançar**.
5. No painel **Adicionar a produtos existentes**, alterne o botão para a posição **Ativado** nas licenças que você quer que os usuários selecionados tenham.\
    Por padrão, todos os serviços associados a essa licença são atribuídos automaticamente ao usuário. Você pode limitar quais serviços estão disponíveis para os usuários. Alterne o botão a posição **Desativado** para os serviços que você não deseja que os usuários tenham.
6. Na parte inferior do painel, selecione **Adicionar** \> **Fechar**.  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a>Atribuir licenças a vários usuários

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.
2. Selecione as caixas ao lado dos nomes dos usuários aos quais você quer atribuir licenças.
3. No painel **Ações em massa**, escolha **Editar licenças de produto**.
4. No painel **Atribuir produtos**, selecione **Adicionar a atribuições de licença de produto existentes** \> **Avançar**.
5. Alterne para a posição **Ativado** das licenças que você quer que os usuários selecionados tenham.\
    Por padrão, todos os serviços associados a essa licença são atribuídos automaticamente ao usuário. Você pode limitar quais serviços estão disponíveis para os usuários. Alterne o botão a posição **Desativado** para os serviços que você não deseja que os usuários tenham.
6. Na parte inferior do painel **Adicionar a produtos existentes**, selecione **Adicionar** \> **Fechar**\> **Fechar**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a>Atribuir licenças a vários usuários

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.
2. Selecione as caixas ao lado dos nomes dos usuários aos quais você quer atribuir licenças.
3. No painel **Ações em massa**, escolha **Editar licenças de produto**.
4. No painel **Atribuir produtos**, selecione **Adicionar a atribuições de licença de produto existentes** \> **Avançar**.
5. Alterne para a posição **Ativado** das licenças que você quer que os usuários selecionados tenham.\
    Por padrão, todos os serviços associados a essa licença são atribuídos automaticamente ao usuário. Você pode limitar quais serviços estão disponíveis para os usuários. Alterne o botão a posição **Desativado** para os serviços que você não deseja que os usuários tenham.
6. Na parte inferior do painel **Adicionar a produtos existentes**, selecione **Adicionar** \> **Fechar**\> **Fechar**.

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a>Atribuir licenças a um usuário

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione a linha do usuário ao qual você quer atribuir uma licença.
3. No painel direito, selecione **Licenças e Aplicativos**.
4. Expanda a seção **Licenças**, marque as caixas das licenças que você deseja atribuir e, em seguida, selecione **salvar alterações**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a>Atribuir licenças a um usuário

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.
2. Selecione a caixa ao lado do nome do usuário ao qual você quer atribuir uma licença.
3. No painel direito, na linha **Licenças do produto**, clique em **Editar**.
4. No painel **Licenças do produto**, alterne o botão para a posição **Ativado** na licença que você quer atribuir ao usuário.
    Por padrão, todos os serviços associados a essa licença são atribuídos automaticamente ao usuário. Você pode limitar quais serviços estão disponíveis para os usuários. Alterne o botão a posição **Desativado** para os serviços que você não deseja que os usuários tenham.
5. Na parte inferior do painel **Licenças de produto**, escolha **Salvar** \> **Fechar** \> **Fechar**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a>Atribuir licenças a um usuário

1. No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.
2. Selecione a caixa ao lado do nome do usuário ao qual você quer atribuir uma licença.
3. No painel direito, na linha **Licenças do produto**, clique em **Editar**.
4. No painel **Licenças do produto**, alterne o botão para a posição **Ativado** na licença que você quer atribuir ao usuário.
    Por padrão, todos os serviços associados a essa licença são atribuídos automaticamente ao usuário. Você pode limitar quais serviços estão disponíveis para os usuários. Alterne o botão a posição **Desativado** para os serviços que você não deseja que os usuários tenham.
5. Na parte inferior do painel **Licenças de produto**, escolha **Salvar** \> **Fechar** \> **Fechar**.

::: moniker-end

## <a name="assign-a-license-to-a-guest-user"></a>Atribuir uma licença a um usuário convidado

É possível convidar usuários convidados para colaborar com sua organização no centro de administração do Azure Active Directory. Para saber mais sobre os usuários convidados, confira [O que é acesso de usuário convidado no Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b). Se você não tiver nenhum usuário convidado, confira [Início Rápido: Adicionar usuários convidados ao seu diretório no portal do Azure](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

> [!IMPORTANT]
> Você terá de ser um administrador global para executar essas etapas.

1. Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">centro de administração do Azure Active Directory</a>
2. No painel de navegação, selecione **Usuários**.
3. Na página **Usuários | Todos os Usuários (Visualização)**, selecione **Adicionar filtros**.
4. No menu **Escolher um campo**, escolha o **Tipo de usuário** e selecione **Aplicar**.
5. No menu seguinte, selecione **Convidado**.
6. Na lista de resultados, selecione o usuário que precisa de uma licença.
7. Em **Gerenciar**, selecione **Licenças**.
8. Selecione **Atribuições**.
9. Na página **Atualizar atribuições de licença**, selecione o produto para o qual deseja atribuir uma licença.
10. À direita, desmarque as caixas de seleção dos serviços às quais você não deseja que o usuário convidado tenha acesso.
11. Clique em **Salvar**.

## <a name="next-steps"></a>Próximas etapas

Se os usuários ainda não tiverem os aplicativos do Office instalados, você poderá compartilhar a [Guia de início rápido dos funcionários](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) com os usuários para configurar coisas, do tipo [como baixar e instalar o Microsoft 365 ou o Office 2019 em um computador ou Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) e [como configurar aplicativos do Office e e-mails em um dispositivo móvel](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Conteúdo relacionado

[Compreender assinaturas e licenças](../../commerce/licenses/subscriptions-and-licenses.md) (artigo)\
[Cancelar a atribuição de licenças de usuários](remove-licenses-from-users.md) (artigo)\
[Compre ou remova licenças da sua assinatura](../../commerce/licenses/buy-licenses.md) (artigo)