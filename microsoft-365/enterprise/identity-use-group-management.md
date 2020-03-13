---
title: 'Etapa 5: usar os grupos para gerenciamento'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Você pode usar os grupos para automatizar o gerenciamento de algumas tarefas administrativas.
ms.openlocfilehash: 215bb84cbb0cedc2f1320372ba8239cd51d07c98
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544040"
---
# <a name="step-5-use-groups-for-management"></a>Etapa 5: usar os grupos para gerenciamento

![Fase 2 – Identidade](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Permitir que usuários criem e gerenciem os próprios grupos

*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 *

Nesta seção, você identificará grupos do Azure Active Directory (Azure AD) que podem ser gerenciados por proprietários de grupos em vez de administradores de TI. Conhecido como *gerenciamento de grupos de autoatendimento*, este recurso permite que proprietários de grupos que não foram atribuídos a uma função administrativa para criar e gerenciar grupos de segurança. 

Os usuários podem solicitar a associação a um grupo de segurança, e essa solicitação vai para o proprietário do grupo e não para o administrador da TI. Isso permite que o controle diário da associação ao grupo seja delegado a equipes, projetos ou aos proprietários da empresa, os quais entendem o uso comercial do grupo e podem gerenciar as suas associações.

>[!Note]
>O gerenciamento de grupos de autoatendimento está disponível apenas para os grupos de segurança do Azure AD e do Office 365. Ele não está disponível para grupos habilitados para email, listas de distribuição ou qualquer grupo que tenha sido sincronizado de serviços locais de domínio do Active Directory (AD DS).
>

Para saber mais, consulte as [instruções para configurar um grupo do Azure AD para o gerenciamento de autoatendimento](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-self-service-groups) para esta seção.

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a>Configurar associações de grupo dinâmico

*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 *

Nesta seção, você criará uma série de regras que vão adicionar ou remover automaticamente contas de usuários como membros do um grupo do Azure AD. Isso é conhecido como *associação de grupo dinâmico*. As regras se baseiam em atributos das contas de usuário, como Departamento ou País.

Veja aqui como as regras são aplicadas:

- Se uma nova conta de usuário atende a todas as regras do grupo, ela se tornará membro.
- Se a conta de usuário não for um membro do grupo, mas seus atributos forem alterados de modo que ela passa a atender a todas as regras do grupo, ela se tornará membro desse grupo.
- Se a conta de usuário não atender a toda as regras do grupo, ela não será incluída no grupo.
- Se a conta de usuário for membro do grupo, mas seus atributos forem alterados de modo que ela passe a não atender mais a todas as regras do grupo, ela será removida do grupo.

Para usar a associação dinâmica, primeiro você precisa determinar os conjuntos de grupos que possuem um conjunto comum de atributos de conta de usuário. Por exemplo, todos os membros do departamento de vendas devem estar no grupo de vendas no Azure AD, com base em no atributo de conta de usuário por departamento definido como "Vendas".

Consulte as [instruções para criar e configurar regras para um grupo dinâmico no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

Os resultados desta seção são:

- um conjunto de grupos do Azure AD que pode ser configurado quanto à associação dinâmica;
- um conjunto de regras em cada grupo dinâmico.

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: automatizar licenças e associação a grupos](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-dyn-groups) para esta seção.

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a>Configurar licenciamento automático

*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 *

Nesta seção, você vai configurar grupos de segurança no Azure AD para atribuir licenças automaticamente de um conjunto de assinaturas para todos os membros do grupo. Isso é conhecido como *licenciamento baseado em grupo*. Se uma conta de usuário for adicionada ou removida do grupo, as licenças das assinaturas do grupo serão atribuída ou terão a atribuição cancelada automaticamente da conta do usuário.

No Microsoft 365 Enterprise, você configurará grupos de segurança do Azure AD para atribuir as licenças apropriadas do Microsoft 365 Enterprise.

Verifique se você tem licenças suficientes para todos os membros do grupo. Caso as licenças acabem, os novos usuários não receberão licenças até que elas fiquem disponíveis.

>[!Note]
>Você não deve configurar o *licenciamento baseado em grupo* para grupos que contenham contas do Azure para empresas (B2B).
>

Consulte as [noções básicas sobre o licenciamento baseado em grupo no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Consulte as [etapas para configurar o licenciamento baseado em grupo para um grupo de segurança do Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).

Os resultados desta seção são:

- Você identificou quais grupos de segurança são adequados para o licenciamento baseado em grupo.
- Você configurou esses grupos para o licenciamento baseado em grupo.

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: automatizar licenças e associação a grupos](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-group-license) desta seção.

|||
|:-------|:-----|
|![Etapa 6](../media/stepnumbers/Step6.png)| [Configurar o controle de identidade](identity-configure-identity-governance.md) |
