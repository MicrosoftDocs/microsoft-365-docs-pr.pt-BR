---
title: Gerenciar incidentes no Microsoft 365 Defender
description: Saiba como atribuir, atualizar o status,
keywords: incidente, incidentes, alertas, alertas correlacionados, atribuir, atualizar, status, gerenciar, classificação, microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4e216f841c8728b1cabd98a931e7326f53344a74
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053503"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="19818-104">Gerenciar incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19818-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="19818-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="19818-105">**Applies to:**</span></span>
- <span data-ttu-id="19818-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19818-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="19818-107">Gerenciar incidentes é fundamental para garantir que as ameaças sejam contidas e tratadas.</span><span class="sxs-lookup"><span data-stu-id="19818-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="19818-108">No Microsoft 365 Defender, você tem acesso ao gerenciamento de incidentes em dispositivos, usuários e caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="19818-108">In Microsoft 365 Defender, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="19818-109">Você pode gerenciar incidentes selecionando um deles da **fila de incidentes**.</span><span class="sxs-lookup"><span data-stu-id="19818-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="19818-110">Você pode editar o nome de um incidente, resolvê-lo e definir sua classificação e determinação.</span><span class="sxs-lookup"><span data-stu-id="19818-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="19818-111">Você também pode atribuir o incidente a si mesmo e adicionar marcas e comentários.</span><span class="sxs-lookup"><span data-stu-id="19818-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="19818-112">Em casos em que, durante uma investigação, você deseje migrar os alertas de um incidente para outro, você também pode fazer isso na guia Alertas, criando, assim, um incidente maior ou menor que inclua todos os alertas relevantes.</span><span class="sxs-lookup"><span data-stu-id="19818-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="19818-113">Editar o nome do incidente</span><span class="sxs-lookup"><span data-stu-id="19818-113">Edit incident name</span></span>
<span data-ttu-id="19818-114">Os incidentes são atribuídos automaticamente a um nome com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias.</span><span class="sxs-lookup"><span data-stu-id="19818-114">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="19818-115">Isso permite que você entenda rapidamente o escopo do incidente.</span><span class="sxs-lookup"><span data-stu-id="19818-115">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="19818-116">Por exemplo: *incidente em vários estágios em vários pontos de extremidade relatados por várias fontes.*</span><span class="sxs-lookup"><span data-stu-id="19818-116">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="19818-117">Você pode modificar o nome do incidente para um melhor alinhamento à sua convenção de nomenclatura preferencial.</span><span class="sxs-lookup"><span data-stu-id="19818-117">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!NOTE]
> <span data-ttu-id="19818-118">Incidentes que existiam antes da adoção do recurso de nomenização automática de incidentes manterão seu nome.</span><span class="sxs-lookup"><span data-stu-id="19818-118">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>



## <a name="assign-incidents"></a><span data-ttu-id="19818-119">Atribuir incidentes</span><span class="sxs-lookup"><span data-stu-id="19818-119">Assign incidents</span></span>
<span data-ttu-id="19818-120">Caso um incidente ainda não tenha sido atribuído, você poderá selecionar **Atribuir a mim** para atribuir o incidente a si mesmo.</span><span class="sxs-lookup"><span data-stu-id="19818-120">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="19818-121">Ao fazer isso, você assume a propriedade não apenas do incidente, como também de todos os alertas associados a ele.</span><span class="sxs-lookup"><span data-stu-id="19818-121">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="19818-122">Definir o status e a classificação</span><span class="sxs-lookup"><span data-stu-id="19818-122">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="19818-123">Status do incidente</span><span class="sxs-lookup"><span data-stu-id="19818-123">Incident status</span></span>
<span data-ttu-id="19818-124">Você pode categorizar os incidentes (como **Ativo** ou **Resolvido**) alterando o status deles durante sua investigação.</span><span class="sxs-lookup"><span data-stu-id="19818-124">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="19818-125">Isso ajuda você a organizar e a gerenciar a maneira como sua equipe é capaz de responder a incidentes.</span><span class="sxs-lookup"><span data-stu-id="19818-125">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="19818-126">Por exemplo, seu analista de SOC pode analisar os incidentes **Ativos** urgentes do dia e decidir atribuí-los a si mesmo para investigação.</span><span class="sxs-lookup"><span data-stu-id="19818-126">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="19818-127">Como alternativa, seu analista de SOC pode definir o incidente como **Resolvido** caso ele já tenha sido solucionado.</span><span class="sxs-lookup"><span data-stu-id="19818-127">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="19818-128">Ao resolver um incidente, todos os alertas que fazem parte do incidente e que ainda estão abertos serão fechados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="19818-128">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="19818-129">Classificação e determinação</span><span class="sxs-lookup"><span data-stu-id="19818-129">Classification and determination</span></span>
<span data-ttu-id="19818-130">Você pode optar por não definir uma classificação ou decidir especificar se um incidente é verdadeiro ou falso.</span><span class="sxs-lookup"><span data-stu-id="19818-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="19818-131">Isso ajuda a equipe a ver padrões e a aprender com eles.</span><span class="sxs-lookup"><span data-stu-id="19818-131">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="19818-132">Adicionar comentários</span><span class="sxs-lookup"><span data-stu-id="19818-132">Add comments</span></span>
<span data-ttu-id="19818-133">Você pode adicionar comentários e exibir eventos históricos sobre um incidente para ver as alterações feitas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="19818-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="19818-134">Sempre que uma alteração ou um comentário forem feitos em um alerta, eles são registrados na seção Comentários e histórico.</span><span class="sxs-lookup"><span data-stu-id="19818-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="19818-135">Os comentários adicionados aparecem instantaneamente no painel.</span><span class="sxs-lookup"><span data-stu-id="19818-135">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="19818-136">Adicionar marcas de incidente</span><span class="sxs-lookup"><span data-stu-id="19818-136">Add incident tags</span></span>
<span data-ttu-id="19818-137">Você pode adicionar marcas personalizadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com características semelhantes.</span><span class="sxs-lookup"><span data-stu-id="19818-137">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="19818-138">Posteriormente, você pode filtrar a fila incidentes, buscando todos os incidentes que contenham uma marca específica.</span><span class="sxs-lookup"><span data-stu-id="19818-138">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>