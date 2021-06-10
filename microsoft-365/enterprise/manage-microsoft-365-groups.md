---
title: Gerenciar grupos do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Saiba mais sobre como gerenciar Microsoft 365 grupos.
ms.openlocfilehash: 529bdb874661329497b103a1207b90625ad33a4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911002"
---
# <a name="manage-microsoft-365-groups"></a>Gerenciar grupos do Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Você pode gerenciar Microsoft 365 grupos de várias maneiras diferentes, dependendo da configuração. Você pode gerenciar contas de usuário no centro de administração [do](../admin/add-users/index.yml)Microsoft 365 , PowerShell, nos Serviços de Domínio do Active Directory (AD DS) ou no centro de administração do [Azure Active Directory (Azure AD).](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>Planejar onde e como você gerenciará seus grupos

Onde e como você pode gerenciar suas contas de usuário depende do modelo de identidade que você deseja usar para sua Microsoft 365. Os dois modelos gerais são somente na nuvem e híbridos.
  
### <a name="cloud-only"></a>Apenas Nuvem

Você cria e gerencia grupos com:

- [O Centro de administração do Microsoft 365](../admin/add-users/index.yml)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Centro de Administração do Microsoft Azure AD](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>Híbrido

Os grupos do AD DS são sincronizados com Microsoft 365 do AD DS, portanto, você deve usar as ferramentas locais do AD DS para gerenciar esses grupos.

Você também pode criar e gerenciar grupos do Azure AD separados de grupos do AD DS, mas que podem conter usuários e grupos do AD DS. Nesse caso, você pode usar:

- [O Centro de administração do Microsoft 365](../admin/add-users/index.yml)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Centro de Administração do Microsoft Azure AD](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Permitir que usuários criem e gerenciem os próprios grupos

O Azure AD permite grupos que podem ser gerenciados por proprietários de grupo em vez de administradores de IT. Conhecido como *gerenciamento de grupos de autoatendimento*, este recurso permite que proprietários de grupos que não foram atribuídos a uma função administrativa para criar e gerenciar grupos de segurança. 

Os usuários podem solicitar a associação a um grupo de segurança, e essa solicitação vai para o proprietário do grupo e não para o administrador da TI. Isso permite que o controle diário da associação ao grupo seja delegado a equipes, projetos ou aos proprietários da empresa, os quais entendem o uso comercial do grupo e podem gerenciar as suas associações.

>[!Note]
>O gerenciamento de grupo de autoatendimento está disponível apenas aos grupos de segurança do Azure AD e Microsoft 365. Ele não está disponível para grupos habilitados para email, listas de distribuição ou qualquer grupo que tenha sido sincronizado do AD DS.
>

Para saber mais, consulte as [instruções para configurar um grupo do Azure AD para o gerenciamento de autoatendimento](/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

## <a name="set-up-dynamic-group-membership"></a>Configurar associações de grupo dinâmico

O Azure AD dá suporte à configuração de uma série de regras que adicionam ou removem automaticamente contas de usuário como membros de um grupo do Azure AD. Isso é conhecido como *associação de grupo dinâmico*. As regras se baseiam em atributos das contas de usuário, como Departamento ou País.

Veja como as regras são aplicadas:

- Se uma nova conta de usuário atende a todas as regras do grupo, ela se tornará membro.
- Se uma conta de usuário não for um membro do grupo, mas seus atributos forem alterados para corresponder a todas as regras do grupo, ela se tornará um membro desse grupo.
- Se uma conta de usuário não corresponder a todas as regras do grupo, ela não será adicionada ao grupo.
- Se a conta de usuário for membro do grupo, mas seus atributos forem alterados de modo que ela passe a não atender mais a todas as regras do grupo, ela será removida do grupo.

Para usar a associação dinâmica, você deve primeiro determinar os conjuntos de grupos que possuem um conjunto comum de atributos de conta do usuário. Por exemplo, todos os membros do Departamento de vendas devem estar no grupo Sales Azure AD, com base no atributo de conta de usuário Departamento definido como "Vendas".

Consulte as [instruções para criar e configurar regras para um grupo dinâmico no Azure AD](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

## <a name="set-up-automatic-licensing"></a>Configurar licenciamento automático

Você pode configurar grupos de segurança no Azure AD para atribuir automaticamente licenças de um conjunto de assinaturas a todos os membros do grupo. Isso é conhecido como *licenciamento baseado em grupo*. Se uma conta de usuário for adicionada ou removida do grupo, as licenças das assinaturas do grupo serão automaticamente atribuídas ou não atribuídas à conta do usuário.

No Microsoft 365 Enterprise, você configurará grupos de segurança do Azure AD para atribuir as licenças apropriadas do Microsoft 365 Enterprise.

Verifique se você tem licenças suficientes para todos os membros do grupo. Se você ficar sem licenças, os novos usuários não receberão licenças até que as licenças estejam disponíveis.

>[!Note]
>Você não deve configurar o licenciamento baseado em grupo para grupos que contenham contas do Azure para empresas (B2B).
>

Para obter mais informações, consulte Noções básicas de licenciamento baseado [em grupo no Azure AD](/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Consulte as [instruções para configurar o licenciamento baseado em grupo para um grupo de segurança do Azure.](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)