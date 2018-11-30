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
# <a name="step-8-monitor-synchronization-health"></a><span data-ttu-id="f277d-103">Etapa 8: Monitorar a integridade da sincronização</span><span class="sxs-lookup"><span data-stu-id="f277d-103">Step 8: Monitor synchronization health</span></span>

<span data-ttu-id="f277d-104">*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="f277d-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="f277d-p101">Nesta etapa, você vai instalar um agente do Azure AD Connect Health em cada um dos servidores de identidade local para monitorar a infraestrutura de identidade e os serviços de sincronização fornecidos pelo Azure AD Connect. As informações de monitoramento serão disponibilizadas em um portal do Azure AD Connect Health, em que você verá alertas, monitoramento do desempenho, análise de uso e outras informações.</span><span class="sxs-lookup"><span data-stu-id="f277d-p101">In Step 4, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect. The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Componentes do Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

<span data-ttu-id="f277d-108">A decisão da estrutura principal de como usar o Azure AD Connect Health baseia-se em como o Azure AD Connect está sendo usado:</span><span class="sxs-lookup"><span data-stu-id="f277d-108">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="f277d-109">Se você estiver usando a opção de **autenticação gerenciada**, comece [usando o Azure AD Connect Health com a sincronização](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) para entender e configurar o Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="f277d-109">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="f277d-110">Se você estiver sincronizando apenas os nomes das contas e dos grupos usando a **autenticação federada** com os Serviços de Federação do Active Directory (AD FS), comece [usando o Azure AD Connect Health com os AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) para entender e configurar o Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="f277d-110">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="f277d-111">Ao concluir essa etapa, você:</span><span class="sxs-lookup"><span data-stu-id="f277d-111">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="f277d-112">Terá instalado o agente do Azure AD Connect Health nos servidores do provedor de identidade local.</span><span class="sxs-lookup"><span data-stu-id="f277d-112">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="f277d-113">Poderá ver, no portal do Azure AD Connect Health, o estado atual de sua infraestrutura local e das atividades de sincronização com o locatário do Azure AD para suas assinaturas do Office 365 e EMS.</span><span class="sxs-lookup"><span data-stu-id="f277d-113">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="f277d-114">Como ponto de verificação provisório, você pode consultar os [critérios de saída](identity-exit-criteria.md#crit-identity-sync-health) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f277d-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="f277d-115">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="f277d-115">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="f277d-116">Simplificar atualizações de senha</span><span class="sxs-lookup"><span data-stu-id="f277d-116">Simplify password updates</span></span>](identity-password-writeback.md) |

