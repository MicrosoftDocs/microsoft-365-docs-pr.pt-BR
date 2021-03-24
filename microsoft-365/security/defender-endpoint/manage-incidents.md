---
title: Gerenciar incidentes do Microsoft Defender ATP
description: Gerencie incidentes atribuindo-o, atualizando seu status ou definindo sua classificação.
keywords: incidentes, gerenciar, atribuir, status, classificação, alerta verdadeiro, alerta falso
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 412938e506895aaabfa0796cb1d46ea892876435
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052872"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a><span data-ttu-id="26c43-104">Gerenciar o Microsoft Defender para incidentes de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="26c43-104">Manage Microsoft Defender for Endpoint incidents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="26c43-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="26c43-105">**Applies to:**</span></span>
- [<span data-ttu-id="26c43-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="26c43-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="26c43-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26c43-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="26c43-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="26c43-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="26c43-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="26c43-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="26c43-110">O gerenciamento de incidentes é uma parte importante de cada operação de segurança cibernética.</span><span class="sxs-lookup"><span data-stu-id="26c43-110">Managing incidents is an important part of every cybersecurity operation.</span></span> <span data-ttu-id="26c43-111">Você pode gerenciar incidentes selecionando um incidente na fila **incidentes ou** no painel de gerenciamento **de incidentes.**</span><span class="sxs-lookup"><span data-stu-id="26c43-111">You can manage incidents by selecting an incident from the **Incidents queue** or the **Incidents management pane**.</span></span> 


<span data-ttu-id="26c43-112">Selecionar um incidente na fila **Incidentes** traz o **painel** gerenciamento de incidentes onde você pode abrir a página de incidentes para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="26c43-112">Selecting an incident from the **Incidents queue** brings up the **Incident management pane** where you can open the incident page for details.</span></span>


![Imagem do painel de gerenciamento de incidentes](images/atp-incidents-mgt-pane-updated.png)

<span data-ttu-id="26c43-114">Você pode atribuir incidentes a si mesmo, alterar o status e a classificação, renomear ou comentar sobre eles para acompanhar seu progresso.</span><span class="sxs-lookup"><span data-stu-id="26c43-114">You can assign incidents to yourself, change the status and classification, rename, or comment on them to keep track of their progress.</span></span>

> [!TIP]
> <span data-ttu-id="26c43-115">Para obter visibilidade adicional rapidamente, os nomes de incidentes são gerados automaticamente com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias.</span><span class="sxs-lookup"><span data-stu-id="26c43-115">For additional visibility at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="26c43-116">Isso permite que você entenda rapidamente o escopo do incidente.</span><span class="sxs-lookup"><span data-stu-id="26c43-116">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="26c43-117">Por exemplo: *incidente em vários estágios em vários pontos de extremidade relatados por várias fontes.*</span><span class="sxs-lookup"><span data-stu-id="26c43-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="26c43-118">Incidentes que existiam antes da adoção da nomenização automática de incidentes manterão seus nomes.</span><span class="sxs-lookup"><span data-stu-id="26c43-118">Incidents that existed prior the rollout of automatic incident naming will retain their names.</span></span>
>


![Imagem da página de detalhes do incidente](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a><span data-ttu-id="26c43-120">Atribuir incidentes</span><span class="sxs-lookup"><span data-stu-id="26c43-120">Assign incidents</span></span>
<span data-ttu-id="26c43-121">Se um incidente ainda não tiver sido atribuído, selecione Atribuir a **mim** para atribuir o incidente a si mesmo.</span><span class="sxs-lookup"><span data-stu-id="26c43-121">If an incident has not been assigned yet, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="26c43-122">Ao fazer isso, você assume a propriedade não apenas do incidente, como também de todos os alertas associados a ele.</span><span class="sxs-lookup"><span data-stu-id="26c43-122">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="26c43-123">Definir o status e a classificação</span><span class="sxs-lookup"><span data-stu-id="26c43-123">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="26c43-124">Status do incidente</span><span class="sxs-lookup"><span data-stu-id="26c43-124">Incident status</span></span>
<span data-ttu-id="26c43-125">Você pode categorizar os incidentes (como **Ativo** ou **Resolvido**) alterando o status deles durante sua investigação.</span><span class="sxs-lookup"><span data-stu-id="26c43-125">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="26c43-126">Isso ajuda você a organizar e a gerenciar a maneira como sua equipe é capaz de responder a incidentes.</span><span class="sxs-lookup"><span data-stu-id="26c43-126">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="26c43-127">Por exemplo, seu analista soC pode revisar os incidentes **ativos** urgentes do dia e decidir atribuí-los a si mesmo para investigação.</span><span class="sxs-lookup"><span data-stu-id="26c43-127">For example, your SoC analyst can review the urgent **Active** incidents for the day, and decide to assign them to himself for investigation.</span></span>

<span data-ttu-id="26c43-128">Como alternativa, seu analista soC pode definir o incidente como **Resolvido** se o incidente tiver sido resolvido.</span><span class="sxs-lookup"><span data-stu-id="26c43-128">Alternatively, your SoC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> 

### <a name="classification"></a><span data-ttu-id="26c43-129">Classificação</span><span class="sxs-lookup"><span data-stu-id="26c43-129">Classification</span></span>
<span data-ttu-id="26c43-130">Você pode optar por não definir uma classificação ou decidir especificar se um incidente é verdadeiro ou falso.</span><span class="sxs-lookup"><span data-stu-id="26c43-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="26c43-131">Isso ajuda a equipe a ver padrões e a aprender com eles.</span><span class="sxs-lookup"><span data-stu-id="26c43-131">Doing so helps the team see patterns and learn from them.</span></span>

### <a name="add-comments"></a><span data-ttu-id="26c43-132">Adicionar comentários</span><span class="sxs-lookup"><span data-stu-id="26c43-132">Add comments</span></span>
<span data-ttu-id="26c43-133">Você pode adicionar comentários e exibir eventos históricos sobre um incidente para ver as alterações feitas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="26c43-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="26c43-134">Sempre que uma alteração ou um comentário forem feitos em um alerta, eles são registrados na seção Comentários e histórico.</span><span class="sxs-lookup"><span data-stu-id="26c43-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="26c43-135">Os comentários adicionados aparecem instantaneamente no painel.</span><span class="sxs-lookup"><span data-stu-id="26c43-135">Added comments instantly appear on the pane.</span></span>



## <a name="related-topics"></a><span data-ttu-id="26c43-136">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="26c43-136">Related topics</span></span>
- [<span data-ttu-id="26c43-137">Fila de incidentes</span><span class="sxs-lookup"><span data-stu-id="26c43-137">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="26c43-138">Exibir e organizar a fila incidentes</span><span class="sxs-lookup"><span data-stu-id="26c43-138">View and organize the Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="26c43-139">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="26c43-139">Investigate incidents</span></span>](investigate-incidents.md)
