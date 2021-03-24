---
title: Investigar usuários no Centro de segurança do Microsoft 365
description: investigar usuários no centro de segurança do Microsoft 365
keywords: segurança, malware, Microsoft 365, M365, central de segurança, monitor, relatório, identidades, dados, dispositivos, aplicativos
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: f48716ebd9e25d1f8b24d9276aaa5890a335a808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052528"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="e5bbe-104">Investigar usuários no Centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e5bbe-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="e5bbe-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e5bbe-105">**Applies to:**</span></span>

- <span data-ttu-id="e5bbe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5bbe-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e5bbe-107">Como parte da investigação, você pode descobrir que um usuário foi comprometido.</span><span class="sxs-lookup"><span data-stu-id="e5bbe-107">As part of your investigation, you might find that a user has been compromised.</span></span>

<span data-ttu-id="e5bbe-108">A página de usuário do Centro de Segurança do Microsoft 365 combina informações do Microsoft Defender para Ponto de Extremidade, do Microsoft Defender para Identidade e do Microsoft Cloud App Security (dependendo das licenças que você tiver).</span><span class="sxs-lookup"><span data-stu-id="e5bbe-108">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> <span data-ttu-id="e5bbe-109">Esta página é o ponto de partida ideal para investigar usuários e possíveis incidentes.</span><span class="sxs-lookup"><span data-stu-id="e5bbe-109">This page is the ideal starting place for investigating users and potential incidents.</span></span>
<span data-ttu-id="e5bbe-110">![Página do usuário](../../media/m3d-userpage.png)</span><span class="sxs-lookup"><span data-stu-id="e5bbe-110">![User page](../../media/m3d-userpage.png)</span></span>

<span data-ttu-id="e5bbe-111">Esta página mostra informações específicas do risco de segurança de um usuário.</span><span class="sxs-lookup"><span data-stu-id="e5bbe-111">This page shows information specific to the security risk of a user.</span></span> <span data-ttu-id="e5bbe-112">Isso inclui uma pontuação que ajuda a avaliar riscos, eventos recentes e alertas que contribuíram para o risco geral do usuário e muito mais.</span><span class="sxs-lookup"><span data-stu-id="e5bbe-112">This includes a score that helps assess risk, recent events and alerts that contributed to the overall risk of the user, and more.</span></span>

<span data-ttu-id="e5bbe-113">Você pode acessar essa página de várias áreas no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e5bbe-113">You can access this page from multiple areas in the Microsoft 365 security center.</span></span> <span data-ttu-id="e5bbe-114">Você pode acessar esta página a partir de um incidente específico na **guia Usuários.** Alguns alertas podem incluir usuários como um ativo afetado específico.</span><span class="sxs-lookup"><span data-stu-id="e5bbe-114">You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset.</span></span> <span data-ttu-id="e5bbe-115">Você também pode pesquisar usuários.</span><span class="sxs-lookup"><span data-stu-id="e5bbe-115">You can also search for users.</span></span>  

<span data-ttu-id="e5bbe-116">Saiba mais sobre como investigar usuários e possíveis riscos [neste tutorial de Segurança do Aplicativo na Nuvem.](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them)</span><span class="sxs-lookup"><span data-stu-id="e5bbe-116">Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e5bbe-117">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e5bbe-117">Related topics</span></span>

- [<span data-ttu-id="e5bbe-118">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="e5bbe-118">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e5bbe-119">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="e5bbe-119">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="e5bbe-120">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="e5bbe-120">Manage incidents</span></span>](manage-incidents.md)