---
title: Atribuir funções de administrador ao Microsoft 365 de administração
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
ms.openlocfilehash: e53d1a414d081ddb74a1c4784adcd982b6194691
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683206"
---
# <a name="assign-admin-roles"></a>Atribuir funções de administrador

Se você for a pessoa que comprou sua assinatura de negócios da Microsoft, será o administrador global. Isso significa que você tem controle ilimitado sobre os produtos em suas assinaturas e pode acessar a maioria dos dados.

Para obter mais informações, confira o artigo [Sobre funções de administrador](about-admin-roles.md).

Quando você adiciona novos usuários, se você não atribuir a  eles uma função de administrador, eles estão na função de usuário e não têm privilégios de administrador em nenhum dos centros de administração da Microsoft. Mas se você precisar de ajuda para fazer as coisas, poderá atribuir uma função de administrador a um usuário. Por exemplo, se você precisar de alguém para ajudar a redefinir senhas, não deve atribuir a elas a função de administrador global, você deve atribuí-las a função de administrador de senha. Ter muitos administradores globais, com acesso ilimitado aos seus dados e negócios online, é um risco de segurança.

## <a name="watch-add-an-adminbrbr"></a>Watch: Adicionar um administrador<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

Se você achou esse vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](../../business-video/index.yml).

## <a name="assign-admin-roles"></a>Atribuir funções de administrador 

Você pode atribuir usuários a uma função de duas maneiras diferentes:

- Você pode ir até os detalhes do usuário e **Gerenciar funções** para atribuir uma função ao usuário.
- Ou você pode ir para **Funções** e selecionar a função e adicionar vários usuários a ela.

### <a name="assign-admin-roles-to-users-using-roles"></a>Atribuir funções de administrador a usuários usando funções

1. No centro de administração, vá para **Funções**. Escolha as **guias Azure AD** ou **Intune** para exibir as funções de administrador disponíveis para sua organização.
2. Selecione a função de administrador à que você deseja atribuir o usuário.
3. Selecione **Administradores atribuídos**  >  **Adicionar**.
4. Digite o nome de **exibição ou** o nome de usuário **do** usuário e selecione o usuário na lista de sugestões.
5. Adicione vários usuários até terminar.
6. Selecione **Salvar** e, em seguida, o usuário será adicionado à lista de administradores atribuídos.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Atribuir um usuário a uma função de administrador a partir de Usuários ativos

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a **página Usuários** > [Usuários ativos.](https://go.microsoft.com/fwlink/p/?linkid=834822)

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

::: moniker-end

2. Na página **Usuários ativos,** selecione o usuário cuja função de administrador você deseja alterar. No painel sublevado, em **Funções**, selecione **Gerenciar funções**.

3. Selecione a função de administrador que deseja atribuir ao usuário. Se você não vir a função que está procurando, selecione **Mostrar tudo** na parte inferior da lista.

## <a name="assign-admin-roles-to-multiple-users"></a>Atribuir funções de administrador para vários usuários

Se você conhece o PowerShell, consulte [Atribuir funções a contas de usuário com o PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md). Ele é ideal para atribuir funções a centenas de usuários.
  
Use as instruções a seguir para atribuir funções a dezenas de usuários.

## <a name="check-admin-roles-in-your-organization"></a>Verificar funções de administrador em sua organização

Talvez você não tenha as permissões corretas para atribuir funções de administrador a outros usuários. Verifique se você tem as permissões corretas ou peça a outro administrador para atribuir funções para você.

Você pode verificar permissões de função de administrador de duas maneiras diferentes:

- Você pode ir até os detalhes do usuário e procurar em **Funções** na **página Conta.**
- Ou você pode ir para **Funções** e selecionar a função de administrador e selecionar administradores atribuídos para ver quais usuários são atribuídos.

## <a name="related-content"></a>Conteúdo relacionado

[Sobre Microsoft 365 de administrador](about-admin-roles.md) (artigo)\
[Permissões de função de administrador Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) (artigo)\
[Atribuir funções a contas de usuário com o PowerShell](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md) (artigo)\
[Autorizar ou remover relacionamentos de parceiros](../misc/add-partner.md) (artigo)