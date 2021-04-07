---
title: Atribuir funções de administrador ao Centro de administração do Microsoft 365
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
description: Saiba como atribuir funções de administrador a um usuário ou vários usuários em sua empresa para que eles possam executar tarefas específicas no centro de administração.
ms.openlocfilehash: 5c40199823c93968be97302efc8e2d404f3cfed1
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604328"
---
# <a name="assign-admin-roles"></a>Atribuir funções de administrador

Se você for a pessoa que comprou sua assinatura de negócios da Microsoft, será o administrador global. Isso significa que você tem controle ilimitado sobre os produtos em suas assinaturas e pode acessar a maioria dos dados.

Para obter mais informações, confira [Sobre funções de administrador](about-admin-roles.md).

Quando você adiciona novos usuários, se você não atribuir a  eles uma função de administrador, eles estão na função de usuário e não têm privilégios de administrador em nenhum dos centros de administração da Microsoft. Mas se você precisar de ajuda para fazer as coisas, poderá atribuir uma função de administrador a um usuário. Por exemplo, se você precisar de alguém para ajudar a redefinir senhas, não deve atribuir a elas a função de administrador global, você deve atribuí-las a função de administrador de senha. Ter muitos administradores globais, com acesso ilimitado aos seus dados e negócios online, é um risco de segurança.

## <a name="watch-add-an-adminbrbr"></a>Assista: Adicionar um administrador.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

Se você achou este vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades para o Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="assign-admin-roles"></a>Atribuir funções de administrador 

::: moniker range="o365-worldwide"

Você pode atribuir usuários a uma função de duas maneiras diferentes:

- Você pode ir até os detalhes do usuário e **Gerenciar funções** para atribuir uma função ao usuário.
- Ou você pode ir para **Funções** e selecionar a função e adicionar vários usuários a ela.

### <a name="assign-admin-roles-to-users-using-roles"></a>Atribuir funções de administrador a usuários usando funções

1. No centro de administração, vá para **Funções**. Escolha as **guias Azure AD** ou **Intune** para exibir as funções de administrador disponíveis para sua organização.
2. Selecione a função de administrador à que você deseja atribuir o usuário.
3. Selecione **Administradores atribuídos** > **Adicionar**.
4. Digite o nome de **exibição ou** o nome de usuário **do** usuário e selecione o usuário na lista de sugestões.
5. Adicione vários usuários até terminar.
6. Selecione **Salvar** e, em seguida, o usuário será adicionado à lista de administradores atribuídos.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Atribuir um usuário a uma função de administrador de usuários ativos

1. No centro de administração, vá para a **página Usuários** > [Usuários ativos.](https://go.microsoft.com/fwlink/p/?linkid=834822)

2. Na página **Usuários ativos,** selecione o usuário cuja função de administrador você deseja alterar. No painel sublevado, em **Funções**, selecione **Gerenciar funções**.

3. Selecione a função de administrador que você deseja atribuir ao usuário. Se você não vir a função que está procurando, selecione **Mostrar tudo** na parte inferior da lista.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Na página **Usuários ativos,** selecione o usuário cuja função de administrador você deseja alterar. No painel de sobrevoos, ao lado de **Funções,** selecione **Editar**. 

    Se você não vir a opção **Editar,** não terá permissão para editar e não poderá atribuir funções de administrador a outras pessoas. Peça a um administrador global em sua empresa para atribuir funções para você. Em uma pequena empresa, o proprietário da empresa (a pessoa que comprou sua assinatura) é um administrador global. Em uma grande empresa, as pessoas-chave no departamento de IT são administradores globais.

3. Selecione **Administrador personalizado** para ver uma lista de funções personalizadas para você. Para uma descrição de cada função, consulte [Sobre funções de administrador.](about-admin-roles.md)

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Na página **Usuários ativos,** selecione o usuário cuja função de administrador você deseja alterar. No painel de sobrevoos, ao lado de **Funções,** selecione **Editar**.

    Se você não vir a opção **Editar,** não terá permissão para editar e não poderá atribuir funções de administrador a outras pessoas. Peça a um administrador global em sua empresa para atribuir funções para você. Em uma pequena empresa, o proprietário da empresa (a pessoa que comprou sua assinatura) é um administrador global. Em uma grande empresa, as pessoas-chave no departamento de IT são administradores globais.

3. Selecione **Administrador personalizado** para ver uma lista de funções personalizadas para você. Para uma descrição de cada função, consulte [Sobre funções de administrador.](about-admin-roles.md)

::: moniker-end

## <a name="assign-admin-roles-to-multiple-users"></a>Atribuir funções de administrador para vários usuários

Se você conhece o PowerShell, consulte [Atribuir funções a contas de usuário com o PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md). Ele é ideal para atribuir funções a centenas de usuários.
  
Use as instruções a seguir para atribuir funções a dezenas de usuários.

::: moniker range="o365-worldwide"

## <a name="check-admin-roles-in-your-organization"></a>Verificar funções de administrador em sua organização

Talvez você não tenha as permissões corretas para atribuir funções de administrador a outros usuários. Verifique se você tem as permissões corretas ou peça a outro administrador para atribuir funções para você.

Você pode verificar permissões de função de administrador de duas maneiras diferentes:

- Você pode ir até os detalhes do usuário e procurar em **Funções** na **página Conta.**
- Ou você pode ir para **Funções** e selecionar a função de administrador e selecionar administradores atribuídos para ver quais usuários são atribuídos.

::: moniker-end

## <a name="related-articles"></a>Artigos relacionados

[Sobre as funções de administrador do Microsoft 365 ](about-admin-roles.md)

[Permissões da função de administrador no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)

[Atribuir funções a contas de usuário com o PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)

[Autorizar ou remover relacionamentos de parceiros](../misc/add-partner.md)