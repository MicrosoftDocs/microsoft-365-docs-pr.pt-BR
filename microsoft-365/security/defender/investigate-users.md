---
title: Analisar usuários no Centro de segurança do Microsoft 365
description: Analisar usuários no centro de segurança do Microsoft 365
keywords: segurança, malware, Microsoft 365, M365, central de segurança, monitor, relatório, identidades, dados, dispositivos, aplicativos, incidente, análise, resposta
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 1fb5a4eee41384ef1afc9b46e5bf538344718fe9
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939725"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="900c8-104">Analisar usuários no Centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="900c8-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="900c8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="900c8-105">**Applies to:**</span></span>

- <span data-ttu-id="900c8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="900c8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="900c8-107">Parte da análise de incidentes pode incluir contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="900c8-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="900c8-108">Comece com a **guia Usuários** para um incidente de **Incidentes & alertas >** incidente *>* **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="900c8-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exemplo de uma página Usuários para um incidente":::

<span data-ttu-id="900c8-110">Para obter um resumo rápido de uma conta de usuário para o incidente, selecione a marca de seleção ao lado do nome da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="900c8-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="900c8-111">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="900c8-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Exemplo do painel de resumo da conta de usuário para um incidente no centro de segurança do Microsoft 365":::

<span data-ttu-id="900c8-113">A partir daqui, você pode selecionar **Ir para a página do usuário** para ver os detalhes de uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="900c8-113">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="900c8-114">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="900c8-114">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Exemplo da página da conta de usuário para um incidente no centro de segurança do Microsoft 365":::

<span data-ttu-id="900c8-116">Você também pode ver esta página selecionando o nome da conta de usuário na lista na **página Usuários.**</span><span class="sxs-lookup"><span data-stu-id="900c8-116">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="900c8-117">A página de usuário do Centro de Segurança do Microsoft 365 combina informações do Microsoft Defender para Ponto de Extremidade, do Microsoft Defender para Identidade e do Microsoft Cloud App Security (dependendo das licenças que você tiver).</span><span class="sxs-lookup"><span data-stu-id="900c8-117">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="900c8-118">Esta página mostra informações específicas do risco de segurança de uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="900c8-118">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="900c8-119">Isso inclui uma pontuação que ajuda a avaliar riscos e eventos recentes e alertas que contribuíram para o risco geral do usuário.</span><span class="sxs-lookup"><span data-stu-id="900c8-119">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="900c8-120">Nesta página, você pode fazer essas ações adicionais:</span><span class="sxs-lookup"><span data-stu-id="900c8-120">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="900c8-121">Marcar a conta de usuário como comprometida</span><span class="sxs-lookup"><span data-stu-id="900c8-121">Mark the user account as compromised</span></span>
- <span data-ttu-id="900c8-122">Exigir que o usuário entre novamente</span><span class="sxs-lookup"><span data-stu-id="900c8-122">Require the user to sign in again</span></span>
- <span data-ttu-id="900c8-123">Suspender a conta de usuário</span><span class="sxs-lookup"><span data-stu-id="900c8-123">Suspend the user account</span></span>
- <span data-ttu-id="900c8-124">Consulte as configurações da conta de usuário do Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="900c8-124">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="900c8-125">Exibir os arquivos pertencentes à conta de usuário</span><span class="sxs-lookup"><span data-stu-id="900c8-125">View the files owned by the user account</span></span>
- <span data-ttu-id="900c8-126">Exibir arquivos compartilhados com esse usuário.</span><span class="sxs-lookup"><span data-stu-id="900c8-126">View files shared with this user.</span></span> 

<span data-ttu-id="900c8-127">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="900c8-127">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Exemplo das ações em uma conta de usuário para um incidente no centro de segurança do Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="900c8-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="900c8-129">Related topics</span></span>

- [<span data-ttu-id="900c8-130">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="900c8-130">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="900c8-131">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="900c8-131">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="900c8-132">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="900c8-132">Manage incidents</span></span>](manage-incidents.md)