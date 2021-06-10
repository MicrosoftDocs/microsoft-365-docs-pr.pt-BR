---
title: Roteiro de locatário para Microsoft 365
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
description: O roteiro para configurar seus locatários para Microsoft 365.
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909449"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Roteiro de locatário para Microsoft 365

Seu Microsoft 365 locatário é o conjunto de serviços atribuídos à sua organização. Normalmente, esse locatário está associado a um ou mais nomes de domínio DNS públicos e age como um contêiner central e isolado para assinaturas diferentes e as licenças dentro delas que você atribui a contas de usuário. Para obter mais informações, consulte [Assinaturas, licenças, contas e locatários para ofertas de nuvem da Microsoft.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)

Ao criar um Microsoft 365 locatário, atribua-o a uma localização geográfica específica. Você também pode ter um locatário com várias localizações geográficas e mover seu locatário de um local para outro.

Para preparar seu locatário para usuários, grupos, licenças e aplicativos de nuvem, é fundamental planejar e executar cuidadosamente a configuração do locatário.

## <a name="set-up-your-microsoft-365-tenant"></a>Configure o locatário do Microsoft 365.

Depois de garantir que sua rede seja otimizada para acesso ao Microsoft 365 para funcionários locais e remotos, suas próximas grandes tarefas estão planejando e configurando seu locatário do Microsoft 365 para nomes de domínio DNS, serviços comuns e para essa infraestrutura de identidade que dá suporte à entrada segura do usuário.

### <a name="plan"></a>Plano

Para planejar a implementação do locatário:

- [Compreender assinaturas, licenças e locatários Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Entender como usar certificados SSL de terceiros](plan-for-third-party-ssl-certificates.md)
- [Entenda como um locatário Microsoft 365 está integrado aos serviços do Azure AD](integrated-apps-and-azure-ads.md)
- [Planejar o suporte ao aplicativo cliente](microsoft-365-client-support-certificate-based-authentication.md)
- [Determinar como usar a autenticação moderna híbrida](hybrid-modern-auth-overview.md)
- [Planejar as Office 2007 e Office 2010](plan-upgrade-previous-versions-office.md)
- [Compreender o isolamento de locatários](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>Implantar

Para implantar seu locatário: 

- Adicione os [domínios DNS](../admin/setup/add-domain.md) para sua organização.
- Use as [guias de instalação no Microsoft 365 de administração](setup-guides-for-microsoft-365.md).
- Crie sua infraestrutura [de identidade e](identity-roadmap-microsoft-365.md) proteja suas [insuportações do usuário.](microsoft-365-secure-sign-in.md)

### <a name="move-a-tenants-geographic-locations"></a>Mover locais geográficos de um locatário

A Microsoft continua a abrir novas localizações geográficas do datacenter (geos) para Microsoft 365 serviços. Esses novos geos do datacenter adicionam capacidade e recursos de computação para dar suporte à demanda do cliente e ao crescimento do uso. Além disso, os novos geos do datacenter oferecem residência de dados no geo para dados principais do cliente.

Para obter mais informações, consulte [Movendo os dados principais para novas Microsoft 365 de datacenter](moving-data-to-new-datacenter-geos.md).


## <a name="deploy-microsoft-365-multi-geo"></a>Implantar Microsoft 365 multi-geo

Com o Microsoft 365 Multi-Geo, sua organização pode expandir sua presença no Microsoft 365 para várias regiões geográficas e/ou países do seu locatário existente.

Para mais informações, consulte [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).

## <a name="manage-multiple-microsoft-365-tenants"></a>Gerenciar vários Microsoft 365 locatários 

Embora ter um único locatário para sua oganização seja ideal, você pode ser uma das muitas organizações que têm vários locatários. Os motivos podem incluir fusões e aquisições, você deseja isolamento administrativo ou ter uma TI descentralizada.

Se você tiver vários Microsoft 365 locatários, confira estes artigos para obter mais informações sobre:

- [Colaboração entre locatários](microsoft-365-inter-tenant-collaboration.md)
- [Migração de caixa de correio entre locatários](cross-tenant-mailbox-migration.md)
- [Migrações de locatário-para-locatário](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Próxima etapa

Inicie o planejamento de [locatários com Assinaturas, licenças, contas e locatários.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)