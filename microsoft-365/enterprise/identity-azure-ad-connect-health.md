---
title: 'Etapa 8: Monitorar a integridade da sincronização'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar o Azure AD Connect Health.
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865101"
---
# <a name="step-8-monitor-synchronization-health"></a>Etapa 8: Monitorar a integridade da sincronização

*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Nesta etapa, você vai instalar um agente do Azure AD Connect Health em cada um dos servidores de identidade local para monitorar a infraestrutura de identidade e os serviços de sincronização fornecidos pelo Azure AD Connect. As informações de monitoramento serão disponibilizadas em um portal do Azure AD Connect Health, em que você verá alertas, monitoramento do desempenho, análise de uso e outras informações.

![Componentes do Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

A decisão da estrutura principal de como usar o Azure AD Connect Health baseia-se em como o Azure AD Connect está sendo usado:

- Se você estiver usando a opção de **autenticação gerenciada**, comece [usando o Azure AD Connect Health com a sincronização](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) para entender e configurar o Azure AD Connect Health.
- Se você estiver sincronizando apenas os nomes das contas e dos grupos usando a **autenticação federada** com os Serviços de Federação do Active Directory (AD FS), comece [usando o Azure AD Connect Health com os AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) para entender e configurar o Azure AD Connect Health.

Ao concluir essa etapa, você:

- Terá instalado o agente do Azure AD Connect Health nos servidores do provedor de identidade local.
- Poderá ver, no portal do Azure AD Connect Health, o estado atual de sua infraestrutura local e das atividades de sincronização com o locatário do Azure AD para suas assinaturas do Office 365 e EMS.

Como ponto de verificação provisório, você pode consultar os [critérios de saída](identity-exit-criteria.md#crit-identity-sync-health) para esta etapa.


## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [Simplificar atualizações de senha](identity-password-writeback.md) |

