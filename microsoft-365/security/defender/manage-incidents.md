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
ms.openlocfilehash: 9cb3cc67c3992773897ea8178f261d25dcd87da0
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594140"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="5f256-104">Gerenciar incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f256-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5f256-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5f256-105">**Applies to:**</span></span>
- <span data-ttu-id="5f256-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f256-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5f256-107">O gerenciamento de incidentes é fundamental para garantir que as ameaças sejam contidas e abordadas.</span><span class="sxs-lookup"><span data-stu-id="5f256-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="5f256-108">Você gerencia incidentes de **incidentes & alertas** > Incidentes no início rápido do centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="5f256-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="5f256-109">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="5f256-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exemplo da fila de incidentes":::

<span data-ttu-id="5f256-111">Aqui estão as maneiras de gerenciar seus incidentes:</span><span class="sxs-lookup"><span data-stu-id="5f256-111">Here are the ways you can manage your incidents:</span></span>

- [<span data-ttu-id="5f256-112">Editar o nome do incidente</span><span class="sxs-lookup"><span data-stu-id="5f256-112">Edit the incident name</span></span>](#edit-the-incident-name)
- [<span data-ttu-id="5f256-113">Adicionar marcas de incidente</span><span class="sxs-lookup"><span data-stu-id="5f256-113">Add incident tags</span></span>](#add-incident-tags)
- [<span data-ttu-id="5f256-114">Atribuir o incidente a si mesmo</span><span class="sxs-lookup"><span data-stu-id="5f256-114">Assign the incident to yourself</span></span>](#assign-incidents)
- [<span data-ttu-id="5f256-115">Resolvê-los</span><span class="sxs-lookup"><span data-stu-id="5f256-115">Resolve them</span></span>](#resolve-an-incident)
- [<span data-ttu-id="5f256-116">Definir sua classificação e determinação</span><span class="sxs-lookup"><span data-stu-id="5f256-116">Set its classification and determination</span></span>](#set-the-classification-and-determination)
- [<span data-ttu-id="5f256-117">Adicionar comentários</span><span class="sxs-lookup"><span data-stu-id="5f256-117">Add comments</span></span>](#add-comments)

<span data-ttu-id="5f256-118">Você pode gerenciar incidentes do **painel Gerenciar incidentes** para um incidente.</span><span class="sxs-lookup"><span data-stu-id="5f256-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="5f256-119">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="5f256-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Exemplo do painel Gerenciar incidentes de um incidente":::

<span data-ttu-id="5f256-121">Você pode exibir esse painel no link **Gerenciar incidentes** no:</span><span class="sxs-lookup"><span data-stu-id="5f256-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="5f256-122">Painel de propriedades de um incidente na fila de incidentes.</span><span class="sxs-lookup"><span data-stu-id="5f256-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="5f256-123">**Página** de resumo de um incidente.</span><span class="sxs-lookup"><span data-stu-id="5f256-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="5f256-124">Nos casos em que você deseja mover alertas de um incidente para outro, você também pode fazê-lo a partir da guia **Alertas,** criando um incidente maior ou menor que inclui todos os alertas relevantes.</span><span class="sxs-lookup"><span data-stu-id="5f256-124">In cases where you want to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="5f256-125">Editar o nome do incidente</span><span class="sxs-lookup"><span data-stu-id="5f256-125">Edit the incident name</span></span>

<span data-ttu-id="5f256-126">Microsoft 365 O Defender atribui automaticamente um nome com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias.</span><span class="sxs-lookup"><span data-stu-id="5f256-126">Microsoft 365 Defender automatically assigns a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="5f256-127">Isso permite que você entenda rapidamente o escopo do incidente.</span><span class="sxs-lookup"><span data-stu-id="5f256-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="5f256-128">Por exemplo: *incidente em vários estágios em vários pontos de extremidade relatados por várias fontes.*</span><span class="sxs-lookup"><span data-stu-id="5f256-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="5f256-129">Você pode editar o nome do incidente no campo **Nome do** incidente no **painel Gerenciar** incidentes.</span><span class="sxs-lookup"><span data-stu-id="5f256-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="5f256-130">Incidentes que existiam antes da adoção do recurso de nomenização automática de incidentes manterão seu nome.</span><span class="sxs-lookup"><span data-stu-id="5f256-130">Incidents that existed before the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="5f256-131">Adicionar marcas de incidente</span><span class="sxs-lookup"><span data-stu-id="5f256-131">Add incident tags</span></span>

<span data-ttu-id="5f256-132">Você pode adicionar marcas personalizadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com uma característica comum.</span><span class="sxs-lookup"><span data-stu-id="5f256-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="5f256-133">Posteriormente, você pode filtrar a fila de incidentes para todos os incidentes que contenham uma marca específica.</span><span class="sxs-lookup"><span data-stu-id="5f256-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="5f256-134">Ao começar a digitar, você tem a opção de selecionar em uma lista de marcas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="5f256-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="5f256-135">Atribuir incidentes</span><span class="sxs-lookup"><span data-stu-id="5f256-135">Assign incidents</span></span>

<span data-ttu-id="5f256-136">Para atribuir um incidente, selecione **Atribuir a mim**.</span><span class="sxs-lookup"><span data-stu-id="5f256-136">To assign an incident, select **Assign to me**.</span></span> <span data-ttu-id="5f256-137">Isso atribui a propriedade do incidente e todos os alertas associados a ele à sua conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="5f256-137">Doing so assigns ownership of the incident and all the alerts associated with it to your user account.</span></span>

<span data-ttu-id="5f256-138">Você pode obter uma lista de incidentes atribuídos a você filtrando a fila de incidentes.</span><span class="sxs-lookup"><span data-stu-id="5f256-138">You can get a list of incidents assigned to you by filtering the incident queue.</span></span> 

1. <span data-ttu-id="5f256-139">Na fila de incidentes, selecione **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="5f256-139">From the incident queue, select **Filters**.</span></span>
2. <span data-ttu-id="5f256-140">na seção **Atribuição de incidentes,** **desin selecione Selecionar tudo** e selecione Atribuído a **mim**.</span><span class="sxs-lookup"><span data-stu-id="5f256-140">in the **Incident assignment** section, clear **Select all** and select **Assigned to me**.</span></span>
3. <span data-ttu-id="5f256-141">Selecione **Aplicar** e feche o painel **Filtros.**</span><span class="sxs-lookup"><span data-stu-id="5f256-141">Select **Apply**, and then close the **Filters** pane.</span></span>

<span data-ttu-id="5f256-142">Em seguida, você pode salvar a URL resultante em seu navegador como um indicador para ver rapidamente a lista de incidentes atribuídos a você.</span><span class="sxs-lookup"><span data-stu-id="5f256-142">You can then save the resulting URL in your browser as a bookmark to quickly see the list of incidents assigned to you.</span></span>

## <a name="resolve-an-incident"></a><span data-ttu-id="5f256-143">Resolver um incidente</span><span class="sxs-lookup"><span data-stu-id="5f256-143">Resolve an incident</span></span>

<span data-ttu-id="5f256-144">Se o incidente tiver sido resolvido, selecione **Resolver incidentes** para mover a alternância para a direita.</span><span class="sxs-lookup"><span data-stu-id="5f256-144">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="5f256-145">Observe que a resolução de um incidente também resolve todos os alertas vinculados e ativos relacionados ao incidente.</span><span class="sxs-lookup"><span data-stu-id="5f256-145">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="5f256-146">Um incidente que não é resolvido é exibido como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="5f256-146">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="5f256-147">Definir a classificação e a determinação</span><span class="sxs-lookup"><span data-stu-id="5f256-147">Set the classification and determination</span></span>

<span data-ttu-id="5f256-148">A classificação de incidentes é se foi um alerta verdadeiro ou falso, que você configura no **campo Classificação.**</span><span class="sxs-lookup"><span data-stu-id="5f256-148">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="5f256-149">Se foi um alerta verdadeiro, você também deve especificar que tipo de ameaça era com o campo **Determinação.**</span><span class="sxs-lookup"><span data-stu-id="5f256-149">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="5f256-150">Especificar o tipo de ameaça ajuda sua equipe de segurança a ver padrões de ameaças e agir para defender sua organização deles.</span><span class="sxs-lookup"><span data-stu-id="5f256-150">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="5f256-151">Adicionar comentários</span><span class="sxs-lookup"><span data-stu-id="5f256-151">Add comments</span></span>

<span data-ttu-id="5f256-152">Você pode adicionar vários comentários a um incidente com o **campo Comentário.**</span><span class="sxs-lookup"><span data-stu-id="5f256-152">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="5f256-153">Cada comentário é adicionado aos eventos históricos do incidente.</span><span class="sxs-lookup"><span data-stu-id="5f256-153">Each comment gets added to the historical events of the incident.</span></span> <span data-ttu-id="5f256-154">Você pode ver os comentários e o histórico de um incidente no link **Comentários e** histórico na página **Resumo.**</span><span class="sxs-lookup"><span data-stu-id="5f256-154">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5f256-155">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5f256-155">Next steps</span></span>

<span data-ttu-id="5f256-156">Para novos incidentes, inicie sua [investigação.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="5f256-156">For new incidents, begin your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="5f256-157">Para incidentes no processo, continue sua [investigação.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="5f256-157">For in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="5f256-158">Para incidentes resolvidos, execute uma [revisão pós-incidente.](first-incident-post.md)</span><span class="sxs-lookup"><span data-stu-id="5f256-158">For resolved incidents, perform a [post-incident review](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5f256-159">Confira também</span><span class="sxs-lookup"><span data-stu-id="5f256-159">See also</span></span>

- [<span data-ttu-id="5f256-160">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="5f256-160">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="5f256-161">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="5f256-161">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="5f256-162">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="5f256-162">Investigate incidents</span></span>](investigate-incidents.md)
