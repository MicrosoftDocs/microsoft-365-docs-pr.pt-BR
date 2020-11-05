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
ms.openlocfilehash: f73c6b010677cdc481655d1d5310872fd1a99126
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920509"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="f4fd0-105">Monitoramento e relatórios de aplicativos no centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4fd0-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f4fd0-106">Esses relatórios fornecem mais informações sobre como os aplicativos de nuvem estão sendo usados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="f4fd0-107">Inclui diferentes tipos de aplicativos, seu nível de risco e alertas.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="f4fd0-108">Monitorar contas de e-mail em risco</span><span class="sxs-lookup"><span data-stu-id="f4fd0-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="f4fd0-109">A **proteção de email** mostra as contas de email em risco.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="f4fd0-110">Você pode selecionar uma conta para investigar ainda mais a central de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![Cartão de proteção de email](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="f4fd0-112">Monitorar permissões de aplicativo concedidas por usuários</span><span class="sxs-lookup"><span data-stu-id="f4fd0-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="f4fd0-113">**Cloud app Security-aplicativos OAuth** lista aplicativos descobertos pela Cloud app Security que receberam permissões pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="f4fd0-114">O catálogo de riscos do Cloud app Security inclui mais de 16.000 aplicativos que são avaliados usando mais de 70 fatores de risco.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="f4fd0-115">Os fatores de risco são iniciados a partir de informações gerais, como o editor de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="f4fd0-116">Em seguida, ele passa para medidas de segurança e controles, como se o aplicativo dá suporte à criptografia em repouso ou fornece um log de auditoria da atividade do usuário.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Cartão de aplicativos OAuth do Cloud app Security](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="f4fd0-118">Monitorar contas de usuário do aplicativo na nuvem</span><span class="sxs-lookup"><span data-stu-id="f4fd0-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="f4fd0-119">**Contas de aplicativo em nuvem para análise** lista contas que podem exigir atenção.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Contas de aplicativo de nuvem para o cartão de revisão](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="f4fd0-121">Entender quais aplicativos de nuvem são usados</span><span class="sxs-lookup"><span data-stu-id="f4fd0-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="f4fd0-122">Os **aplicativos de nuvem descobertos (categorias)** mostram quais tipos de aplicativos estão sendo usados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="f4fd0-123">Ele é vinculado ao painel de descoberta de nuvem no Cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="f4fd0-124">Para obter mais informações, consulte [QuickStart: work with untected apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span><span class="sxs-lookup"><span data-stu-id="f4fd0-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Cartão de categorias de aplicativos de nuvem descoberto](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="f4fd0-126">Monitorar onde os usuários acessam os aplicativos de nuvem</span><span class="sxs-lookup"><span data-stu-id="f4fd0-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="f4fd0-127">**Locais de atividade do aplicativo na nuvem** mostram onde os usuários estão acessando aplicativos em nuvem.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Cartão de locais de atividade do Cloud app](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="f4fd0-129">Monitorar a integridade das cargas de trabalho da infraestrutura</span><span class="sxs-lookup"><span data-stu-id="f4fd0-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="f4fd0-130">**Infrastructure Health** mostra alertas de status de integridade para cargas de trabalho de infraestrutura no Azure defender.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender.</span></span>

<span data-ttu-id="f4fd0-131">O Azure defender fornece o gerenciamento de segurança unificado e o defender para Office 365 entre cargas de trabalho locais e em nuvem.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-131">Azure Defender provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="f4fd0-132">Você pode coletar, Pesquisar e analisar dados de segurança de fontes diferentes, incluindo firewalls e outras soluções de parceiros.</span><span class="sxs-lookup"><span data-stu-id="f4fd0-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="f4fd0-133">Para obter mais informações, consulte a [documentação do Azure defender](https://docs.microsoft.com/azure/security-center/).</span><span class="sxs-lookup"><span data-stu-id="f4fd0-133">For more information, see [Azure Defender Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Cartão de integridade de infraestrutura](../../media/infrastructure-health.png)
