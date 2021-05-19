---
title: Governando o acesso Microsoft 365 grupos, Teams e SharePoint
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
recommendations: false
description: Saiba mais sobre como reger o acesso Microsoft 365 grupos, Teams e SharePoint.
ms.openlocfilehash: 3e0485813a264fe9042e0de9596ba07e50ef72a3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538142"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Governando o acesso Microsoft 365 grupos, Teams e SharePoint

Há muitos controles que permitem que você governe como as pessoas acessam recursos em grupos, equipes e SharePoint. Revise essas opções e considere como elas mapeiam para suas necessidades de negócios, a sensibilidade de seus dados e o escopo das pessoas com as qual os usuários precisam colaborar.

A tabela a seguir fornece uma referência rápida para os controles de acesso disponíveis no Microsoft 365. Outras informações são fornecidas nas seções a seguir.

|Categoria|Descrição|Referência|
|:-------|:----------|:--------|
|Associação|||
||Descoberta de equipes privadas|[Gerenciar a descoberta de equipes privadas Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)|
||Associação dinâmica de grupo com base em regras|[Criar ou atualizar um grupo dinâmico no Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)|
||Controle quem pode compartilhar arquivos, pastas e sites.|[Configurar e gerenciar solicitações de acesso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Acesso condicional|||
||Autenticação Multifator|[Azure AD Multi-Factor Authentication](/azure/active-directory/authentication/concept-mfa-howitworks)|
||Controlar o acesso ao dispositivo com base na sensibilidade de grupo, equipe ou site.|[Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Limitar o acesso ao site para dispositivos não autorizados.|[Controlar SharePoint acesso de dispositivos não controlados](/sharepoint/control-access-from-unmanaged-devices)|
||Controlar o acesso ao site com base no local|[Controlar o acesso aos dados do SharePoint Online e do OneDrive com base no local de rede](/sharepoint/control-access-based-on-network-location)|
|Acesso de convidados|||
||Permitir ou bloquear SharePoint compartilhamento de domínios especificados.|[Restringir o compartilhamento do SharePoint e do OneDrive por domínio](/sharepoint/restricted-domains-sharing)|
||Permitir ou bloquear a associação de equipe ou grupo de domínios especificados.|[Permitir ou bloquear convites para usuários B2B de organizações específicas](/azure/active-directory/b2b/allow-deny-list)|
||Impedir o compartilhamento anônimo.|[Desativar links para Qualquer pessoa](./share-limit-accidental-exposure.md#turn-off-anyone-links)|
||Controle as permissões para links de acesso anônimo.|[Definir permissões de link para links de qualquer pessoa](./best-practices-anonymous-sharing.md#set-link-permissions)|
||Controlar a expiração de links de compartilhamento anônimos.|[Definir uma data de vencimento para links de Qualquer pessoa](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)|
||Controlar o tipo de link de compartilhamento mostrado aos usuários por padrão.|[Alterar o tipo de link padrão para um site](/sharepoint/change-default-sharing-link)|
||Limite o compartilhamento externo a pessoas específicas.|[Limitar o compartilhamento externo a grupos de segurança especificados](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Controlar o acesso de convidados a um grupo, equipe ou site com base na sensibilidade de informações.|[Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Desativar opções de compartilhamento.|[Limitar o compartilhamento no Microsoft 365](./microsoft-365-limit-sharing.md)|
|Gerenciamento de usuários|||
||Revise a associação de equipe e grupo regularmente.|[O que são avaliações de acesso do Azure AD?](/azure/active-directory/governance/access-reviews-overview)|
||Automatizar o gerenciamento de acesso a grupos e equipes.|[O que é o gerenciamento de direitos do Azure AD?](/azure/active-directory/governance/entitlement-management-overview)|
||Permitir ou bloquear a criação de canais privados Teams.|[Gerenciar o ciclo de vida de canais privados no Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Associação

A associação de equipes e grupos é controlada por proprietários. Os membros podem convidar outras pessoas, mas os convites são enviados aos proprietários para aprovação. Embora equipes e grupos públicos sejam descobertos por qualquer pessoa na organização, você pode controlar se equipes privadas e grupos podem ser descobertos:

- [Gerenciar a descoberta de equipes privadas Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)

Você pode gerenciar a associação de um grupo ou equipe dinamicamente com base em alguns critérios, como departamento. Nesse caso, membros e proprietários não podem convidar pessoas para a equipe. Os grupos dinâmicos usam metadados que você define Azure Active Directory para controlar quem é membro do grupo. Certifique-se de que os metadados que você está usando estão completos e atualizados, pois metadados incorretos podem levar os usuários a serem deixados de fora de grupos ou usuários incorretos sendo adicionados.

- [Criar ou atualizar um grupo dinâmico no Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint sites fornecem a capacidade de adicionar proprietários, membros e visitantes além da associação de grupo ou equipe. Dependendo de seus requisitos, talvez você queira restringir quem pode convidar pessoas para o site. Além disso, dependendo da sensibilidade das informações em um determinado site, talvez você queira restringir quem pode compartilhar arquivos e pastas. Essas restrições são configuradas pela equipe, grupo ou proprietário do site:

- [Configurar e gerenciar solicitações de acesso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Acesso condicional

Com Microsoft 365, você pode exigir autenticação multifa factor para pessoas dentro e fora da sua organização. Há muitas opções para as circunstâncias em que as pessoas são solicitados a solicitar um segundo fator de autenticação. É altamente recomendável implantar a autenticação multifa factor para sua organização:

- [Azure AD Multi-Factor Authentication](/azure/active-directory/authentication/concept-mfa-howitworks)

Se você tiver informações confidenciais em alguns de seus grupos e equipes, poderá impor políticas de gerenciamento de dispositivos com base em um grupo ou rótulo de sensibilidade da equipe. Você pode bloquear o acesso inteiramente de dispositivos não autorizados ou permitir acesso limitado somente à Web:

- [Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)

Em SharePoint, você pode restringir o acesso a sites de locais de rede especificados.

- [Controlar o acesso aos dados do SharePoint Online e do OneDrive com base no local de rede](/sharepoint/control-access-based-on-network-location)


Recursos adicionais:

- [Planejar uma implantação de Acesso Condicional](/azure/active-directory/conditional-access/plan-conditional-access)

- [Microsoft Intune visão geral](/mem/intune/fundamentals/what-is-intune)

- [Controlar SharePoint acesso de dispositivos não controlados](/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Acesso de convidados

Você pode restringir convidados com base no domínio de seu endereço de email. SharePoint oferece configurações de restrição de domínio específicas para toda a organização e do site. Grupos e Teams usam as listas de autorização e negação de domínio no Azure AD. Configure ambas as configurações para evitar o compartilhamento indesejado e garantir uma experiência de usuário consistente:

- [Restringir o compartilhamento do SharePoint e do OneDrive por domínio](/sharepoint/restricted-domains-sharing)

- [Permitir ou bloquear convites para usuários B2B de organizações específicas](/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 permite o compartilhamento anônimo de arquivos e pastas usando links *de compartilhamento de* qualquer pessoa. *Os* links de qualquer pessoa podem ser encaminhados e qualquer pessoa com o link pode acessar o item compartilhado. Dependendo da sensibilidade de seus dados, considere o controle sobre como os *links* de Qualquer Pessoa são usados , incluindo a reação total, a restrição de permissões de link para somente leitura ou a definição de um tempo de expiração para eles:

- [Desativar links para Qualquer pessoa](./share-limit-accidental-exposure.md#turn-off-anyone-links)

- [Definir permissões de link para links de qualquer pessoa](./best-practices-anonymous-sharing.md#set-link-permissions)

- [Definir uma data de vencimento para links de Qualquer pessoa](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)

Ao compartilhar arquivos ou pastas, os usuários têm vários tipos de link para escolher. Para reduzir o risco de compartilhamento inadequado acidental, você pode alterar o tipo de link padrão apresentado aos usuários quando eles compartilham. Por exemplo, alterar o padrão de *links* de Qualquer pessoa - que permitem acesso anônimo - para pessoas em sua organização *links* pode reduzir o risco de compartilhamento externo indesejado de informações confidenciais:

- [Alterar o tipo de link padrão para um site](/sharepoint/change-default-sharing-link)

Se sua organização tiver dados confidenciais que você precisa compartilhar com convidados, mas estiver preocupado com o compartilhamento inadequado, poderá limitar o compartilhamento externo de arquivos e pastas aos membros de grupos de segurança especificados. Dessa forma, você pode restringir o compartilhamento externo a um grupo específico de pessoas ou exigir que os usuários adotem treinamentos sobre o compartilhamento externo apropriado antes de adi adiá-los ao grupo de segurança:

- [Limitar o compartilhamento externo a grupos de segurança especificados](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Grupos e Teams têm configurações no nível da organização que permitem ou negam o acesso de convidados. Embora você possa restringir o acesso de convidados a equipes ou grupos específicos usando o [Microsoft PowerShell,](per-group-guest-access.md)recomendamos fazer isso por meio de um rótulo de sensibilidade. Com rótulos de sensibilidade, você pode permitir ou negar automaticamente o acesso de convidados com base no rótulo aplicado:

- [Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)

Em um ambiente em que você frequentemente convida convidados para grupos e equipes, considere configurar avaliações de acesso de convidados agendadas regularmente. Os proprietários podem ser solicitados a revisar convidados em seus grupos e equipes e aprovar ou negar o acesso.

- [Acesso de convidado com revisões de acesso](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

Microsoft 365 oferece muitos métodos diferentes de compartilhamento de informações. Se você tiver informações confidenciais e quiser restringir como ela é compartilhada, revise as opções para limitar o compartilhamento:

- [Limitar o compartilhamento no Microsoft 365](./microsoft-365-limit-sharing.md)

Recursos adicionais:

- [Configurar a colaboração segura com o Microsoft 365](./setup-secure-collaboration-with-teams.md)

- [Práticas recomendadas para compartilhar arquivos e pastas com usuários não autenticados](./best-practices-anonymous-sharing.md)

- [Limitar a exposição acidental a arquivos ao compartilhar arquivos com pessoas de fora da sua organização](./share-limit-accidental-exposure.md)

- [Criar um ambiente de compartilhamento de convidados seguro](./create-secure-guest-sharing-environment.md)

- [Habilite a colaboração externa B2B e gerencie quem pode convidar pessoas](/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Gerenciamento de usuários

À medida que grupos e equipes evoluem em sua organização, uma boa prática é revisar a associação de equipe e grupo regularmente. Isso pode ser particularmente útil para equipes e grupos com uma associação em mudança, aquelas que contêm informações confidenciais ou aquelas que incluem convidados. Considere configurar avaliações de acesso para essas equipes e grupos:

- [O que são avaliações de acesso do Azure AD?](/azure/active-directory/governance/access-reviews-overview)

Muitas organizações têm parcerias comerciais com outras organizações ou fornecedores importantes com os quais colaboram detalhadamente. O gerenciamento de usuários e o acesso a recursos podem ser difíceis de gerenciar nesses cenários. Considere automatizar algumas das tarefas de gerenciamento do usuário e até mesmo fazer a transição de algumas delas para sua organização parceira:

- [O que é o gerenciamento de direitos do Azure AD?](/azure/active-directory/governance/entitlement-management-overview)

Canais privados em Teams permitem conversas com escopo e compartilhamento de arquivos entre um subconjunto de membros da equipe. Dependendo de suas necessidades comerciais específicas, talvez você queira permitir ou bloquear esse recurso.

- [Canais privados no Microsoft Teams](/MicrosoftTeams/private-channels)

- [Gerenciar o ciclo de vida de canais privados no Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)

Recursos adicionais:

- [Azure Active Directory Governança de Identidade](/azure/active-directory/governance)

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Segurança e conformidade no Microsoft Teams](/microsoftteams/security-compliance-overview)

[Gerenciar configurações de compartilhamento em SharePoint](/sharepoint/turn-external-sharing-on-or-off)

[Criar e gerenciar uma rede externa no Yammer](/yammer/work-with-external-users/create-and-manage-an-external-network)

[Configure o Teams com três camadas de proteção](./configure-teams-three-tiers-protection.md)