---
title: Gerenciar incidentes no Microsoft 365 Defender
description: Saiba como atribuir, atualizar o status,
keywords: incidentes, incidentes, análise, resposta, alertas, alertas correlacionados, atribuir, atualizar, status, gerenciar, classificação, microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 5f66189979f401430353f4c15978a85276b48840
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939749"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="c8a73-104">Gerenciar incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8a73-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c8a73-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c8a73-105">**Applies to:**</span></span>
- <span data-ttu-id="c8a73-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8a73-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c8a73-107">O gerenciamento de incidentes é fundamental para garantir que as ameaças sejam contidas e abordadas.</span><span class="sxs-lookup"><span data-stu-id="c8a73-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="c8a73-108">Você gerencia incidentes de **incidentes & alertas** > incidentes no início rápido do centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="c8a73-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="c8a73-109">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="c8a73-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exemplo da fila de incidentes":::

<span data-ttu-id="c8a73-111">Aqui estão as maneiras de gerenciar seus incidentes:</span><span class="sxs-lookup"><span data-stu-id="c8a73-111">Here are the ways you can manage your incidents:</span></span>

- <span data-ttu-id="c8a73-112">Alterar o nome do incidente</span><span class="sxs-lookup"><span data-stu-id="c8a73-112">Change the incident name</span></span>
- <span data-ttu-id="c8a73-113">Adicione marcas de incidente.</span><span class="sxs-lookup"><span data-stu-id="c8a73-113">Add incident tags.</span></span>
- <span data-ttu-id="c8a73-114">Atribuir o incidente a uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="c8a73-114">Assign the incident to a user account</span></span>
- <span data-ttu-id="c8a73-115">Resolvê-los</span><span class="sxs-lookup"><span data-stu-id="c8a73-115">Resolve them</span></span> 
- <span data-ttu-id="c8a73-116">Definir sua classificação e determinação</span><span class="sxs-lookup"><span data-stu-id="c8a73-116">Set its classification and determination</span></span>
- <span data-ttu-id="c8a73-117">Adicione comentários.</span><span class="sxs-lookup"><span data-stu-id="c8a73-117">Add comments.</span></span>

<span data-ttu-id="c8a73-118">Você pode gerenciar incidentes do **painel Gerenciar incidentes** para um incidente.</span><span class="sxs-lookup"><span data-stu-id="c8a73-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="c8a73-119">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="c8a73-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Exemplo do painel Gerenciar incidentes de um incidente":::

<span data-ttu-id="c8a73-121">Você pode exibir esse painel no link **Gerenciar incidentes** no:</span><span class="sxs-lookup"><span data-stu-id="c8a73-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="c8a73-122">Painel de propriedades de um incidente na fila de incidentes.</span><span class="sxs-lookup"><span data-stu-id="c8a73-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="c8a73-123">**Página** de resumo de um incidente.</span><span class="sxs-lookup"><span data-stu-id="c8a73-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="c8a73-124">Em casos em que, ao analisar você gostaria de mover alertas de um incidente para outro, você também pode fazê-lo a partir da guia **Alertas,** criando assim um incidente maior ou menor que inclui todos os alertas relevantes.</span><span class="sxs-lookup"><span data-stu-id="c8a73-124">In cases where, while analyzing you would like to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="c8a73-125">Editar o nome do incidente</span><span class="sxs-lookup"><span data-stu-id="c8a73-125">Edit the incident name</span></span>

<span data-ttu-id="c8a73-126">O Microsoft 365 Defender atribui automaticamente um nome com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias.</span><span class="sxs-lookup"><span data-stu-id="c8a73-126">Microsoft 365 Defender automatically assigns a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="c8a73-127">Isso permite que você entenda rapidamente o escopo do incidente.</span><span class="sxs-lookup"><span data-stu-id="c8a73-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="c8a73-128">Por exemplo: *incidente em vários estágios em vários pontos de extremidade relatados por várias fontes.*</span><span class="sxs-lookup"><span data-stu-id="c8a73-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="c8a73-129">Você pode editar o nome do incidente no campo **Nome do** incidente no **painel Gerenciar** incidentes.</span><span class="sxs-lookup"><span data-stu-id="c8a73-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="c8a73-130">Incidentes que existiam antes da adoção do recurso de nomenização automática de incidentes manterão seu nome.</span><span class="sxs-lookup"><span data-stu-id="c8a73-130">Incidents that existed before the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="c8a73-131">Adicionar marcas de incidente</span><span class="sxs-lookup"><span data-stu-id="c8a73-131">Add incident tags</span></span>

