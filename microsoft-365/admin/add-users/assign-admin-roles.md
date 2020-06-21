---
title: Atribuir funções de administrador o centro de administração do Microsoft 365
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
ms.openlocfilehash: 59fc2211051aa4f122462186753e7f626715722f
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780632"
---
# <a name="assign-admin-roles"></a>Atribuir funções de administrador

Se você é a pessoa que comprou sua assinatura do Microsoft Business, você é o administrador global. Isso significa que você tem controle ilimitado sobre os produtos em suas assinaturas e pode acessar a maioria dos dados.

Para obter mais informações, consulte [sobre funções de administrador](about-admin-roles.md).

Ao adicionar novos usuários, se você não atribuir a eles uma função de administrador, eles estão na *função de usuário* e não têm privilégios de administrador em nenhum dos centros de administração da Microsoft. Mas se você precisar de ajuda para realizar tarefas, você pode atribuir uma função de administrador a um usuário. Por exemplo, se precisar de alguém para ajudar a redefinir senhas, você não deve atribuir a função de administrador global, você deve atribuir a função de administrador de senha. Ter muitos administradores globais, com acesso ilimitado aos seus dados e à empresa online, é um risco de segurança.

Assista a um pequeno vídeo sobre como adicionar um administrador.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

Se você achou esse vídeo útil, Confira as [ séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="assign-admin-roles"></a>Atribuir funções de administrador 

::: moniker range="o365-worldwide"

Você pode atribuir usuários a uma função de duas maneiras diferentes:

- Você pode ir para os detalhes do usuário e **gerenciar funções** para atribuir uma função ao usuário.
- Ou você pode ir para **funções** e selecionar a função e, em seguida, adicionar vários usuários a ela.

### <a name="assign-admin-roles-to-users-using-roles"></a>Atribuir funções de administrador a usuários usando funções

1. No centro de administração, **vá até funções funções** > **Roles** para exibir todas as funções de administrador disponíveis para sua organização.
2. Selecione a função de administrador à qual você deseja atribuir o usuário.
3. Selecione **Administradores atribuídos** > **Adicionar**.
4. Digite o nome de **exibição** do usuário ou o nome de **usuário**e, em seguida, selecione o usuário na lista de sugestões.
5. Adicione vários usuários até que você tenha concluído.
6. Selecione **salvar**e o usuário será adicionado à lista de administradores atribuídos.

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>Atribuir um usuário a uma função de administrador de usuários ativos

1. No centro de administração, vá para **Users** a > página [usuários ativos](https://go.microsoft.com/fwlink/p/?linkid=834822) do usuário.

2. Na página **usuários ativos** , selecione o usuário cuja função de administrador você deseja alterar. No painel de submenu, ao lado de **funções**, selecione **gerenciar funções**.

3. Selecione a função de administrador que você deseja atribuir ao usuário. Se você não vir a função que está procurando, selecione **Mostrar tudo** na parte inferior da lista.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

2. Na página **usuários ativos** , selecione o usuário cuja função de administrador você deseja alterar. No painel de submenu, ao lado de **funções**, selecione **Editar**. 

    Se você não vir a opção **Editar** , não terá permissão para editar e não poderá atribuir funções de administrador a outras pessoas. Peça a um administrador global em sua empresa para atribuir funções para você. Em uma pequena empresa, o proprietário da empresa (a pessoa que comprou sua assinatura) é um administrador global. Em uma grande empresa, as principais pessoas no departamento de ti são administradores globais.

3. Selecione **administrador personalizado** para ver uma lista de funções que foram personalizadas para você. Para obter uma descrição de cada função, consulte [about admin Roles.](about-admin-roles.md)

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

2. Na página **usuários ativos** , selecione o usuário cuja função de administrador você deseja alterar. No painel de submenu, ao lado de **funções**, selecione **Editar**.

    Se você não vir a opção **Editar** , não terá permissão para editar e não poderá atribuir funções de administrador a outras pessoas. Peça a um administrador global em sua empresa para atribuir funções para você. Em uma pequena empresa, o proprietário da empresa (a pessoa que comprou sua assinatura) é um administrador global. Em uma grande empresa, as principais pessoas no departamento de ti são administradores globais.

3. Selecione **administrador personalizado** para ver uma lista de funções que foram personalizadas para você. Para obter uma descrição de cada função, consulte [about admin Roles.](about-admin-roles.md)

::: moniker-end


## <a name="assign-admin-roles-to-multiple-users"></a>Atribuir funções de administrador para vários usuários

Se você souber o PowerShell, confira [atribuir funções a contas de usuário com o PowerShell](https://go.microsoft.com/fwlink/?linkid=854257). Ele é ideal para atribuir funções a centenas de usuários.
  
Use as instruções a seguir para atribuir funções a dezenas de usuários.

::: moniker range="o365-worldwide"


## <a name="didnt-work-for-you"></a>Não funcionou?

Você pode não ter as permissões corretas e, portanto, não tem acesso para atribuir funções de administrador a outros usuários. Peça a outro administrador para atribuir funções de administrador para você.

::: moniker-end

## <a name="related-articles"></a>Artigos relacionados

[Sobre as funções de administrador do Microsoft 365 ](about-admin-roles.md)

[Atribuir funções a contas de usuário com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-roles-to-user-accounts-with-office-365-powershell)

[Autorizar ou remover relacionamentos de parceiros](../misc/add-partner.md)

[Adicionar um endereço de email alternativo usando o centro de administração do Exchange](https://docs.microsoft.com/Exchange/recipients/user-mailboxes/email-addresses?view=exchserver-2019#add-an-email-address-to-a-user-mailbox)