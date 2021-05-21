---
title: Adicionar ou remover membros de Microsoft 365 grupos
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: Saiba como adicionar um membro a um grupo, remover membro do grupo e gerenciar o status do proprietário do grupo no Microsoft 365 de administração.
ms.openlocfilehash: 3ab3ebe21caa2d9d3dfa381dd3b68c9d2512cb79
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593376"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>Adicionar ou remover membros de grupos Microsoft 365 usando o centro de administração

Em Microsoft 365, os membros do grupo normalmente criam seus próprios grupos, se adicionam aos grupos que eles querem ingressar ou são convidados pelos proprietários do grupo. Se a propriedade do grupo mudar ou se você determinar que um membro deve ser adicionado ou removido, como administrador, você também pode fazer essa alteração. Somente um administrador global, Exchange administrador, administrador de grupos ou administrador de usuário pode fazer essas alterações. [O que é um Microsoft 365 grupo?](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> Se você não for um administrador, poderá adicionar [ou remover membros usando Outlook](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de).
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>Adicionar um membro a um grupo no centro de administração

1. No centro de administração, vá para a [**página Grupos ativos.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Clique em um nome de grupo.

3. No painel de detalhes, na guia **Membros,** selecione Exibir todos e **gerenciar** membros e selecione **Adicionar membros**.

4. Pesquisar ou selecionar o nome do membro que você deseja adicionar.

5. Selecione **Salvar**.

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>Adicionar um grupo a um membro no centro de administração

1. No centro de administração, vá para a [**página Usuários ativos.**](https://admin.microsoft.com/Adminportal/Home?#/users)  

2. Clique em um usuário.

3. No painel de detalhes, na **guia** Conta, selecione **Gerenciar grupos**.

4. Pesquise ou selecione o nome do grupo que você deseja adicionar.

5. Selecione **Salvar**.

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>Remover um membro de um grupo no centro de administração

> [!NOTE]
> Quando você remove um membro de um grupo privado, leva 5 minutos para a pessoa ser bloqueada do grupo.

1. No centro de administração, vá para a [**página Grupos ativos.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Clique em um nome de grupo.

3. No painel de detalhes, na guia **Membros,** selecione **Exibir todos e gerenciar membros**.

4. Ao lado do membro que você deseja remover, selecione o X.

5. Selecione **Salvar** para remover o membro.

## <a name="manage-group-owner-status"></a>Gerenciar o status do proprietário do grupo

Por padrão, a pessoa que criou o grupo é o proprietário dele. Muitas vezes, um grupo pode ter vários proprietários, para dar suporte de backup ou por outros motivos. Os membros podem ser promovidos ao status de proprietários, e os proprietários podem ser rebaixados ao status de membros.
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>Promover um membro para o status do proprietário no centro de administração

1. No centro de administração, vá para a [**página Grupos ativos.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Clique em um nome de grupo.

3. No painel de detalhes, na guia **Membros,** selecione **Exibir tudo e gerenciar proprietários.**

4. Selecione **Adicionar proprietários**.

5. Marque a caixa de seleção ao lado do nome do membro que você deseja adicionar.

6. Selecione **Salvar** e, em **seguida, Fechar**.

### <a name="remove-owner-status-in-the-admin-center"></a>Remover o status do proprietário no centro de administração

1. No centro de administração, vá para a [**página Grupos ativos.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Clique em um nome de grupo.

3. No painel de detalhes, na guia **Membros,** selecione **Exibir tudo e gerenciar proprietários.**

4. Selecione o X ao lado do nome do proprietário.

5. Selecione **Salvar**.

## <a name="more-on-managing-membership"></a>Mais sobre o gerenciamento de associações

- [Gerenciar grupos dinamicamente no Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal): confira a seção "Como posso gerenciar a associação de um grupo dinamicamente?"

- Para adicionar centenas ou milhares de usuários a grupos, use [o Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks).

- [Atribuir um novo proprietário a um grupo órfão](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="related-content"></a>Conteúdo relacionado

[Atualizar listas de distribuição para Microsoft 365 grupos em Outlook](../manage/upgrade-distribution-lists.md) (artigo)

[Por que você deve atualizar suas listas de distribuição para grupos no Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) (artigo)

[Gerenciar o acesso de convidados Microsoft 365 grupos](manage-guest-access-in-groups.md) (artigo)

[Gerenciar Microsoft 365 grupos com o PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md): este artigo apresenta os principais cmdlets e fornece exemplos (artigo)

[Microsoft 365 de nomes de grupos](../../solutions/groups-naming-policy.md) (artigo)