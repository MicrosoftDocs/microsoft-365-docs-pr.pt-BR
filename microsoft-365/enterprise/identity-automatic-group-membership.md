---
title: 'Etapa 15: Configurar associação de grupo dinâmica'
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
description: Entender e configurar a associação de grupo automática com base nos atributos de conta.
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865195"
---
# <a name="step-15-set-up-dynamic-group-membership"></a>Etapa 15: Configurar associação de grupo dinâmica

*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Nesta etapa, você vai criar uma série de regras que adicionam ou removem automaticamente contas de usuários como membros de um grupo no Azure AD, o que é conhecido como *associação de grupo dinâmica*. As regras são baseadas nos atributos de conta de usuário, como o departamento ou o país.

Veja aqui como as regras são aplicadas:

- Se uma nova conta de usuário atende a todas as regras do grupo, ela se tornará membro.
- Se a conta de usuário não for um membro do grupo, mas seus atributos forem alterados de modo que ela passa a atender a todas as regras do grupo, ela se tornará membro desse grupo.
- Se a conta de usuário não atender a toda as regras do grupo, ela não será incluída no grupo.
- Se a conta de usuário for membro do grupo, mas seus atributos forem alterados de modo que ela passe a não atender mais a todas as regras do grupo, ela será removida do grupo.

Para usar a associação dinâmica, primeiro você precisa determinar os conjuntos de grupos que possuem um conjunto comum de atributos de conta de usuário. Por exemplo, todos os membros do departamento de vendas devem estar no grupo de vendas no Azure AD, com base em no atributo de conta de usuário por departamento definido como "Vendas".

Consulte as [instruções para criar e configurar regras para um grupo dinâmico no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

Os resultados desta etapa são:

- um conjunto de grupos do Azure AD que pode ser configurado quanto à associação dinâmica;
- um conjunto de regras em cada grupo dinâmico.

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: automatizar licenças e associação a grupos](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Como ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-dyn-groups) para esta etapa.

## <a name="next-step"></a>Próxima etapa

[Critérios de saída da infraestrutura de identidade](identity-exit-criteria.md)
