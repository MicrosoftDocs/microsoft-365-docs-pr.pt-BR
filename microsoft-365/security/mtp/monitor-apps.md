---
title: Relatórios de monitoramento de & de aplicativos-central de segurança
description: Saiba como obter mais informações sobre o uso do aplicativo na nuvem em sua organização. Inclui diferentes tipos de aplicativos, seu nível de risco e alertas.
keywords: segurança, malware, Microsoft 365, M365, central de segurança, monitor, relatório, aplicativos
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dcb7997c8c248c2b4e7d16902b6ebdd7756ccd0b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846623"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Monitoramento e relatórios de aplicativos no centro de segurança do Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Esses relatórios fornecem mais informações sobre como os aplicativos de nuvem estão sendo usados em sua organização. Inclui diferentes tipos de aplicativos, seu nível de risco e alertas.

## <a name="monitor-email-accounts-at-risk"></a>Monitorar contas de e-mail em risco

A **proteção de email** mostra as contas de email em risco. Você pode selecionar uma conta para investigar ainda mais a central de segurança do Microsoft defender.

![Cartão de proteção de email](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>Monitorar permissões de aplicativo concedidas por usuários

**Cloud app Security-aplicativos OAuth** lista aplicativos descobertos pela Cloud app Security que receberam permissões pelos usuários. O catálogo de riscos do Cloud app Security inclui mais de 16.000 aplicativos que são avaliados usando mais de 70 fatores de risco.

Os fatores de risco são iniciados a partir de informações gerais, como o editor de aplicativos. Em seguida, ele passa para medidas de segurança e controles, como se o aplicativo dá suporte à criptografia em repouso ou fornece um log de auditoria da atividade do usuário.

![Cartão de aplicativos OAuth do Cloud app Security](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>Monitorar contas de usuário do aplicativo na nuvem

**Contas de aplicativo em nuvem para análise** lista contas que podem exigir atenção.

![Contas de aplicativo de nuvem para o cartão de revisão](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>Entender quais aplicativos de nuvem são usados

Os **aplicativos de nuvem descobertos (categorias)** mostram quais tipos de aplicativos estão sendo usados em sua organização. Ele é vinculado ao painel de descoberta de nuvem no Cloud app Security. Para obter mais informações, consulte [QuickStart: work with untected apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).  

![Cartão de categorias de aplicativos de nuvem descoberto](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>Monitorar onde os usuários acessam os aplicativos de nuvem

**Locais de atividade do aplicativo na nuvem** mostram onde os usuários estão acessando aplicativos em nuvem.

![Cartão de locais de atividade do Cloud app](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>Monitorar a integridade das cargas de trabalho da infraestrutura

**Infrastructure Health** mostra alertas de status de integridade para cargas de trabalho de infraestrutura no Azure defender *.

O Azure defender * fornece o gerenciamento de segurança unificado e o defender para Office 365 entre cargas de trabalho locais e em nuvem. Você pode coletar, Pesquisar e analisar dados de segurança de fontes diferentes, incluindo firewalls e outras soluções de parceiros.

Para obter mais informações, consulte a [documentação do Azure defender *](https://docs.microsoft.com/azure/security-center/).

![Cartão de integridade de infraestrutura](../../media/infrastructure-health.png)
