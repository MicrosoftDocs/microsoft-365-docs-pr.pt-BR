---
title: Monitoramento e relatórios de aplicativos no centro de segurança do Microsoft 365
description: Descreve como você pode obter mais informações sobre o uso do aplicativo na nuvem em sua organização
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
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: f0f436e2b4e9a26f10ec134718796624c9496e81
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600148"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Monitoramento e relatórios de aplicativos no centro de segurança do Microsoft 365

Esses relatórios fornecem mais informações sobre como os aplicativos de nuvem estão sendo usados na sua organização, incluindo os tipos de aplicativos, seu nível de risco e alertas.

## <a name="monitor-email-accounts-at-risk"></a>Monitorar contas de email em risco

A **proteção de email** mostra as contas de email em risco. Você pode clicar em uma conta para investigar ainda mais a central de segurança do Microsoft defender.

![Cartão de proteção de email](../images/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>Monitorar permissões de aplicativo concedidas por usuários

**Cloud app Security-aplicativos OAuth** lista aplicativos descobertos pela Cloud app Security que receberam permissões pelos usuários. O catálogo de riscos do Cloud app Security inclui mais de 16.000 aplicativos que são avaliados usando mais de 70 fatores de risco.

Os fatores de risco são iniciados a partir de informações gerais, como o editor de aplicativos, medidas de segurança e controles, como se o aplicativo dá suporte para criptografia em repouso ou fornece um log de auditoria da atividade do usuário.

![Cartão de aplicativos OAuth do Cloud app Security](../images/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>Monitorar contas de usuário do aplicativo na nuvem

**Contas de aplicativo em nuvem para análise** lista contas que podem exigir atenção.

![Contas de aplicativo de nuvem para o cartão de revisão](../images/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>Entender quais aplicativos de nuvem são usados

Os **aplicativos de nuvem descobertos (categorias)** mostram quais tipos de aplicativos estão sendo usados na sua organização e links para o painel de descoberta de nuvem no Cloud app Security. Para obter mais informações, consulte [QuickStart: work with untected apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).  

![Cartão de categorias de aplicativos de nuvem descoberto](../images/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>Monitorar onde os usuários acessam os aplicativos de nuvem

**Locais de atividade do aplicativo na nuvem** mostram onde os usuários estão acessando aplicativos em nuvem.

![Cartão de locais de atividade do Cloud app](../images/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>Monitorar a integridade das cargas de trabalho da infraestrutura

**Infrastructure Health** mostra alertas de status de integridade para cargas de trabalho de infraestrutura na central de segurança do Azure.

A central de segurança do Azure oferece gerenciamento de segurança unificado e proteção avançada contra ameaças em cargas de trabalho locais e em nuvem. Você pode coletar, Pesquisar e analisar dados de segurança de várias fontes, incluindo firewalls e outras soluções de parceiros.

Para obter mais informações, consulte a [documentação da central de segurança do Azure](https://docs.microsoft.com/azure/security-center/).

![Cartão de integridade de infraestrutura](../images/infrastructure-health.png)
