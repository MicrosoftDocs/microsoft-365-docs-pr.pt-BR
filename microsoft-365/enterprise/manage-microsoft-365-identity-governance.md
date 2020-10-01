---
title: Gerenciar o Microsoft 365 Identity Governance
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
description: Saiba como usar os recursos de governança de identidade do Microsoft 365.
ms.openlocfilehash: d5bcafb5b452e693bf3ff706c436a9986eeeae76
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328479"
---
# <a name="manage-microsoft-365-identity-governance"></a>Gerenciar o Microsoft 365 Identity Governance

O controle de identidades é sobre proteção, monitoramento e auditoria do acesso a ativos essenciais enquanto garante a produtividade dos funcionários. Por exemplo, com o controle de identidade, você pode garantir que os usuários certos tenham o acesso apropriado aos recursos necessários e determinar se esse acesso muda com o tempo.

Para obter mais informações, consulte esta [visão geral do controle de identidade do Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).

## <a name="set-up-azure-ad-access-reviews"></a>Configurar revisões de acesso do Azure AD

As revisões do Azure AD Access permitem que você revise o acesso de um usuário para garantir que apenas as pessoas certas tenham acesso contínuo. Por exemplo:

- A medida que um novo funcionárioingressa na sua organização, você precisa garantir que ele tenha o acesso certo para ser produtivo.
- Quando esse funcionário se move para outras equipes, locais ou departamentos, você precisa garantir que o acesso a equipes, locais ou departamentos anteriores sejam removidos conforme necessário.
- Quando esse funcionário ou um convidado deixa sua organização, você precisará garantir que seu acesso seja removido.

Isso é especialmente importante se a sua organização está sujeita a auditorias de segurança para determinar se as contas de usuários têm muito acesso, o que pode resultar em multas se estiverem se violar os regulamentos da região ou do setor.

Para obter mais informações, consulte [visão geral das revisões do Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).

O Azure AD Privileged Identity Management (PIM) fornece controles adicionais adaptados para proteger direitos de acesso para recursos, entre o Azure AD, o Azure e outros serviços de nuvem da Microsoft. O Azure AD PIM fornece um conjunto abrangente de controles de governança para ajudar a proteger os recursos da empresa, como diretório, o Office 365 e as funções de recurso do Azure. Assim como acontece com outras formas de acesso, as organizações podem usar revisões de acesso para configurar a recertificação recorrente de acesso para todos os usuários nas funções de administrador. O Azure AD PIM só está disponível na versão E5 do Microsoft 365 Enterprise.

Confira estes artigos para configurar os diferentes tipos de revisões de acesso:

- [Grupos e aplicativos](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Funções do Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Funções de recurso do Azure](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Configurar o gerenciamento de qualificação do Azure AD

Wiht gerenciamento de direitos do Azure AD, você pode gerenciar o ciclo de vida de identidade e acesso em escala automatizando fluxos de trabalho de solicitação de acesso, atribuições de acesso, revisões e expiração.

Seus funcionários precisam acessar vários grupos, aplicativos e sites para realizar o trabalho. O gerenciamento desse acesso pode ser desafiador porque os requisitos mudam, novos aplicativos são adicionados ou os usuários precisam de direitos de acesso adicionais. Ao colaborar com outras organizações, talvez você não saiba quem, na outra organização, precisa acessar os recursos da sua organização, e os usuários externos não saberão quais aplicativos, grupos ou sites sua organização está usando.

O gerenciamento de direitos do Azure AD pode ajudá-lo a gerenciar com mais eficiência o acesso a grupos, aplicativos e sites do SharePoint para usuários internos e externos.
 
Para obter mais informações, consulte a [visão geral do gerenciamento de qualificação do Azure ad](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).
