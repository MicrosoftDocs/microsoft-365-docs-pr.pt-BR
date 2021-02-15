---
title: Governing access in Microsoft 365 groups, Teams, and SharePoint
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
description: Saiba mais sobre como reger o acesso em grupos do Microsoft 365, Teams e SharePoint.
ms.openlocfilehash: fb1bec219ef0d27c2a908f5f385185a1a70e01e1
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613461"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Governing access in Microsoft 365 groups, Teams, and SharePoint

Há muitos controles que permitem que você controle como as pessoas acessam recursos em grupos, equipes e SharePoint. Revise essas opções e considere como elas são mapeáveis para suas necessidades de negócios, a sensibilidade de seus dados e o escopo das pessoas com as qual seus usuários precisam colaborar.

A tabela a seguir fornece uma referência rápida para os controles de acesso disponíveis no Microsoft 365. Outras informações são fornecidas nas seções a seguir.

|Categoria|Descrição|Referência|
|:-------|:----------|:--------|
|Associação|||
||Descoberta de equipes privadas|[Gerenciar a descoberta de equipes privadas no Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||Associação de grupo dinâmico com base em regras|[Criar ou atualizar um grupo dinâmico no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||Controlar quem pode compartilhar arquivos, pastas e sites.|[Configurar e gerenciar solicitações de acesso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Acesso condicional|||
||Autenticação multifa factor|[Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||Controlar o acesso do dispositivo com base na sensibilidade de grupo, equipe ou site.|[Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Limitar o acesso ao site para dispositivos não autorizados.|[Controlar o acesso do SharePoint de dispositivos não controlados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||Controlar o acesso ao site com base no local|[Controlar o acesso aos dados do SharePoint Online e do OneDrive com base no local de rede](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|Acesso de convidados|||
||Permitir ou bloquear o compartilhamento do SharePoint de domínios especificados.|[Restringir o compartilhamento de conteúdo do SharePoint e do OneDrive por domínio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||Permitir ou bloquear a associação de equipe ou grupo de domínios especificados.|[Permitir ou bloquear convites para usuários B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||Impedir o compartilhamento anônimo.|[Desativar links para Qualquer pessoa](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||Controlar as permissões para links de acesso anônimo.|[Definir permissões de link para links para Qualquer pessoa](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||Controlar a expiração de links de compartilhamento anônimos.|[Definir uma data de vencimento para links de Qualquer pessoa](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||Controlar o tipo de link de compartilhamento mostrado aos usuários por padrão.|[Alterar o tipo de link padrão para um site](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||Limitar o compartilhamento externo a pessoas específicas.|[Limitar o compartilhamento externo a grupos de segurança especificados](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Controlar o acesso de convidados a um grupo, equipe ou site com base na sensibilidade das informações.|[Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Desativar opções de compartilhamento.|[Limitar o compartilhamento no Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|Gerenciamento de usuários|||
||Revise a associação de equipe e grupo regularmente.|[O que são revisões de acesso do Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||Automatizar o gerenciamento de acesso a grupos e equipes.|[O que é o gerenciamento de direitos do Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||Permitir ou impedir que as pessoas criar canais privados no Teams.|[Gerenciar o ciclo de vida de canais privados no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Associação

A associação de equipes e grupos é controlada por proprietários. Os membros podem convidar outras pessoas, mas os convites são enviados aos proprietários para aprovação. Embora equipes e grupos públicos possam ser descobertos por qualquer pessoa na organização, você pode controlar se equipes e grupos privados podem ser descobertos:

- [Gerenciar a descoberta de equipes privadas no Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

Você pode gerenciar a associação de um grupo ou equipe dinamicamente com base em alguns critérios, como departamento. Nesse caso, os membros e proprietários não podem convidar pessoas para a equipe.

- [Criar ou atualizar um grupo dinâmico no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

Os sites do SharePoint oferecem a capacidade de adicionar proprietários, membros e visitantes além da associação a grupos ou equipes. Dependendo de seus requisitos, talvez você queira restringir quem pode convidar pessoas para o site. Além disso, dependendo da sensibilidade das informações em um determinado site, talvez você queira restringir quem pode compartilhar arquivos e pastas. Essas restrições são configuradas pela equipe, grupo ou proprietário do site:

- [Configurar e gerenciar solicitações de acesso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Acesso condicional

Com o Microsoft 365, você pode exigir autenticação multifafa para pessoas dentro e fora da sua organização. Há muitas opções para as circunstâncias em que as pessoas são solicitados a solicitar um segundo fator de autenticação. É altamente recomendável que você implante a autenticação multifa factor para sua organização:

- [Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

Se você tiver informações confidenciais em alguns de seus grupos e equipes, poderá impor políticas de gerenciamento de dispositivos com base em um grupo ou rótulo de sensibilidade da equipe. Você pode bloquear o acesso inteiramente de dispositivos não-autorizados ou permitir acesso limitado somente à Web:

- [Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

No SharePoint, você pode restringir o acesso a sites de locais de rede especificados.

- [Controlar o acesso aos dados do SharePoint Online e do OneDrive com base no local de rede](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


Recursos adicionais:

- [Planejar uma implantação de Acesso Condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Visão geral do Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [Controlar o acesso do SharePoint de dispositivos não controlados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Acesso de convidados

Você pode restringir convidados com base no domínio de seus endereços de email. O SharePoint oferece configurações de restrição de domínio específicas do site e da organização. Grupos e Equipes usam as listas de autorização e negação de domínio no Azure AD. Certifique-se de definir as duas configurações para evitar o compartilhamento indesejado e garantir uma experiência de usuário consistente:

- [Restringir o compartilhamento de conteúdo do SharePoint e do OneDrive por domínio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [Permitir ou bloquear convites para usuários B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

O Microsoft 365 permite o compartilhamento anônimo de arquivos e pastas usando links *de compartilhamento* de Qualquer pessoa. *Os* links de qualquer pessoa podem ser encaminhados e qualquer pessoa com o link pode acessar o item compartilhado. Dependendo da sensibilidade dos seus dados, considere a governança de como os *links* de Qualquer pessoa são usados, incluindo a sua reação total, a restrição de permissões de link para somente leitura ou a definição de um tempo de expiração para eles:

- [Desativar links para Qualquer pessoa](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [Definir permissões de link para links para Qualquer pessoa](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [Definir uma data de vencimento para links de Qualquer pessoa](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

Ao compartilhar arquivos ou pastas, os usuários têm vários tipos de link para escolher. Para reduzir o risco de compartilhamento inadequado acidental, você pode alterar o tipo de link padrão apresentado aos usuários quando eles compartilham. Por exemplo, alterar o padrão de *links* de Qualquer Pessoa , que permitem acesso anônimo – para *links* de pessoas em sua organização pode reduzir o risco de compartilhamento externo indesejado de informações confidenciais:

- [Alterar o tipo de link padrão para um site](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

Se sua organização tiver dados confidenciais que você precisa compartilhar com convidados, mas estiver preocupado com o compartilhamento inadequado, poderá limitar o compartilhamento externo de arquivos e pastas aos membros de grupos de segurança especificados. Dessa forma, você pode restringir o compartilhamento externamente a um grupo específico de pessoas ou exigir que seus usuários adotem treinamento sobre o compartilhamento externo apropriado antes de adições ao grupo de segurança:

- [Limitar o compartilhamento externo a grupos de segurança especificados](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Grupos e Equipes têm configurações no nível da organização que permitem ou negam o acesso de convidados. Embora você possa restringir o acesso de convidados a equipes ou grupos específicos usando o [Microsoft PowerShell,](per-group-guest-access.md)recomendamos fazer isso por meio de um rótulo de sensibilidade. Com os rótulos de sensibilidade, você pode permitir ou negar automaticamente o acesso de convidados com base no rótulo aplicado:

- [Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

O Microsoft 365 oferece muitos métodos diferentes de compartilhamento de informações. Se você tiver informações confidenciais e quiser restringir como são compartilhadas, revise as opções para limitar o compartilhamento:

- [Limitar o compartilhamento no Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

Recursos adicionais:

- [Configure a colaboração segura com o Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [Limitar a exposição acidental a arquivos ao compartilhar arquivos com pessoas de fora da sua organização](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [Criar um ambiente seguro de compartilhamento de convidados](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [Habilitar a colaboração externa B2B e gerenciar quem pode convidar convidados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Gerenciamento de usuários

À medida que grupos e equipes evoluem em sua organização, uma boa prática é revisar a associação de equipes e grupos regularmente. Isso pode ser particularmente útil para equipes e grupos com uma associação em mudança, aquelas que contêm informações confidenciais ou aquelas que incluem convidados. Considere configurar revisões de acesso para essas equipes e grupos:

- [O que são revisões de acesso do Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Muitas organizações têm parcerias comerciais com outras organizações ou fornecedores importantes com os quais colaboram em detalhes. O gerenciamento de usuários e o acesso a recursos podem ser difíceis de gerenciar nesses cenários. Considere automatizar algumas das tarefas de gerenciamento de usuários e até mesmo fazer a transição de algumas delas para sua organização de parceiro:

- [O que é o gerenciamento de direitos do Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

Os canais privados no Teams permitem conversas com escopo e compartilhamento de arquivos entre um subconjunto de membros da equipe. Dependendo de suas necessidades comerciais específicas, talvez você queira permitir ou bloquear esse recurso.

- [Canais privados no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [Gerenciar o ciclo de vida de canais privados no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

Recursos adicionais:

- [Governança de Identidade do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Segurança e conformidade no Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Gerenciar configurações de compartilhamento no SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Criar e gerenciar uma rede externa no Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[Configure equipes com três níveis de proteção](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
