---
title: 'Etapa 7: Configurar o controle de identidade'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Compreender e configurar o controle de identidade para o locatário do Azure AD.
ms.openlocfilehash: a965b74afc680c2ff506e0fc2ddebc280ee312a1
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982904"
---
# <a name="step-7-configure-identity-governance"></a>Etapa 7: Configurar o controle de identidade

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

O controle de identidades é sobre proteção, monitoramento e auditoria do acesso a ativos essenciais enquanto garante a produtividade dos funcionários. Por exemplo, com o controle de identidade, você pode garantir que os usuários certos tenham o acesso apropriado aos recursos necessários e determinar se esse acesso muda com o tempo.

Confira [este artigo](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) para saber mais sobre o controle de identidade para o Azure Active Directory (Azure AD).

<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a>Configurar revisões de acesso do Azure AD

*Isso é opcional e só se aplica à versão E5 do Microsoft 365 Enterprise*

Nesta etapa, você configurará as revisões de acesso do Azure AD, que permitem que você examine o acesso de um usuário para garantir que apenas as pessoas certas tenham acesso contínuo. Por exemplo:

- A medida que um novo funcionárioingressa na sua organização, você precisa garantir que ele tenha o acesso certo para ser produtivo.
- Quando esse funcionário se move para outras equipes, locais ou departamentos, você precisa garantir que o acesso a equipes, locais ou departamentos anteriores sejam removidos conforme necessário.
- Quando esse funcionário ou um convidado deixa sua organização, você precisará garantir que seu acesso seja removido.

Isso é especialmente importante se a sua organização está sujeita a auditorias de segurança para determinar se as contas de usuários têm muito acesso, o que pode resultar em multas se estiverem se violar os regulamentos da região ou do setor.

Confira [este artigo](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) para saber mais sobre as revisões de acesso do Azure AD.

Confira estes artigos para configurar os diferentes tipos de revisões de acesso:

- [Grupos e aplicativos](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Funções do Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Funções de recurso do Azure](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-access-reviews) para esta seção.

## <a name="next-step"></a>Próxima etapa

[Critérios de saída da infraestrutura de identidade](identity-exit-criteria.md)

