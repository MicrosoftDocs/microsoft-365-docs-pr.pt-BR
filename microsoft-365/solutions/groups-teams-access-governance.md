---
title: Controle de acesso em grupos, equipes e SharePoint do Microsoft 365
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Saiba mais sobre como controlar o acesso nos grupos, equipes e SharePoint do Microsoft 365.
ms.openlocfilehash: fb1bec219ef0d27c2a908f5f385185a1a70e01e1
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613461"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Controle de acesso em grupos, equipes e SharePoint do Microsoft 365

Há muitos controles que permitem controlar como as pessoas acessam recursos em grupos, equipes e SharePoint. Revise essas opções e considere como elas são mapeadas para suas necessidades de negócios, a sensibilidade dos seus dados e o escopo das pessoas com as quais os usuários precisam colaborar.

A tabela a seguir fornece uma referência rápida para os controles de acesso disponíveis no Microsoft 365. Mais informações são fornecidas nas seções a seguir.

|Categoria|Descrição|Referência|
|:-------|:----------|:--------|
|Associação|||
||Descoberta de equipes privadas|[Gerenciar a descoberta de equipes privadas no Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||Associação de grupo dinâmico com base em regras|[Criar ou atualizar um grupo dinâmico no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||Controlar quem pode compartilhar arquivos, pastas e sites.|[Configurar e gerenciar solicitações de acesso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Acesso condicional|||
||Autenticação multifator|[Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||Controlar o acesso ao dispositivo com base na confidencialidade de grupo, equipe ou site.|[Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Limitar o acesso ao site para dispositivos não gerenciados.|[Controlar o acesso do SharePoint de dispositivos não gerenciados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||Controlar o acesso ao site com base no local|[Controlar o acesso aos dados do SharePoint Online e do OneDrive com base no local de rede](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|Acesso de convidados|||
||Permitir ou bloquear o compartilhamento do SharePoint de domínios especificados.|[Restringir o compartilhamento de conteúdo do SharePoint e do OneDrive por domínio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||Permitir ou bloquear a associação de grupo ou de equipe de domínios especificados.|[Permitir ou bloquear convites para usuários de B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||Impedir o compartilhamento anônimo.|[Desativar links para Qualquer pessoa](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||Controlar as permissões para links de acesso anônimo.|[Definir permissões de link para links de qualquer pessoa](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||Controlar a expiração de links de compartilhamento anônimos.|[Definir uma data de vencimento para links de Qualquer pessoa](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||Controle o tipo de link de compartilhamento mostrado aos usuários por padrão.|[Alterar o tipo de link padrão para um site](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||Limitar o compartilhamento externo a pessoas específicas.|[Limitar o compartilhamento externo a grupos de segurança especificados](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Controlar o acesso de convidados a um grupo, equipe ou site com base na confidencialidade das informações.|[Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Desative as opções de compartilhamento.|[Limitar o compartilhamento no Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|Gerenciamento de usuários|||
||Revise a associação de grupo e equipe regularmente.|[O que são revisões do Azure AD Access?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||Automatize o gerenciamento de acesso a grupos e equipes.|[O que é gerenciamento de qualificação do AD do Azure?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||Permitir ou impedir que pessoas criem canais privados no Microsoft Teams.|[Gerenciar o ciclo de vida de canais privados no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Associação

A associação de equipes e grupos é controlada por proprietários. Os membros podem convidar outros, mas os convites são enviados aos proprietários para aprovação. Embora equipes e grupos públicos sejam detectáveis por qualquer pessoa na organização, você pode controlar se as equipes e os grupos privados podem ser detectáveis:

- [Gerenciar a descoberta de equipes privadas no Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

Você pode gerenciar a associação de um grupo ou equipe dinamicamente com base em alguns critérios, como departamento. Nesse caso, os membros e proprietários não podem convidar pessoas para a equipe.

- [Criar ou atualizar um grupo dinâmico no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

Os sites do SharePoint oferecem a capacidade de adicionar proprietários, membros e visitantes à associação de grupo ou de equipe. Dependendo dos seus requisitos, convém restringir quem pode convidar pessoas para o site. Além disso, dependendo da sensibilidade das informações em um determinado site, talvez você queira restringir quem pode compartilhar arquivos e pastas. Essas restrições são configuradas pelo proprietário de equipe, grupo ou site:

- [Configurar e gerenciar solicitações de acesso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Acesso condicional

Com o Microsoft 365, você pode exigir a autenticação multifator para ambas as pessoas dentro e fora da sua organização. Há muitas opções para as circunstâncias em que as pessoas são solicitadas por um segundo fator de autenticação. É altamente recomendável implantar a autenticação multifator em sua organização:

- [Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

Se você tiver informações confidenciais em alguns de seus grupos e equipes, poderá aplicar as políticas de gerenciamento de dispositivos com base em um grupo ou em um rótulo de confidencialidade da equipe. Você pode bloquear o acesso totalmente de dispositivos não gerenciados ou permitir acesso limitado, somente Web:

- [Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

No SharePoint, você pode restringir o acesso a sites de locais de rede especificados.

- [Controlar o acesso aos dados do SharePoint Online e do OneDrive com base no local de rede](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


Recursos adicionais:

- [Planejar uma implantação de acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Visão geral do Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [Controlar o acesso do SharePoint de dispositivos não gerenciados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Acesso de convidados

Você pode restringir convidados com base no domínio de seu endereço de email. O SharePoint oferece configurações de restrição de domínio específicas de toda a organização e de site. Grupos e equipes usam as listas de permissões e de negação de domínio no Azure AD. Certifique-se de definir ambas as configurações para evitar o compartilhamento indesejado e garantir uma experiência de usuário consistente:

- [Restringir o compartilhamento de conteúdo do SharePoint e do OneDrive por domínio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [Permitir ou bloquear convites para usuários de B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

O Microsoft 365 permite o compartilhamento anônimo de arquivos e pastas usando links de compartilhamento de *pessoas* . Os links de *qualquer pessoa* podem ser encaminhados e qualquer pessoa com o link pode acessar o item compartilhado. Dependendo da confidencialidade dos seus dados, considere a governança de como os links de *pessoas* são usados, incluindo desativá-los totalmente, restringindo permissões de link para somente leitura ou definindo um tempo de expiração para eles:

- [Desativar links para Qualquer pessoa](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [Definir permissões de link para links de qualquer pessoa](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [Definir uma data de vencimento para links de Qualquer pessoa](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

Ao compartilhar arquivos ou pastas, os usuários têm vários tipos de link para escolher. Para reduzir o risco de compartilhamento inadequado acidental, você pode alterar o tipo de link padrão apresentado aos usuários quando eles compartilham. Por exemplo, alterar o padrão de links de *qualquer pessoa* , que permitem acesso anônimo a *pessoas em seus* links de organização pode reduzir o risco de compartilhamento externo indesejado de informações confidenciais:

- [Alterar o tipo de link padrão para um site](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

Se sua organização tiver dados confidenciais que você precisa compartilhar com convidados, mas estiver preocupado com o compartilhamento inadequado, você poderá limitar o compartilhamento externo de arquivos e pastas aos membros de grupos de segurança especificados. Dessa forma, você pode restringir o compartilhamento externamente a um grupo específico de pessoas ou exigir que seus usuários façam o treinamento sobre o compartilhamento externo apropriado antes de adicioná-los ao grupo de segurança:

- [Limitar o compartilhamento externo a grupos de segurança especificados](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Grupos e equipes têm configuração no nível da organização que permite ou nega acesso de convidado. Embora você possa [restringir o acesso de convidados a equipes ou grupos específicos usando o Microsoft PowerShell](per-group-guest-access.md), é recomendável fazer isso por meio de um rótulo de confidencialidade. Com rótulos de sensibilidade, você pode permitir ou negar automaticamente o acesso de convidados com base no rótulo aplicado:

- [Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

O Microsoft 365 oferece vários métodos diferentes de informações de compartilhamento. Se você tiver informações confidenciais e quiser restringir a forma como elas são compartilhadas, revise as opções para limitar o compartilhamento:

- [Limitar o compartilhamento no Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

Recursos adicionais:

- [Configurar a colaboração segura com o Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [Limitar a exposição acidental a arquivos ao compartilhar arquivos com pessoas de fora da sua organização](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [Criar um ambiente seguro de compartilhamento de convidados](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [Habilitar a colaboração externa B2B e gerenciar quem pode convidar convidados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Gerenciamento de usuários

À medida que os grupos e equipes evoluem em sua organização, uma boa prática é analisar a associação de grupo e equipe regularmente. Isso pode ser especialmente útil para equipes e grupos com uma associação de alteração, as que contêm informações confidenciais ou aquelas que incluem convidados. Considere configurar as revisões do Access para essas equipes e grupos:

- [O que são revisões do Azure AD Access?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Muitas organizações têm parcerias de negócios com outras organizações ou principais fornecedores com os quais eles colaboram em profundidade. O gerenciamento de usuários e o acesso aos recursos podem ser difíceis de gerenciar nesses cenários. Considere a automação de algumas das tarefas de gerenciamento de usuários e até mesmo de fazer a transição de algumas delas para sua organização de parceiros:

- [O que é gerenciamento de qualificação do AD do Azure?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

Os canais privados no Teams permitem conversas com escopo e compartilhamento de arquivos entre um subconjunto de membros da equipe. Dependendo das suas necessidades comerciais específicas, talvez você queira permitir ou bloquear esse recurso.

- [Canais privados no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [Gerenciar o ciclo de vida de canais privados no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

Recursos adicionais:

- [Governança de identidade do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>Tópicos relacionados

[Passo a passo de planejamento de governança de colaboração](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Segurança e conformidade no Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Gerenciar configurações de compartilhamento no SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Criar e gerenciar uma rede externa no Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[Configurar equipes com três camadas de proteção](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
