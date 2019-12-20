---
title: Gerenciar incidentes na Proteção contra Ameaças da Microsoft
description: Saiba como atribuir, atualizar o status,
keywords: incidente, incidentes, alertas, alertas correlacionados, atribuir, atualizar, status, gerenciar, classificação, microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: d6b7c754db3b43e909871a5a60fa1ab155f2d01d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806950"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="04696-104">Gerenciar incidentes na Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="04696-104">Manage incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="04696-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="04696-105">**Applies to:**</span></span>
- <span data-ttu-id="04696-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="04696-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="04696-107">Gerenciar incidentes é fundamental para garantir que as ameaças sejam contidas e tratadas.</span><span class="sxs-lookup"><span data-stu-id="04696-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="04696-108">No Proteção contra Ameaças da Microsoft, você tem acesso ao gerenciamento de incidentes em dispositivos, usuários e caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="04696-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="04696-109">Você pode gerenciar incidentes selecionando um deles da **fila de incidentes**.</span><span class="sxs-lookup"><span data-stu-id="04696-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="04696-110">Você pode editar o nome de um incidente, resolvê-lo e definir sua classificação e determinação.</span><span class="sxs-lookup"><span data-stu-id="04696-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="04696-111">Você também pode atribuir o incidente a si mesmo e adicionar marcas e comentários.</span><span class="sxs-lookup"><span data-stu-id="04696-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="04696-112">Em casos em que, durante uma investigação, você deseje migrar os alertas de um incidente para outro, você também pode fazer isso na guia Alertas, criando, assim, um incidente maior ou menor que inclua todos os alertas relevantes.</span><span class="sxs-lookup"><span data-stu-id="04696-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="04696-113">Editar o nome do incidente</span><span class="sxs-lookup"><span data-stu-id="04696-113">Edit incident name</span></span>
<span data-ttu-id="04696-114">Por padrão, um número é atribuído a um incidente.</span><span class="sxs-lookup"><span data-stu-id="04696-114">By default, an incident is assigned a number.</span></span> <span data-ttu-id="04696-115">Você pode modificar o nome do incidente para um melhor alinhamento à sua convenção de nomenclatura preferencial.</span><span class="sxs-lookup"><span data-stu-id="04696-115">You can modify the incident name to better align with your preferred naming convention.</span></span>
 
## <a name="assign-incidents"></a><span data-ttu-id="04696-116">Atribuir incidentes</span><span class="sxs-lookup"><span data-stu-id="04696-116">Assign incidents</span></span>
<span data-ttu-id="04696-117">Caso um incidente ainda não tenha sido atribuído, você poderá selecionar **Atribuir a mim** para atribuir o incidente a si mesmo.</span><span class="sxs-lookup"><span data-stu-id="04696-117">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="04696-118">Ao fazer isso, você assume a propriedade não apenas do incidente, como também de todos os alertas associados a ele.</span><span class="sxs-lookup"><span data-stu-id="04696-118">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="04696-119">Definir o status e a classificação</span><span class="sxs-lookup"><span data-stu-id="04696-119">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="04696-120">Status do incidente</span><span class="sxs-lookup"><span data-stu-id="04696-120">Incident status</span></span>
<span data-ttu-id="04696-121">Você pode categorizar os incidentes (como **Ativo**ou **Resolvido**) alterando o status deles durante sua investigação.</span><span class="sxs-lookup"><span data-stu-id="04696-121">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="04696-122">Isso ajuda você a organizar e a gerenciar a maneira como sua equipe é capaz de responder a incidentes.</span><span class="sxs-lookup"><span data-stu-id="04696-122">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="04696-123">Por exemplo, seu analista de SOC pode analisar os incidentes **Ativos** urgentes do dia e decidir atribuí-los a si mesmo para investigação.</span><span class="sxs-lookup"><span data-stu-id="04696-123">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="04696-124">Como alternativa, seu analista de SOC pode definir o incidente como **Resolvido** caso ele já tenha sido solucionado.</span><span class="sxs-lookup"><span data-stu-id="04696-124">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="04696-125">Ao resolver um incidente, todos os alertas que fazem parte do incidente e que ainda estão abertos serão fechados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="04696-125">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="04696-126">Classificação e determinação</span><span class="sxs-lookup"><span data-stu-id="04696-126">Classification and determination</span></span>
<span data-ttu-id="04696-127">Você pode optar por não definir uma classificação ou decidir especificar se um incidente é verdadeiro ou falso.</span><span class="sxs-lookup"><span data-stu-id="04696-127">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="04696-128">Isso ajuda a equipe a ver padrões e a aprender com eles.</span><span class="sxs-lookup"><span data-stu-id="04696-128">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="04696-129">Adicionar comentários</span><span class="sxs-lookup"><span data-stu-id="04696-129">Add comments</span></span>
<span data-ttu-id="04696-130">Você pode adicionar comentários e exibir eventos históricos sobre um incidente para ver as alterações feitas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="04696-130">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="04696-131">Sempre que uma alteração ou um comentário forem feitos em um alerta, eles são registrados na seção Comentários e histórico.</span><span class="sxs-lookup"><span data-stu-id="04696-131">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="04696-132">Os comentários adicionados aparecem instantaneamente no painel.</span><span class="sxs-lookup"><span data-stu-id="04696-132">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="04696-133">Adicionar marcas de incidente</span><span class="sxs-lookup"><span data-stu-id="04696-133">Add incident tags</span></span>
<span data-ttu-id="04696-134">Você pode adicionar marcas personalizadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com características semelhantes.</span><span class="sxs-lookup"><span data-stu-id="04696-134">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="04696-135">Posteriormente, você pode filtrar a fila incidentes, buscando todos os incidentes que contenham uma marca específica.</span><span class="sxs-lookup"><span data-stu-id="04696-135">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>

