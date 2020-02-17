---
title: 'Etapa 7: Configurar o controle de identidade'
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
description: Compreender e configurar o controle de identidade para o locatário do Azure AD.
ms.openlocfilehash: 5b7b1c91735611046133a0247ae028ed090106fd
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067348"
---
# <a name="step-6-configure-identity-governance"></a>Etapa 6: configurar o controle de identidade

![Fase 2 – Identidade](../media/deploy-foundation-infrastructure/identity_icon-small.png)

O controle de identidades é sobre proteção, monitoramento e auditoria do acesso a ativos essenciais enquanto garante a produtividade dos funcionários. Por exemplo, com o controle de identidade, você pode garantir que os usuários certos tenham o acesso apropriado aos recursos necessários e determinar se esse acesso muda com o tempo.

Confira [este artigo](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) para saber mais sobre o controle de identidade do Azure Active Directory (Azure AD).


*Isso é opcional e se aplica somente às versões E3 e E5 do Microsoft 365 Enterprise*


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a>Configurar revisões de acesso do Azure AD

*Isso é opcional e só se aplica à versão E5 do Microsoft 365 Enterprise*

Nesta etapa, você configurará as revisões de acesso do Azure AD, que permitem que você examine o acesso de um usuário para garantir que apenas as pessoas certas tenham acesso contínuo. Por exemplo:

- A medida que um novo funcionárioingressa na sua organização, você precisa garantir que ele tenha o acesso certo para ser produtivo.
- Quando esse funcionário se move para outras equipes, locais ou departamentos, você precisa garantir que o acesso a equipes, locais ou departamentos anteriores sejam removidos conforme necessário.
- Quando esse funcionário ou um convidado deixa sua organização, você precisará garantir que seu acesso seja removido.

Isso é especialmente importante se a sua organização está sujeita a auditorias de segurança para determinar se as contas de usuários têm muito acesso, o que pode resultar em multas se estiverem se violar os regulamentos da região ou do setor.

Confira [este artigo](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) para saber mais sobre as revisões de acesso do Azure AD.

O Azure AD Privileged Identity Management (PIM) fornece controles adicionais adaptados para proteger direitos de acesso para recursos, entre o Azure AD, o Azure e outros serviços de nuvem da Microsoft. O Azure AD PIM fornece um conjunto abrangente de controles de governança para ajudar a proteger os recursos da empresa, como diretório, o Office 365 e as funções de recurso do Azure. Assim como acontece com outras formas de acesso, as organizações podem usar revisões de acesso para configurar a recertificação recorrente de acesso para todos os usuários nas funções de administrador. O Azure AD PIM só está disponível na versão E5 do Microsoft 365 Enterprise.

Confira estes artigos para configurar os diferentes tipos de revisões de acesso:

- [Grupos e aplicativos](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Funções do Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Funções de recurso do Azure](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-access-reviews) para esta seção.

## <a name="next-step"></a>Próxima etapa

[Critérios de saída da infraestrutura de identidade](identity-exit-criteria.md)

