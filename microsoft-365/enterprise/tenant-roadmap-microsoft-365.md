---
title: Mapa de locatários do Microsoft 365
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
ms.openlocfilehash: d2640a036eedda0b0962a15a03dcf0211ea0209b
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948392"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Mapa de locatários do Microsoft 365

Seu locatário do Microsoft 365 é o conjunto de serviços atribuídos à sua organização. Normalmente, esse locatário é associado a um ou mais dos seus nomes de domínio DNS públicos e atua como um contêiner central e isolado para assinaturas diferentes e as licenças dentro deles que você atribui a contas de usuário. Para saber mais, confira [Assinaturas, licenças, contas e locatários para ofertas de nuvem da Microsoft.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)

Ao criar um locatário do Microsoft 365, você o atribui a uma localização geográfica específica. Você também pode ter um locatário com várias localizações geográficas e mover seu locatário de um local para outro.

Para preparar seu locatário para usuários, grupos, licenças e aplicativos de nuvem, é fundamental planejar e executar cuidadosamente a configuração do locatário.

## <a name="set-up-your-microsoft-365-tenant"></a>Configurar seu locatário do Microsoft 365

Depois de garantir que sua rede seja otimizada para acessar o Microsoft 365 para funcionários locais e remotos, suas próximas grandes tarefas estão planejando e configurando seu locatário do Microsoft 365 para nomes de domínio DNS, serviços comuns e para essa infraestrutura de identidade que dá suporte à entrada segura do usuário.

### <a name="plan"></a>Planejar

Para planejar a implementação do locatário:

- [Compreender assinaturas, licenças e locatários do Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Entender como usar certificados SSL de terceiros](plan-for-third-party-ssl-certificates.md)
- [Entenda como um locatário do Microsoft 365 é integrado aos serviços do Azure AD](integrated-apps-and-azure-ads.md)
- [Planejar o suporte ao aplicativo cliente](microsoft-365-client-support-certificate-based-authentication.md)
- [Determinar como usar a autenticação moderna híbrida](hybrid-modern-auth-overview.md)
- [Planejar atualizações do Office 2007 e do Office 2010](plan-upgrade-previous-versions-office.md)
- [Compreender o isolamento do locatário](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>Implantar

Para implantar seu locatário: 

- Adicione os [domínios DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) para sua organização.
- Use os [guias de configuração no centro de administração do Microsoft 365.](setup-guides-for-microsoft-365.md)
- Crie sua [infraestrutura de identidade e](identity-roadmap-microsoft-365.md) proteja suas [ins loções de usuário.](microsoft-365-secure-sign-in.md)

### <a name="move-a-tenants-geographic-locations"></a>Mover as localizações geográficas de um locatário

A Microsoft continua a abrir novas localizações geográficas do datacenter (geos) para os serviços do Microsoft 365. Essas novas áreas geográficas de datacenter adicionam capacidade e recursos de computação para dar suporte à demanda do cliente e ao crescimento do uso. Além disso, as novas áreas geográficas do datacenter oferecem residência de dados na área geográfica para dados principais do cliente.

Para saber mais, confira Movendo os dados principais para a nova área geográfica do [datacenter do Microsoft 365.](moving-data-to-new-datacenter-geos.md)


## <a name="deploy-microsoft-365-multi-geo"></a>Implantar o Microsoft 365 Multi-Geo

Com o Microsoft 365 Multi-Geo, sua organização pode expandir sua presença no Microsoft 365 para várias regiões geográficas e/ou países do seu locatário existente.

Para mais informações, consulte [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenants"></a>Gerenciar vários locatários do Microsoft 365 

Embora ter um único locatário para sua organização seja ideal, você pode ser uma das muitas organizações que têm vários locatários. Os motivos podem incluir fusões e aquisições, você quer isolamento administrativo ou tem uma TI descentralizada.

Se você tiver vários locatários do Microsoft 365, confira estes artigos para obter mais informações sobre:

- [Colaboração entre locatários](microsoft-365-inter-tenant-collaboration.md)
- [Migração de caixa de correio entre locatários](cross-tenant-mailbox-migration.md)
- [Migrações de locatário-para-locatário](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Próxima etapa

Inicie o planejamento de [locatários com assinaturas, licenças, contas e locatários.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
