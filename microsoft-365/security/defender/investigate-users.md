---
title: Investigar usuários no Centro de segurança do Microsoft 365
description: Investigar usuários no centro de Microsoft 365 segurança
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
ms.openlocfilehash: c03e4d5bd94eb6105ffab91c6dad2b74d7159dde
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300056"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="859b0-104">Investigar usuários no Centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="859b0-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="859b0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="859b0-105">**Applies to:**</span></span>

- <span data-ttu-id="859b0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="859b0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="859b0-107">Parte da investigação de incidentes pode incluir contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="859b0-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="859b0-108">Comece com a **guia Usuários** para um incidente de **Incidentes & alertas >** incidente *>* **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="859b0-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exemplo de uma página Usuários para um incidente":::

<span data-ttu-id="859b0-110">Para obter um resumo rápido de uma conta de usuário para o incidente, selecione a marca de seleção ao lado do nome da conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="859b0-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="859b0-111">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="859b0-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Exemplo do painel de resumo da conta de usuário para um incidente no Microsoft 365 de segurança":::

> [!NOTE]
> <span data-ttu-id="859b0-113">A página Usuário mostra Azure Active Directory organização (AD), bem como grupos, ajudando você a entender os grupos e permissões associados a um usuário.</span><span class="sxs-lookup"><span data-stu-id="859b0-113">The User page shows Azure Active Directory (AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="859b0-114">Nesta página de pré-saída, você pode revisar as informações de ameaça do usuário, incluindo quaisquer incidentes atuais, alertas ativos e nível de risco, bem como a exposição do usuário, contas, dispositivos e muito mais.</span><span class="sxs-lookup"><span data-stu-id="859b0-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="859b0-115">Além disso, você pode tomar medidas diretamente no centro de segurança Microsoft 365 para lidar com um usuário comprometido, confirmando que o usuário está comprometido ou exigindo que ele entre novamente.</span><span class="sxs-lookup"><span data-stu-id="859b0-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="859b0-116">A partir daqui, você pode selecionar **Ir para a página do usuário** para ver os detalhes de uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="859b0-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="859b0-117">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="859b0-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Exemplo da página de conta de usuário para um incidente no centro Microsoft 365 segurança":::

<span data-ttu-id="859b0-119">Você também pode ver esta página selecionando o nome da conta de usuário na lista na **página Usuários.**</span><span class="sxs-lookup"><span data-stu-id="859b0-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="859b0-120">A Microsoft 365 de usuário do centro de segurança combina informações do Microsoft Defender para Ponto de Extremidade, Do Microsoft Defender para Identidade e Microsoft Cloud App Security (dependendo das licenças que você tiver).</span><span class="sxs-lookup"><span data-stu-id="859b0-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="859b0-121">Esta página mostra informações específicas do risco de segurança de uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="859b0-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="859b0-122">Isso inclui uma pontuação que ajuda a avaliar riscos e eventos recentes e alertas que contribuíram para o risco geral do usuário.</span><span class="sxs-lookup"><span data-stu-id="859b0-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="859b0-123">Nesta página, você pode fazer essas ações adicionais:</span><span class="sxs-lookup"><span data-stu-id="859b0-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="859b0-124">Marcar a conta de usuário como comprometida</span><span class="sxs-lookup"><span data-stu-id="859b0-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="859b0-125">Exigir que o usuário entre novamente</span><span class="sxs-lookup"><span data-stu-id="859b0-125">Require the user to sign in again</span></span>
- <span data-ttu-id="859b0-126">Suspender a conta de usuário</span><span class="sxs-lookup"><span data-stu-id="859b0-126">Suspend the user account</span></span>
- <span data-ttu-id="859b0-127">Consulte as configurações de Azure Active Directory de usuário (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="859b0-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="859b0-128">Exibir os arquivos pertencentes à conta de usuário</span><span class="sxs-lookup"><span data-stu-id="859b0-128">View the files owned by the user account</span></span>
- <span data-ttu-id="859b0-129">Exibir arquivos compartilhados com esse usuário.</span><span class="sxs-lookup"><span data-stu-id="859b0-129">View files shared with this user.</span></span> 

<span data-ttu-id="859b0-130">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="859b0-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Exemplo das ações em uma conta de usuário para um incidente no centro Microsoft 365 segurança":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a><span data-ttu-id="859b0-132">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="859b0-132">Next steps</span></span>

<span data-ttu-id="859b0-133">Conforme necessário para incidentes no processo, continue sua [investigação](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="859b0-133">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="859b0-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="859b0-134">See also</span></span>

- [<span data-ttu-id="859b0-135">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="859b0-135">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="859b0-136">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="859b0-136">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="859b0-137">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="859b0-137">Manage incidents</span></span>](manage-incidents.md)