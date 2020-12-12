---
title: Adicionar ou remover membros dos grupos da Microsoft 365
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
description: Saiba como adicionar um membro a um grupo, remover membro do grupo e gerenciar o status do proprietário do grupo no centro de administração do Microsoft 365.
ms.openlocfilehash: 34c026bced5563e07a1ae0d13f4c691cfaf3f624
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663238"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>Adicionar ou remover membros dos grupos do Microsoft 365 usando o centro de administração

No Microsoft 365, os membros do grupo normalmente criam seus próprios grupos, adicionam-se a grupos que desejam participar ou são convidados por proprietários de grupo. Se a propriedade de grupo for alterada ou se você determinar que um membro deve ser adicionado ou removido, como administrador, você também pode fazer essa alteração. Somente um administrador global, administrador do Exchange, administrador de grupos ou administrador de usuários pode fazer essas alterações. [O que é um grupo do Microsoft 365?](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> Se você não for um administrador, poderá [Adicionar ou remover membros usando o Outlook](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de).
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>Adicionar um membro a um grupo no centro de administração

1. No centro de administração, vá para a página [**grupos ativos**](https://admin.microsoft.com/Adminportal/Home?#/groups) .  

2. Clique em um nome de grupo.

3. No painel de detalhes, na guia **Membros** , selecione **Exibir todos e gerenciar Membros** e, em seguida, selecione **adicionar membros**.

4. Pesquisar ou selecionar o nome do membro que você deseja adicionar.

5. Selecione **Salvar**.

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>Adicionar um grupo a um membro no centro de administração

1. No centro de administração, vá para a página [**usuários ativos**](https://admin.microsoft.com/Adminportal/Home?#/users) .  

2. Clique em um usuário.

3. No painel de detalhes, na guia **conta** , selecione **gerenciar grupos**.

4. Procure ou selecione o nome do grupo que você deseja adicionar.

5. Selecione **Salvar**.

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>Remover um membro de um grupo no centro de administração

> [!NOTE]
> Quando você remove um membro de um grupo privado, leva cinco minutos para a pessoa ser bloqueada do grupo.

1. No centro de administração, vá para a página [**grupos ativos**](https://admin.microsoft.com/Adminportal/Home?#/groups) .  

2. Clique em um nome de grupo.

3. No painel de detalhes, na guia **Membros** , selecione **Exibir todos e gerenciar Membros**.

4. Ao lado do membro que você deseja remover, selecione o X.

5. Selecione **salvar** para remover o membro.

## <a name="manage-group-owner-status"></a>Gerenciar o status do proprietário do grupo

Por padrão, a pessoa que criou o grupo é o proprietário dele. Muitas vezes, um grupo pode ter vários proprietários, para dar suporte de backup ou por outros motivos. Os membros podem ser promovidos ao status de proprietários, e os proprietários podem ser rebaixados ao status de membros.
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>Promover um membro ao status do proprietário no centro de administração

1. No centro de administração, vá para a página [**grupos ativos**](https://admin.microsoft.com/Adminportal/Home?#/groups) .  

2. Clique em um nome de grupo.

3. No painel de detalhes, na guia **Membros** , selecione **Exibir todos os proprietários e gerenciá**-los.

4. Selecione **Adicionar proprietários**.

5. Marque a caixa de seleção ao lado do nome do membro que você deseja adicionar.

6. Selecione **salvar** e **fechar**.

### <a name="remove-owner-status-in-the-admin-center"></a>Remover o status do proprietário no centro de administração

1. No centro de administração, vá para a página [**grupos ativos**](https://admin.microsoft.com/Adminportal/Home?#/groups) .  

2. Clique em um nome de grupo.

3. No painel de detalhes, na guia **Membros** , selecione **Exibir todos os proprietários e gerenciá**-los.

4. Selecione o X ao lado do nome do proprietário.

5. Selecione **Salvar**.

## <a name="more-on-managing-membership"></a>Mais sobre o gerenciamento de associações

- [Gerenciar grupos dinamicamente no Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=847632): confira a seção "Como posso gerenciar a associação de um grupo dinamicamente?"

- Para adicionar centenas ou milhares de usuários a grupos, use o [Add-UnifiedGroupLinks](https://docs.microsoft.com/powershell/module/exchange/add-unifiedgrouplinks).

- [Atribuir um novo proprietário a um grupo órfão](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="articles-about-managing-groups"></a>Artigos sobre o gerenciamento de grupos

- [Atualizar listas de distribuição para grupos do Microsoft 365 no Outlook](../manage/upgrade-distribution-lists.md)

- [Por que você deve atualizar suas listas de distribuição para grupos no Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

- [Gerenciar o acesso de convidados nos grupos do Microsoft 365](manage-guest-access-in-groups.md)

- [Gerenciar os grupos do Microsoft 365 com o PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell): Este artigo apresenta os principais cmdlets e fornece exemplos

- [Política de nomenclatura de grupos do Microsoft 365](groups-naming-policy.md)
