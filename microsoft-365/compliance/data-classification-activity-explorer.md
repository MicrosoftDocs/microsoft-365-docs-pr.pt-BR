---
title: Usando o explorador de atividade de classificação de dados
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: O explorador de atividade dá o toque final na funcionalidade do recurso de classificação de dados, permitindo que você veja e filtre as ações que os usuários estão executando no conteúdo rotulado.
ms.openlocfilehash: f80ce94433028b2434d442a364c336060b730d94
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076748"
---
# <a name="view-activity-on-your-labeled-content-preview"></a><span data-ttu-id="be0bf-103">Exibir atividade do seu conteúdo rotulado (visualização)</span><span class="sxs-lookup"><span data-stu-id="be0bf-103">View activity on your labeled content (preview)</span></span>

<span data-ttu-id="be0bf-104">As guias visão geral de classificação de dados e explorador de conteúdo dão visibilidade ao conteúdo que foi descoberto e rotulado e mostra onde está esse conteúdo.</span><span class="sxs-lookup"><span data-stu-id="be0bf-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="be0bf-105">O explorador de atividade arremata esse pacote de funcionalidade permitindo monitorar o que está sendo feito com o conteúdo rotulado.</span><span class="sxs-lookup"><span data-stu-id="be0bf-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="be0bf-106">O explorador de atividades fornece um modo de exibição histórica.</span><span class="sxs-lookup"><span data-stu-id="be0bf-106">Activity explorer provides a historical view.</span></span>

