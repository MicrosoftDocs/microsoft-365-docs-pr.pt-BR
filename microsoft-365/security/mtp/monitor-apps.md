---
title: Relatórios de monitoramento & aplicativo - Central de segurança
description: Saiba como obter mais informações sobre o uso de aplicativos na nuvem em sua organização. Inclui diferentes tipos de aplicativos, seu nível de risco e alertas.
keywords: segurança, malware, Microsoft 365, M365, centro de segurança, monitorar, relatório, aplicativos
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930517"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="60be3-105">Monitoramento e relatório de aplicativos no centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="60be3-105">App monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="60be3-106">Esses relatórios fornecem mais informações sobre como os aplicativos de nuvem estão sendo usados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="60be3-106">These reports provide more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="60be3-107">Inclui diferentes tipos de aplicativos, seu nível de risco e alertas.</span><span class="sxs-lookup"><span data-stu-id="60be3-107">Includes different kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="60be3-108">Monitorar contas de e-mail em risco</span><span class="sxs-lookup"><span data-stu-id="60be3-108">Monitor email accounts at risk</span></span>

<span data-ttu-id="60be3-109">**A proteção de** email mostra contas de email em risco.</span><span class="sxs-lookup"><span data-stu-id="60be3-109">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="60be3-110">Você pode selecionar uma conta para investigar mais na Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="60be3-110">You can select an account to investigate further in Microsoft Defender Security Center.</span></span>

![Cartão de proteção de email](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="60be3-112">Monitorar permissões de aplicativo concedidas pelos usuários</span><span class="sxs-lookup"><span data-stu-id="60be3-112">Monitor app permissions granted by users</span></span>

<span data-ttu-id="60be3-113">**Segurança de Aplicativo na Nuvem - Os** aplicativos OAuth listam aplicativos descobertos pelo Cloud App Security que foram concedidos por usuários.</span><span class="sxs-lookup"><span data-stu-id="60be3-113">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="60be3-114">O catálogo de riscos do Cloud App Security inclui mais de 16.000 aplicativos avaliados usando mais de 70 fatores de risco.</span><span class="sxs-lookup"><span data-stu-id="60be3-114">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="60be3-115">Os fatores de risco começam com informações gerais, como o editor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="60be3-115">The risk factors start from general information, such as the app publisher.</span></span> <span data-ttu-id="60be3-116">Em seguida, ele passa para medidas e controles de segurança, como se o aplicativo dá suporte à criptografia em repouso ou fornece um log de auditoria de atividades do usuário.</span><span class="sxs-lookup"><span data-stu-id="60be3-116">It then moves to security measures and controls, such as whether the app supports encryption at rest or provides an audit log of user activity.</span></span>

![Cartão de aplicativos OAuth do Cloud App Security](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="60be3-118">Monitorar contas de usuário do aplicativo na nuvem</span><span class="sxs-lookup"><span data-stu-id="60be3-118">Monitor cloud app user accounts</span></span>

<span data-ttu-id="60be3-119">**Contas de aplicativos na nuvem para contas** de listas de revisão que podem exigir atenção.</span><span class="sxs-lookup"><span data-stu-id="60be3-119">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Contas de aplicativo na nuvem para cartão de opinião](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="60be3-121">Entender quais aplicativos de nuvem são usados</span><span class="sxs-lookup"><span data-stu-id="60be3-121">Understand which cloud apps are used</span></span>

<span data-ttu-id="60be3-122">**Aplicativos de nuvem descobertos (categorias)** mostram quais tipos de aplicativos estão sendo usados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="60be3-122">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization.</span></span> <span data-ttu-id="60be3-123">Ele é links para o painel descoberta na nuvem no Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="60be3-123">It links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="60be3-124">Para obter mais informações, consulte [Guia de início rápido: trabalhar com aplicativos descobertos.](https://docs.microsoft.com/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="60be3-124">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Cartão de categorias de aplicativos em nuvem descoberto](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="60be3-126">Monitorar onde os usuários acessam aplicativos na nuvem</span><span class="sxs-lookup"><span data-stu-id="60be3-126">Monitor where users access cloud apps</span></span>

<span data-ttu-id="60be3-127">**Os locais de atividade do aplicativo na nuvem** mostram onde os usuários estão acessando aplicativos de nuvem.</span><span class="sxs-lookup"><span data-stu-id="60be3-127">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Cartão de locais de atividades do aplicativo na nuvem](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="60be3-129">Monitorar a saúde de cargas de trabalho de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="60be3-129">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="60be3-130">**A infraestrutura mostra** alertas de status de saúde para cargas de trabalho de infraestrutura no Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="60be3-130">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Defender.</span></span>

<span data-ttu-id="60be3-131">O Azure Defender fornece gerenciamento de segurança unificado e o Defender para Office 365 em cargas de trabalho locais e na nuvem.</span><span class="sxs-lookup"><span data-stu-id="60be3-131">Azure Defender provides unified security management and Defender for Office 365 across on-premises and cloud workloads.</span></span> <span data-ttu-id="60be3-132">Você pode coletar, pesquisar e analisar dados de segurança de diferentes fontes, incluindo firewalls e outras soluções de parceiros.</span><span class="sxs-lookup"><span data-stu-id="60be3-132">You can collect, search, and analyze security data from different sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="60be3-133">Para obter mais informações, consulte [a Documentação do Azure Defender.](https://docs.microsoft.com/azure/security-center/)</span><span class="sxs-lookup"><span data-stu-id="60be3-133">For more information, see [Azure Defender Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Cartão de saúde da infraestrutura](../../media/infrastructure-health.png)
