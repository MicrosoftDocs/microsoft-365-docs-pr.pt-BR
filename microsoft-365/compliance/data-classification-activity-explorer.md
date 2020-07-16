---
title: Começar a usar o gerenciador de atividades
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
ms.openlocfilehash: 63ecb84c0ae658b0fd3463dba10d56059352910b
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126640"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="76caa-103">Começar a usar o gerenciador de atividades</span><span class="sxs-lookup"><span data-stu-id="76caa-103">Get started with activity explorer</span></span>

<span data-ttu-id="76caa-104">As guias visão geral de classificação de dados e explorador de conteúdo dão visibilidade ao conteúdo que foi descoberto e rotulado e mostra onde está esse conteúdo.</span><span class="sxs-lookup"><span data-stu-id="76caa-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="76caa-105">O explorador de atividade arremata esse pacote de funcionalidade permitindo monitorar o que está sendo feito com o conteúdo rotulado.</span><span class="sxs-lookup"><span data-stu-id="76caa-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="76caa-106">O explorador de atividades fornece um modo de exibição histórica.</span><span class="sxs-lookup"><span data-stu-id="76caa-106">Activity explorer provides a historical view.</span></span>

![Visão geral da captura de tela do Explorador de atividades](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="76caa-108">Há mais de 30 filtros diferentes disponíveis para uso, alguns são:</span><span class="sxs-lookup"><span data-stu-id="76caa-108">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="76caa-109">intervalo de datas</span><span class="sxs-lookup"><span data-stu-id="76caa-109">date range</span></span>
- <span data-ttu-id="76caa-110">tipo de atividade</span><span class="sxs-lookup"><span data-stu-id="76caa-110">activity type</span></span>
- <span data-ttu-id="76caa-111">localização</span><span class="sxs-lookup"><span data-stu-id="76caa-111">location</span></span>
- <span data-ttu-id="76caa-112">usuário</span><span class="sxs-lookup"><span data-stu-id="76caa-112">user</span></span>
- <span data-ttu-id="76caa-113">rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="76caa-113">sensitivity label</span></span>
- <span data-ttu-id="76caa-114">rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="76caa-114">retention label</span></span>
- <span data-ttu-id="76caa-115">caminho do arquivo</span><span class="sxs-lookup"><span data-stu-id="76caa-115">file path</span></span>
- <span data-ttu-id="76caa-116">Política de DLP</span><span class="sxs-lookup"><span data-stu-id="76caa-116">DLP policy</span></span>


## <a name="prerequisites"></a><span data-ttu-id="76caa-117">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="76caa-117">Prerequisites</span></span>

<span data-ttu-id="76caa-118">Toda conta que acessa e usa a classificação de dados deve ter uma licença atribuída a partir de uma destas assinaturas:</span><span class="sxs-lookup"><span data-stu-id="76caa-118">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="76caa-119">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="76caa-119">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="76caa-120">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="76caa-120">Office 365 (E5)</span></span>
- <span data-ttu-id="76caa-121">Complemento de Conformidade Avançada (E5)</span><span class="sxs-lookup"><span data-stu-id="76caa-121">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="76caa-122">Complemento Avançado de Inteligência contra Ameaças (E5)</span><span class="sxs-lookup"><span data-stu-id="76caa-122">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="76caa-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="76caa-123">Permissions</span></span>

 <span data-ttu-id="76caa-124">Para obter acesso à guia do explorador de atividades, é necessário atribuir uma conta à participação em qualquer uma dessas funções ou grupos de funções.</span><span class="sxs-lookup"><span data-stu-id="76caa-124">In order to get access to the activity explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="76caa-125">**Grupos de funções do Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="76caa-125">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="76caa-126">Administrador global</span><span class="sxs-lookup"><span data-stu-id="76caa-126">Global administrator</span></span>
- <span data-ttu-id="76caa-127">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="76caa-127">Compliance administrator</span></span>
- <span data-ttu-id="76caa-128">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="76caa-128">Security administrator</span></span>
- <span data-ttu-id="76caa-129">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="76caa-129">Compliance data administrator</span></span>

## <a name="activity-type"></a><span data-ttu-id="76caa-130">Tipo de atividade</span><span class="sxs-lookup"><span data-stu-id="76caa-130">Activity type</span></span>

<span data-ttu-id="76caa-131">O Microsoft 365 monitora e relata os tipos de atividades em todo o SharePoint Online e OneDrive como:</span><span class="sxs-lookup"><span data-stu-id="76caa-131">Microsoft 365 monitors and reports on types of activities across SharePoint Online, and OneDrive like:</span></span>

- <span data-ttu-id="76caa-132">rótulo foi aplicado</span><span class="sxs-lookup"><span data-stu-id="76caa-132">label applied</span></span>
- <span data-ttu-id="76caa-133">rótulo alterado (atualizado, regredido ou removido)</span><span class="sxs-lookup"><span data-stu-id="76caa-133">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="76caa-134">simulação de rotulação automática</span><span class="sxs-lookup"><span data-stu-id="76caa-134">auto-labeling simulation</span></span>

<span data-ttu-id="76caa-135">O vantagem de ficar sabendo que ações estão sendo tomadas com o conteúdo rotulado como confidencial é que você pode verificar se os controles que você já colocou em ação, tais como as [políticas de prevenção de perda de dados](data-loss-prevention-policies.md) estão sendo eficazes ou não.</span><span class="sxs-lookup"><span data-stu-id="76caa-135">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="76caa-136">Se elas não estiverem funcionando, ou se você descobrir algo inesperado, como um grande número de itens que foram rotulados `highly confidential` e regredidos `general`, você pode gerenciar suas diversas políticas e executar novas ações para restringir o comportamento indesejado.</span><span class="sxs-lookup"><span data-stu-id="76caa-136">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="76caa-137">O explorador de atividades não monitora atualmente as atividades de retenção do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="76caa-137">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="76caa-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="76caa-138">See also</span></span>
- [<span data-ttu-id="76caa-139">Saiba mais sobre rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="76caa-139">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="76caa-140">Saiba mais sobre as políticas de retenção e os rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="76caa-140">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="76caa-141">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="76caa-141">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

