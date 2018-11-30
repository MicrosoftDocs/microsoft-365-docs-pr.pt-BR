---
title: 'Etapa 14: Permitir que usuários criem e gerenciem seus próprios grupos'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar o gerenciamento de grupos de autoatendimento do Azure AD.
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865008"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a>Etapa 14: Permitir que usuários criem e gerenciem seus próprios grupos

*Esta etapa é opcional e aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Nesta etapa, você vai identificar os grupos do Azure Active Directory (AD) que podem ser gerenciados por proprietários de grupos em vez de administradores de TI. Conhecido como *gerenciamento de grupos de autoatendimento*, esse recurso permite que os proprietários de grupos que não estejam atribuídos a uma função administrativa criem e gerenciem grupos de segurança. 

Os usuários podem solicitar a associação a um grupo de segurança, e essa solicitação vai para o proprietário do grupo e não para o administrador da TI. Isso permite que o controle diário da associação ao grupo seja delegado a equipes, projetos ou aos proprietários da empresa, os quais entendem o uso comercial do grupo e podem gerenciar as suas associações.

>[!Note]
>O gerenciamento de grupos de autoatendimento está disponível apenas para os grupos do Office 365 e de segurança do Azure AD. Não está disponível para grupos habilitados para email, listas de distribuição ou qualquer outro grupo que tenha sido sincronizado no Windows Server Active Directory (AD) local.
>

Para saber mais, consulte as [instruções para configurar um grupo do Azure AD para o gerenciamento de autoatendimento](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

Como ponto de verificação provisório, você pode consultar os [critérios de saída](identity-exit-criteria.md#crit-identity-self-service-groups) para esta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [Configurar a associação de grupo dinâmica](identity-automatic-group-membership.md) |
