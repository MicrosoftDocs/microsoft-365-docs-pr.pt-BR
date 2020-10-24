---
title: Roteiro do locatário para o Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: O roteiro para configurar seus locatários para o Microsoft 365.
ms.openlocfilehash: 038d9b0d94b84d184f0d9d9b250d0ee4d2c19de9
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753961"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Roteiro do locatário para o Microsoft 365

O Microsoft 365 locatário é o conjunto de serviços atribuídos à sua organização. Normalmente, esse locatário é associado a um ou mais nomes de domínio DNS públicos e atua como um contêiner central e isolado para assinaturas diferentes e as licenças dentro delas que você atribui às contas de usuário. Para obter mais informações, consulte [assinaturas, licenças, contas e locatários para ofertas de nuvem da Microsoft](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).

Ao criar um locatário do Microsoft 365, você o atribui a uma localização geográfica específica. Você também pode ter um locatário com vários locais geográficos e mover o locatário de um local para outro.

Para preparar o locatário para usuários, grupos, licenças e aplicativos de nuvem, é fundamental planejar e executar cuidadosamente a configuração do locatário.

## <a name="set-up-your-microsoft-365-tenant"></a>Configurar seu locatário do Microsoft 365

Após garantir que sua rede seja otimizada para acessar o Microsoft 365 para os funcionários remotos e locais, suas próximas tarefas grandes estão planejando e, em seguida, configurando o Microsoft 365 locatário para nomes de domínio DNS, serviços comuns e para essa infraestrutura de identidade que oferece suporte à entrada de usuário segura.

### <a name="plan"></a>Plano

Para planejar sua implementação de locatário:

- [Entender as assinaturas, as licenças e os locatários do Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Entender como usar certificados SSL de terceiros](plan-for-third-party-ssl-certificates.md)
- [Entender as maneiras como um Microsoft 365 locatário é integrado aos serviços do Azure AD](integrated-apps-and-azure-ads.md)
- [Planejar o suporte ao aplicativo cliente](microsoft-365-client-support-certificate-based-authentication.md)
- [Determinar como usar a autenticação moderna híbrida](hybrid-modern-auth-overview.md)
- [Planejar atualizações do Office 2007 e do Office 2010](plan-upgrade-previous-versions-office.md)
- [Entender o isolamento do locatário](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>Implantar

Para implantar seu locatário: 

- Adicione os [domínios DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) para sua organização.
- Use os [guias de configuração no centro de administração do Microsoft 365](setup-guides-for-microsoft-365.md).
- Crie sua [infraestrutura de identidade](identity-roadmap-microsoft-365.md) e [proteja suas entradas de usuário](microsoft-365-secure-sign-in.md).

### <a name="move-a-tenants-geographic-locations"></a>Mover os locais geográficos de um locatário

A Microsoft continua a abrir os novos locais geográficos do datacenter (GEOS) para serviços do Microsoft 365. Esses novos datacenters GEOS adicionam capacidade e computam recursos para dar suporte ao crescimento de demanda e uso do cliente. Além disso, o novo GEOS de datacenter oferece residências de dados geográficos para dados essenciais do cliente.

Para obter mais informações, consulte [movendo dados principais para o novo Microsoft 365 datacenter GEOS](moving-data-to-new-datacenter-geos.md).


## <a name="deploy-microsoft-365-multi-geo"></a>Implantar o Microsoft 365 multigeográfico

Com o Microsoft 365 Multi-Geo, sua organização pode expandir sua presença no Microsoft 365 para várias regiões geográficas e/ou países do seu locatário existente.

Para obter mais informações, consulte [Microsoft 365 multigeo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenant"></a>Gerenciar vários Microsoft 365 locatário 

Embora ter um único locatário para o seu oganization seja ideal, você pode ser uma das muitas organizações que têm vários locatários. Os motivos podem incluir fusões e aquisições, você deseja o isolamento administrativo ou ter um recurso descentralizado.

Se você tiver vários locatários do Microsoft 365, consulte estes artigos para obter mais informações sobre:

- [Colaboração entre locatários](microsoft-365-inter-tenant-collaboration.md)
- [Migração de caixa de correio entre locatários](cross-tenant-mailbox-migration.md)
- [Migrações de locatário-para-locatário](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Próxima etapa

Inicie o planejamento de locatários com [assinaturas, licenças, contas e locatários](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).