![Visão geral da captura de tela do Explorador de atividades](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="be0bf-108">Você pode filtrar os dados de acordo com:</span><span class="sxs-lookup"><span data-stu-id="be0bf-108">You can filter the data by:</span></span>

- <span data-ttu-id="be0bf-109">intervalo de datas</span><span class="sxs-lookup"><span data-stu-id="be0bf-109">date range</span></span>
- <span data-ttu-id="be0bf-110">tipo de atividade</span><span class="sxs-lookup"><span data-stu-id="be0bf-110">activity type</span></span>
- <span data-ttu-id="be0bf-111">localização</span><span class="sxs-lookup"><span data-stu-id="be0bf-111">location</span></span>
- <span data-ttu-id="be0bf-112">usuário</span><span class="sxs-lookup"><span data-stu-id="be0bf-112">user</span></span>
- <span data-ttu-id="be0bf-113">rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="be0bf-113">sensitivity label</span></span>
- <span data-ttu-id="be0bf-114">rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="be0bf-114">retention label</span></span>


<span data-ttu-id="be0bf-115">Você pode exibir os dados como uma lista ou como um gráfico de barras.</span><span class="sxs-lookup"><span data-stu-id="be0bf-115">You can view the data either as a list or a bar graph.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="be0bf-116">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="be0bf-116">Prerequisites</span></span>

<span data-ttu-id="be0bf-117">Toda conta que acessa e usa o explorador de atividades deve ter uma licença atribuída a partir de uma destas assinaturas:</span><span class="sxs-lookup"><span data-stu-id="be0bf-117">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="be0bf-118">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="be0bf-118">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="be0bf-119">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="be0bf-119">Office 365 (E5)</span></span>
- <span data-ttu-id="be0bf-120">Complemento de Conformidade Avançada (E5)</span><span class="sxs-lookup"><span data-stu-id="be0bf-120">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="be0bf-121">Complemento Avançado de Inteligência contra Ameaças (E5)</span><span class="sxs-lookup"><span data-stu-id="be0bf-121">Advanced Threat Intelligence (E5) add-on</span></span>

## <a name="activity-type"></a><span data-ttu-id="be0bf-122">Tipo de atividade</span><span class="sxs-lookup"><span data-stu-id="be0bf-122">Activity type</span></span>

<span data-ttu-id="be0bf-123">O Microsoft 365 monitora e relata 12 tipos de atividades em todo o SharePoint Online, OneDrive e pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="be0bf-123">Microsoft 365 monitors and reports on 12 types of activities across SharePoint Online, OneDrive and endpoints.</span></span> <span data-ttu-id="be0bf-124">Os pontos de extremidade são dispositivos de usuário que executam o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="be0bf-124">Endpoints are user devices running Windows 10.</span></span>

- <span data-ttu-id="be0bf-125">Arquivo foi criado</span><span class="sxs-lookup"><span data-stu-id="be0bf-125">File created</span></span>
- <span data-ttu-id="be0bf-126">Arquivo foi modificado</span><span class="sxs-lookup"><span data-stu-id="be0bf-126">File modified</span></span>
- <span data-ttu-id="be0bf-127">Arquivo foi renomeado</span><span class="sxs-lookup"><span data-stu-id="be0bf-127">File renamed</span></span>
- <span data-ttu-id="be0bf-128">Arquivo foi copiado para a nuvem</span><span class="sxs-lookup"><span data-stu-id="be0bf-128">File copied to cloud</span></span>
- <span data-ttu-id="be0bf-129">Arquivo foi acessado por aplicativo que não tem permissão de acesso</span><span class="sxs-lookup"><span data-stu-id="be0bf-129">File accessed by unallowed app</span></span>
- <span data-ttu-id="be0bf-130">Arquivo foi impresso</span><span class="sxs-lookup"><span data-stu-id="be0bf-130">File printed</span></span>
- <span data-ttu-id="be0bf-131">Arquivo foi copiado para mídia removível</span><span class="sxs-lookup"><span data-stu-id="be0bf-131">File copied to removable media</span></span>
- <span data-ttu-id="be0bf-132">Arquivo copiado ser compartilhado na rede</span><span class="sxs-lookup"><span data-stu-id="be0bf-132">File copied to network share</span></span>
- <span data-ttu-id="be0bf-133">Arquivo foi lido</span><span class="sxs-lookup"><span data-stu-id="be0bf-133">File read</span></span>
- <span data-ttu-id="be0bf-134">Arquivo foi copiado para a área de transferência</span><span class="sxs-lookup"><span data-stu-id="be0bf-134">file copied to clipboard</span></span>
- <span data-ttu-id="be0bf-135">Rótulo foi aplicado</span><span class="sxs-lookup"><span data-stu-id="be0bf-135">Label applied</span></span>
- <span data-ttu-id="be0bf-136">Rótulo foi alterado (atualizado, regredido ou removido)</span><span class="sxs-lookup"><span data-stu-id="be0bf-136">Label changed (upgraded, downgraded, or removed)</span></span>

<span data-ttu-id="be0bf-137">O vantagem de ficar sabendo que ações estão sendo tomadas com o conteúdo rotulado como confidencial é que você pode verificar se os controles que você já colocou em ação, tais como as [políticas de prevenção de perda de dados](data-loss-prevention-policies.md) estão sendo eficazes ou não.</span><span class="sxs-lookup"><span data-stu-id="be0bf-137">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="be0bf-138">Se elas não estiverem funcionando, ou se você descobrir algo inesperado, como um grande número de itens que foram rotulados `highly confidential` e regredidos `general`, você pode gerenciar suas diversas políticas e executar novas ações para restringir o comportamento indesejado.</span><span class="sxs-lookup"><span data-stu-id="be0bf-138">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

<span data-ttu-id="be0bf-139">Depois de definir os filtros, você poderá:</span><span class="sxs-lookup"><span data-stu-id="be0bf-139">Once your filters are set, you can:</span></span>

- <span data-ttu-id="be0bf-140">Passe o mouse sobre um segmento do gráfico de barras para ver o número de itens que se encontram nessa categoria ![imagem do explorador de atividade ao passar o mouse](../media/data-classification-activity-explorer-hover-over-2.png)</span><span class="sxs-lookup"><span data-stu-id="be0bf-140">hover over a segment of the bar chart to see the number of items that fall into that category ![activity explorer hover over](../media/data-classification-activity-explorer-hover-over-2.png)</span></span>
- <span data-ttu-id="be0bf-141">exportar os dados</span><span class="sxs-lookup"><span data-stu-id="be0bf-141">export the data</span></span>
- <span data-ttu-id="be0bf-142">selecione um determinado item na lista e exiba os detalhes da ação no submenu</span><span class="sxs-lookup"><span data-stu-id="be0bf-142">select any given item from the list and view the details of the action in the fly-out</span></span>

![detalhes do submenu do explorador de atividade](../media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a><span data-ttu-id="be0bf-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="be0bf-144">See also</span></span>
- [<span data-ttu-id="be0bf-145">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="be0bf-145">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="be0bf-146">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="be0bf-146">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="be0bf-147">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="be0bf-147">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="be0bf-148">Visão geral de políticas de retenção</span><span class="sxs-lookup"><span data-stu-id="be0bf-148">Overview of retention policies</span></span>](retention-policies.md)
