---
title: Gerenciar a governança de identidade do Microsoft 365
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
ms.openlocfilehash: 6a97ca24c609724a2cab93feec9e90f25d3361e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910949"
---
# <a name="manage-microsoft-365-identity-governance"></a>Gerenciar a governança de identidade do Microsoft 365

O controle de identidades é sobre proteção, monitoramento e auditoria do acesso a ativos essenciais enquanto garante a produtividade dos funcionários. Por exemplo, com o controle de identidade, você pode garantir que os usuários certos tenham o acesso apropriado aos recursos necessários e determinar se esse acesso muda com o tempo.

Para obter mais informações, consulte esta visão geral da governança de [identidade do Azure Active Directory (Azure AD)](/azure/active-directory/governance/identity-governance-overview).

## <a name="set-up-azure-ad-access-reviews"></a>Configurar revisões de acesso do Azure AD

As análises de acesso ao Azure AD permitem que você revise o acesso de um usuário para garantir que apenas as pessoas certas tenham acesso contínuo. Por exemplo:

- A medida que um novo funcionárioingressa na sua organização, você precisa garantir que ele tenha o acesso certo para ser produtivo.
- Quando esse funcionário se move para outras equipes, locais ou departamentos, você precisa garantir que o acesso a equipes, locais ou departamentos anteriores sejam removidos conforme necessário.
- Quando esse funcionário ou um convidado deixa sua organização, você precisará garantir que seu acesso seja removido.

Isso é especialmente importante se a sua organização está sujeita a auditorias de segurança para determinar se as contas de usuários têm muito acesso, o que pode resultar em multas se estiverem se violar os regulamentos da região ou do setor.

Para obter mais informações, consulte a [visão geral das avaliações de acesso.](/azure/active-directory/governance/access-reviews-overview)

Confira estes artigos para configurar os diferentes tipos de revisões de acesso:

- [Grupos e aplicativos](/azure/active-directory/governance/create-access-review)
- [Funções do Microsoft Azure Active Directory](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Funções de recurso do Azure](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Configurar o gerenciamento de direitos do Azure AD

Gerenciamento de direitos do Wiht Azure AD, você pode gerenciar a identidade e o ciclo de vida de acesso em escala automatizando fluxos de trabalho de solicitação de acesso, atribuições de acesso, análises e expiração.

Seus funcionários precisam de acesso a vários grupos, aplicativos e sites para executar seu trabalho. Gerenciar esse acesso pode ser um desafio porque os requisitos mudam, novos aplicativos são adicionados ou os usuários precisam de direitos de acesso adicionais. Quando você colabora com outras organizações, talvez não saiba quem na outra organização precisa de acesso aos recursos da sua organização, e usuários externos não saberão quais aplicativos, grupos ou sites sua organização está usando.

O gerenciamento de direitos do Azure AD pode ajudá-lo a gerenciar com mais eficiência o acesso a grupos, aplicativos e sites do SharePoint para usuários internos e externos.
 
Para obter mais informações, consulte a visão geral do gerenciamento de direitos do [Azure AD.](/azure/active-directory/governance/entitlement-management-overview)