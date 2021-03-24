---
title: Exibir e organizar a fila incidentes
ms.reviewer: ''
description: Consulte a lista de incidentes e saiba como aplicar filtros para limitar a lista e obter uma exibição mais focada.
keywords: exibir, organizar, incidentes, agregar, investigações, fila, ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f25189ac6550d9c3349e08f7e7ac685d4b8031fc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053267"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a><span data-ttu-id="25032-104">Exibir e organizar a fila do Microsoft Defender para Incidentes de Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="25032-104">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="25032-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="25032-105">**Applies to:**</span></span>
- [<span data-ttu-id="25032-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="25032-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="25032-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25032-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="25032-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="25032-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="25032-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="25032-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="25032-110">A **fila Incidentes** mostra uma coleção de incidentes que foram sinalizados de dispositivos em sua rede.</span><span class="sxs-lookup"><span data-stu-id="25032-110">The **Incidents queue** shows a collection of incidents that were flagged from devices in your network.</span></span> <span data-ttu-id="25032-111">Isso ajuda a classificar incidentes e criar uma decisão de resposta de segurança cibernética embasada.</span><span class="sxs-lookup"><span data-stu-id="25032-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>

<span data-ttu-id="25032-112">Por padrão, a fila exibe incidentes vistos nos últimos 30 dias, com o incidente mais recente sendo exibido na parte superior da lista, ajudando você a ver os incidentes mais recentes primeiro.</span><span class="sxs-lookup"><span data-stu-id="25032-112">By default, the queue displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="25032-113">Há várias opções que você pode escolher para personalizar o exibição de fila de incidentes.</span><span class="sxs-lookup"><span data-stu-id="25032-113">There are several options you can choose from to customize the Incidents queue view.</span></span> 

<span data-ttu-id="25032-114">Na navegação superior, você pode:</span><span class="sxs-lookup"><span data-stu-id="25032-114">On the top navigation you can:</span></span>
- <span data-ttu-id="25032-115">Personalizar colunas para adicionar ou remover colunas</span><span class="sxs-lookup"><span data-stu-id="25032-115">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="25032-116">Modificar o número de itens para exibição por página</span><span class="sxs-lookup"><span data-stu-id="25032-116">Modify the number of items to view per page</span></span>
- <span data-ttu-id="25032-117">Selecione os itens a mostrar por página</span><span class="sxs-lookup"><span data-stu-id="25032-117">Select the items to show per page</span></span>
- <span data-ttu-id="25032-118">Selecione em lotes os incidentes a atribuir</span><span class="sxs-lookup"><span data-stu-id="25032-118">Batch-select the incidents to assign</span></span> 
- <span data-ttu-id="25032-119">Navegar entre páginas</span><span class="sxs-lookup"><span data-stu-id="25032-119">Navigate between pages</span></span>
- <span data-ttu-id="25032-120">Aplicar filtros</span><span class="sxs-lookup"><span data-stu-id="25032-120">Apply filters</span></span>

![Imagem da fila de incidentes](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a><span data-ttu-id="25032-122">Classificar e filtrar a fila de incidentes</span><span class="sxs-lookup"><span data-stu-id="25032-122">Sort and filter the incidents queue</span></span>
<span data-ttu-id="25032-123">Você pode aplicar os filtros a seguir para limitar a lista de incidentes e obter uma exibição mais focada.</span><span class="sxs-lookup"><span data-stu-id="25032-123">You can apply the following filters to limit the list of incidents and get a more focused view.</span></span>

### <a name="severity"></a><span data-ttu-id="25032-124">Severity</span><span class="sxs-lookup"><span data-stu-id="25032-124">Severity</span></span>

<span data-ttu-id="25032-125">Gravidade do incidente</span><span class="sxs-lookup"><span data-stu-id="25032-125">Incident severity</span></span> | <span data-ttu-id="25032-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="25032-126">Description</span></span>
:---|:---
<span data-ttu-id="25032-127">Alto</span><span class="sxs-lookup"><span data-stu-id="25032-127">High</span></span> </br><span data-ttu-id="25032-128">(Vermelho)</span><span class="sxs-lookup"><span data-stu-id="25032-128">(Red)</span></span> | <span data-ttu-id="25032-129">Ameaças frequentemente associadas a ameaças persistentes avançadas (APT).</span><span class="sxs-lookup"><span data-stu-id="25032-129">Threats often associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="25032-130">Esses incidentes indicam um alto risco devido à gravidade dos danos que podem causar em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="25032-130">These incidents indicate a high risk due to the severity of damage they can inflict on devices.</span></span>
<span data-ttu-id="25032-131">Médio</span><span class="sxs-lookup"><span data-stu-id="25032-131">Medium</span></span> </br><span data-ttu-id="25032-132">(Laranja)</span><span class="sxs-lookup"><span data-stu-id="25032-132">(Orange)</span></span> | <span data-ttu-id="25032-133">Ameaças raramente observadas na organização, como alteração anômala do Registro, execução de arquivos suspeitos e comportamentos observados típicos de estágios de ataque.</span><span class="sxs-lookup"><span data-stu-id="25032-133">Threats rarely observed in the organization, such as anomalous registry change, execution of suspicious files, and observed behaviors typical of attack stages.</span></span>
<span data-ttu-id="25032-134">Baixo</span><span class="sxs-lookup"><span data-stu-id="25032-134">Low</span></span> </br><span data-ttu-id="25032-135">(Amarelo)</span><span class="sxs-lookup"><span data-stu-id="25032-135">(Yellow)</span></span> | <span data-ttu-id="25032-136">Ameaças associadas a malwares e ferramentas de hackers predominantes que não indicam necessariamente uma ameaça avançada direcionando a organização.</span><span class="sxs-lookup"><span data-stu-id="25032-136">Threats associated with prevalent malware and hack-tools that do not necessarily indicate an advanced threat targeting the organization.</span></span>
<span data-ttu-id="25032-137">Informações</span><span class="sxs-lookup"><span data-stu-id="25032-137">Informational</span></span> </br><span data-ttu-id="25032-138">(Cinza)</span><span class="sxs-lookup"><span data-stu-id="25032-138">(Grey)</span></span> | <span data-ttu-id="25032-139">Incidentes informacionais podem não ser considerados prejudiciais para a rede, mas podem ser bons para acompanhar.</span><span class="sxs-lookup"><span data-stu-id="25032-139">Informational incidents might not be considered harmful to the network but might be good to keep track of.</span></span>

## <a name="assigned-to"></a><span data-ttu-id="25032-140">Atribuído a</span><span class="sxs-lookup"><span data-stu-id="25032-140">Assigned to</span></span>
<span data-ttu-id="25032-141">Você pode optar por filtrar a lista selecionando não atribuir a ninguém ou os que estão atribuídos a você.</span><span class="sxs-lookup"><span data-stu-id="25032-141">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="category"></a><span data-ttu-id="25032-142">Categoria</span><span class="sxs-lookup"><span data-stu-id="25032-142">Category</span></span>
<span data-ttu-id="25032-143">Os incidentes são categorizados com base na descrição do estágio em que a cadeia de crimes de segurança cibernética está.</span><span class="sxs-lookup"><span data-stu-id="25032-143">Incidents are categorized based on the description of the stage by which the cybersecurity kill chain is in.</span></span> <span data-ttu-id="25032-144">Essa exibição ajuda o analista de ameaças a determinar a prioridade, a urgência e a estratégia de resposta correspondente a ser implantada com base no contexto.</span><span class="sxs-lookup"><span data-stu-id="25032-144">This view helps the threat analyst to determine priority, urgency, and corresponding response strategy to deploy based on context.</span></span>

### <a name="status"></a><span data-ttu-id="25032-145">Status</span><span class="sxs-lookup"><span data-stu-id="25032-145">Status</span></span>
<span data-ttu-id="25032-146">Você pode optar por limitar a lista de incidentes exibidos com base em seu status para ver quais estão ativos ou resolvidos.</span><span class="sxs-lookup"><span data-stu-id="25032-146">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="25032-147">Confidencialidade de dados</span><span class="sxs-lookup"><span data-stu-id="25032-147">Data sensitivity</span></span>
<span data-ttu-id="25032-148">Use este filtro para mostrar incidentes que contêm rótulos de sensibilidade.</span><span class="sxs-lookup"><span data-stu-id="25032-148">Use this filter to show incidents that contain sensitivity labels.</span></span>

## <a name="incident-naming"></a><span data-ttu-id="25032-149">Nomeação de incidente</span><span class="sxs-lookup"><span data-stu-id="25032-149">Incident naming</span></span>

<span data-ttu-id="25032-150">Para entender rapidamente o escopo do incidente, os nomes de incidentes são gerados automaticamente com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias.</span><span class="sxs-lookup"><span data-stu-id="25032-150">To understand the incident's scope at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span>

<span data-ttu-id="25032-151">Por exemplo: *incidente em vários estágios em vários pontos de extremidade relatados por várias fontes.*</span><span class="sxs-lookup"><span data-stu-id="25032-151">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="25032-152">Incidentes que existiam antes da adoção da nomenização automática de incidentes manterão seu nome.</span><span class="sxs-lookup"><span data-stu-id="25032-152">Incidents that existed prior the rollout of automatic incident naming will retain their name.</span></span>


## <a name="see-also"></a><span data-ttu-id="25032-153">Confira também</span><span class="sxs-lookup"><span data-stu-id="25032-153">See also</span></span>
- [<span data-ttu-id="25032-154">Fila de incidentes</span><span class="sxs-lookup"><span data-stu-id="25032-154">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="25032-155">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="25032-155">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="25032-156">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="25032-156">Investigate incidents</span></span>](investigate-incidents.md)

