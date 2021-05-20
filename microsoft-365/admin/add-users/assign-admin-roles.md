---
title: Atribuir funções administrativas ao centro administrativo Microsoft 365
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
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: Aprenda a atribuir funções de administrador a um usuário ou a vários usuários em sua empresa para que eles possam executar tarefas específicas no centro administrativo.
ms.openlocfilehash: f23a30cfd1be53982572d745d476558c3be615e6
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571860"
---
# <a name="assign-admin-roles"></a>Atribuir funções de administrador

Se você é a pessoa que comprou sua assinatura de negócios da Microsoft, você é o administrador global. Isso significa que você tem controle ilimitado sobre os produtos em suas assinaturas e você pode acessar a maioria dos dados.

Para mais informações, consulte [Sobre funções de administrador](about-admin-roles.md).

Quando você adiciona novos usuários, se você não atribuir a eles uma função de administração, então eles estão na *função de usuário* e não têm privilégios administrativos para nenhum dos centros administrativos da Microsoft. Mas se você precisar de ajuda para fazer as coisas, você pode atribuir uma função de administração a um usuário. Por exemplo, se você precisar de alguém para ajudar a redefinir senhas, você não deve atribuir a elas a função de administração global, você deve atribuir-lhes a função de administrador de senha. Ter muitos administradores globais, com acesso ilimitado aos seus dados e negócios online, é um risco de segurança.

## <a name="watch-add-an-adminbrbr"></a>Assista: Adicione um administrador.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

Se você achou esse vídeo útil, confira as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](../../business-video/index.yml).

## <a name="assign-admin-roles"></a>Atribuir funções de administrador 

::: moniker range="o365-worldwide"

Você pode atribuir os usuários a uma função de 2 maneiras diferentes:

- Você pode ir aos detalhes do usuário e **gerenciar funções** para atribuir uma função ao usuário.
- Ou você pode ir para **Funções** e selecionar a função e, em seguida, adicionar vários usuários a ela.

### <a name="assign-admin-roles-to-users-using-roles"></a>Atribuir funções administrativas aos usuários usando Funções

1. No centro administrativo, vá para **Papéis.** Escolha as guias **Azure AD** ou **Intune** para visualizar as funções de administração disponíveis para sua organização.
2. Selecione a função de administração a que deseja atribuir ao usuário.
3. Selecione **Adicionar administradores atribuídos** > .
4. Digite o nome de **exibição** ou nome de **usuário** do usuário e selecione o usuário na lista de sugestões.
5. Adicione vários usuários até terminar.
6. Selecione **Salvar** e, em seguida, o usuário será adicionado à lista de administradores atribuídos.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Atribuir um usuário a uma função de administrador a partir de Usuários ativos

1. Na central administrativa, acesse a página **usuários** > [ativos](https://go.microsoft.com/fwlink/p/?linkid=834822) dos usuários.

2. Na página **usuários ativos,** selecione o usuário cuja função de administração você deseja alterar. No painel flyout, em **Roles**, selecione **Gerenciar funções**.

3. Selecione a função de administrador que deseja atribuir ao usuário. Se você não ver o papel que está procurando, selecione **Mostrar tudo** na parte inferior da lista.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Na página **usuários ativos,** selecione o usuário cuja função de administração você deseja alterar. No painel flyout, ao lado **de Roles**, selecione **Editar**. 

    Se você não ver a opção **Editar,** então você não tem permissão para editar e não pode atribuir funções administrativas a outras pessoas. Peça a um administrador global em seu negócio para atribuir funções para você. Em uma pequena empresa, o dono do negócio (a pessoa que comprou sua assinatura) é um administrador global. Em uma grande empresa, as pessoas-chave no departamento de TI são administradores globais.

3. Selecione **administrador personalizado** para ver uma lista de funções que personalizamos para você. Para obter uma descrição de cada papel, consulte [Sobre papéis administrativos.](about-admin-roles.md)

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Na página **usuários ativos,** selecione o usuário cuja função de administração você deseja alterar. No painel flyout, ao lado **de Roles**, selecione **Editar**.

    Se você não ver a opção **Editar,** então você não tem permissão para editar e não pode atribuir funções administrativas a outras pessoas. Peça a um administrador global em seu negócio para atribuir funções para você. Em uma pequena empresa, o dono do negócio (a pessoa que comprou sua assinatura) é um administrador global. Em uma grande empresa, as pessoas-chave no departamento de TI são administradores globais.

3. Selecione **administrador personalizado** para ver uma lista de funções que personalizamos para você. Para obter uma descrição de cada papel, consulte [Sobre papéis administrativos.](about-admin-roles.md)

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a>Atribuir funções de administrador para vários usuários

Se você conhece o PowerShell, consulte [Atribuir funções a contas de usuário com o PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md). Ele é ideal para atribuir funções a centenas de usuários.
  
Use as instruções a seguir para atribuir funções a dezenas de usuários.

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a>Verifique os papéis da administração em sua organização

Você pode não ter as permissões corretas para atribuir funções administrativas a outros usuários. Verifique se você tem as permissões corretas ou peça a outro administrador para atribuir funções para você.

Você pode verificar as permissões de papel administrativo de 2 maneiras diferentes:

- Você pode ir até os detalhes do usuário e olhar em **Funções** na página **Conta.**
- Ou você pode ir para **Funções** e selecionar a função administradora e selecionar administradores atribuídos para ver quais usuários são atribuídos.

::: moniker-end

## <a name="related-content"></a>Conteúdo relacionado

[Sobre Microsoft 365 papéis administrativos](about-admin-roles.md) (artigo)

[Permissões de função do administrador em Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (artigo)

[Atribuir funções a contas de usuário com o PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (artigo)

[Autorizar ou remover relações de parceiros](../misc/add-partner.md) (artigo)