<span data-ttu-id="c8a73-132">Você pode adicionar marcas personalizadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com uma característica comum.</span><span class="sxs-lookup"><span data-stu-id="c8a73-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="c8a73-133">Posteriormente, você pode filtrar a fila de incidentes para todos os incidentes que contenham uma marca específica.</span><span class="sxs-lookup"><span data-stu-id="c8a73-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="c8a73-134">Ao começar a digitar, você tem a opção de selecionar em uma lista de marcas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="c8a73-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="c8a73-135">Atribuir incidentes</span><span class="sxs-lookup"><span data-stu-id="c8a73-135">Assign incidents</span></span>

<span data-ttu-id="c8a73-136">Se um incidente ainda não tiver sido atribuído, você poderá selecionar **Atribuir e** especificar a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="c8a73-136">If an incident has not yet been assigned, you can select **Assign to** and specify the user account.</span></span> <span data-ttu-id="c8a73-137">Isso atribui a propriedade do incidente e todos os alertas associados a ele.</span><span class="sxs-lookup"><span data-stu-id="c8a73-137">Doing so assigns ownership of the incident and all the alerts associated with it.</span></span>

## <a name="resolve-incident"></a><span data-ttu-id="c8a73-138">Resolver incidente</span><span class="sxs-lookup"><span data-stu-id="c8a73-138">Resolve incident</span></span>

<span data-ttu-id="c8a73-139">Se o incidente tiver sido resolvido, selecione **Resolver incidentes** para mover a alternância para a direita.</span><span class="sxs-lookup"><span data-stu-id="c8a73-139">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="c8a73-140">Observe que a resolução de um incidente também resolve todos os alertas vinculados e ativos relacionados ao incidente.</span><span class="sxs-lookup"><span data-stu-id="c8a73-140">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="c8a73-141">Um incidente que não é resolvido é exibido como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="c8a73-141">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="c8a73-142">Definir a classificação e a determinação</span><span class="sxs-lookup"><span data-stu-id="c8a73-142">Set the classification and determination</span></span>

<span data-ttu-id="c8a73-143">A classificação de incidentes é se foi um alerta verdadeiro ou falso, que você configura no **campo Classificação.**</span><span class="sxs-lookup"><span data-stu-id="c8a73-143">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="c8a73-144">Se foi um alerta verdadeiro, você também deve especificar que tipo de ameaça era com o campo **Determinação.**</span><span class="sxs-lookup"><span data-stu-id="c8a73-144">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="c8a73-145">Especificar o tipo de ameaça ajuda sua equipe de segurança a ver padrões de ameaças e agir para defender sua organização deles.</span><span class="sxs-lookup"><span data-stu-id="c8a73-145">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="c8a73-146">Adicionar comentários</span><span class="sxs-lookup"><span data-stu-id="c8a73-146">Add comments</span></span>

<span data-ttu-id="c8a73-147">Você pode adicionar vários comentários a um incidente com o **campo Comentário.**</span><span class="sxs-lookup"><span data-stu-id="c8a73-147">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="c8a73-148">Cada comentário é adicionado aos eventos históricos do incidente.</span><span class="sxs-lookup"><span data-stu-id="c8a73-148">Each comment gets added to the historical events of the incident.</span></span> <span data-ttu-id="c8a73-149">Você pode ver os comentários e o histórico de um incidente no link **Comentários e** histórico na página **Resumo.**</span><span class="sxs-lookup"><span data-stu-id="c8a73-149">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c8a73-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c8a73-150">Related topics</span></span>

- [<span data-ttu-id="c8a73-151">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="c8a73-151">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c8a73-152">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="c8a73-152">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="c8a73-153">Analisar incidentes</span><span class="sxs-lookup"><span data-stu-id="c8a73-153">Analyze incidents</span></span>](investigate-incidents.md)
