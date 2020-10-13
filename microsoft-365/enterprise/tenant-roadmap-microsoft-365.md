---
title: Roteiro do locatário para o Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: O roteiro para configurar seus locatários para o Microsoft 365.
ms.openlocfilehash: 0f1fa91bb81fd6cc87820f2b2d48e00e1b75a0c4
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446002"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Roteiro do locatário para o Microsoft 365

O Microsoft 365 locatário é o conjunto de serviços atribuídos à sua organização. Normalmente, esse locatário é associado a um ou mais dos nomes de domínio DNS e atua como um contêiner central para assinaturas diferentes e as licenças dentro delas que você atribui às contas de usuário.

Ao criar um locatário do Microsoft 365, você o atribui a uma localização geográfica específica. Você também pode ter um locatário com vários locais geográficos e mover o locatário de um local para outro.

Para que o seu locatário fique pronto para os serviços fundamentais de rede e identidade, é fundamental planejar e executar cuidadosamente a configuração do locatário.

## <a name="plan"></a>Plano

Para planejar sua implementação de locatário:

- [Entender as assinaturas, as licenças e os locatários do Azure Active Directory (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Entender como usar certificados SSL de terceiros](plan-for-third-party-ssl-certificates.md)
- [Entender as maneiras como um Microsoft 365 locatário é integrado aos serviços do Azure AD](integrated-apps-and-azure-ads.md)
- [Planejar o suporte ao aplicativo cliente](microsoft-365-client-support-certificate-based-authentication.md)
- [Determinar como usar a autenticação moderna híbrida](hybrid-modern-auth-overview.md)
- [Planejar atualizações do Office 2007 e do Office 2010](plan-upgrade-previous-versions-office.md)
- [Entender o isolamento do locatário](microsoft-365-tenant-isolation-overview.md)
- [Obtenha os detalhes sobre o Microsoft 365 Service Assurance](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a>Implantar

Para implantar seu locatário, [adicione os domínios DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) para sua organização e use os [guias de configuração no centro de administração do Microsoft 365](setup-guides-for-microsoft-365.md).

## <a name="tenants-with-multiple-geographic-locations"></a>Locatários com vários locais geográficos

Com o Microsoft 365 Multi-Geo, sua organização pode expandir sua presença no Microsoft 365 para várias regiões geográficas e/ou países do seu locatário existente.

Para obter informações sobre o Microsoft 365 multigeo, incluindo como planejar, configurar e administrar, [comece aqui](microsoft-365-multi-geo.md).

## <a name="move-a-tenants-geographic-locations"></a>Mover os locais geográficos de um locatário

A Microsoft continua a abrir os novos locais geográficos do datacenter (GEOS) para serviços do Microsoft 365. Esses novos datacenters GEOS adicionam capacidade e computam recursos para dar suporte ao crescimento de demanda e uso do cliente. Além disso, o novo GEOS de datacenter oferece residências de dados geográficos para dados essenciais do cliente.

Para obter informações sobre a geografia do Microsoft 365 datacenter, incluindo como solicitar uma movimentação de dados geográfica, [comece aqui](moving-data-to-new-datacenter-geos.md).

## <a name="next-step"></a>Próxima etapa

Inicie o planejamento de locatários com [assinaturas, licenças, contas e locatários](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).

