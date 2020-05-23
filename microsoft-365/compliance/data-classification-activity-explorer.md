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
ms.openlocfilehash: 5cb6a8dbfa570b3b0e0d1ce39648d12050d2af81
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327837"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="f23dd-103">Começar a usar o gerenciador de atividades</span><span class="sxs-lookup"><span data-stu-id="f23dd-103">Get started with activity explorer</span></span>

<span data-ttu-id="f23dd-104">As guias visão geral de classificação de dados e explorador de conteúdo dão visibilidade ao conteúdo que foi descoberto e rotulado e mostra onde está esse conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f23dd-104">The data classification overview and content explorer tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="f23dd-105">O explorador de atividade arremata esse pacote de funcionalidade permitindo monitorar o que está sendo feito com o conteúdo rotulado.</span><span class="sxs-lookup"><span data-stu-id="f23dd-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="f23dd-106">O explorador de atividades fornece um modo de exibição histórica.</span><span class="sxs-lookup"><span data-stu-id="f23dd-106">Activity explorer provides a historical view.</span></span>

![Visão geral da captura de tela do Explorador de atividades](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="f23dd-108">Há mais de 30 filtros diferentes disponíveis para uso, alguns são:</span><span class="sxs-lookup"><span data-stu-id="f23dd-108">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="f23dd-109">intervalo de datas</span><span class="sxs-lookup"><span data-stu-id="f23dd-109">date range</span></span>
- <span data-ttu-id="f23dd-110">tipo de atividade</span><span class="sxs-lookup"><span data-stu-id="f23dd-110">activity type</span></span>
- <span data-ttu-id="f23dd-111">localização</span><span class="sxs-lookup"><span data-stu-id="f23dd-111">location</span></span>
- <span data-ttu-id="f23dd-112">usuário</span><span class="sxs-lookup"><span data-stu-id="f23dd-112">user</span></span>
- <span data-ttu-id="f23dd-113">rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="f23dd-113">sensitivity label</span></span>
- <span data-ttu-id="f23dd-114">rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="f23dd-114">retention label</span></span>
- <span data-ttu-id="f23dd-115">caminho do arquivo</span><span class="sxs-lookup"><span data-stu-id="f23dd-115">file path</span></span>
- <span data-ttu-id="f23dd-116">Política de DLP</span><span class="sxs-lookup"><span data-stu-id="f23dd-116">DLP policy</span></span>


## <a name="prerequisites"></a><span data-ttu-id="f23dd-117">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f23dd-117">Prerequisites</span></span>

<span data-ttu-id="f23dd-118">Toda conta que acessa e usa a classificação de dados deve ter uma licença atribuída a partir de uma destas assinaturas:</span><span class="sxs-lookup"><span data-stu-id="f23dd-118">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="f23dd-119">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="f23dd-119">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="f23dd-120">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="f23dd-120">Office 365 (E5)</span></span>
- <span data-ttu-id="f23dd-121">Complemento de Conformidade Avançada (E5)</span><span class="sxs-lookup"><span data-stu-id="f23dd-121">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="f23dd-122">Complemento Avançado de Inteligência contra Ameaças (E5)</span><span class="sxs-lookup"><span data-stu-id="f23dd-122">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="f23dd-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="f23dd-123">Permissions</span></span>

 <span data-ttu-id="f23dd-124">Para obter acesso à guia do explorador de atividades, é necessário atribuir uma conta à participação em qualquer uma dessas funções ou grupos de funções.</span><span class="sxs-lookup"><span data-stu-id="f23dd-124">In order to get access to the activity explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="f23dd-125">**Grupos de funções do Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="f23dd-125">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="f23dd-126">Administrador global</span><span class="sxs-lookup"><span data-stu-id="f23dd-126">Global administrator</span></span>
- <span data-ttu-id="f23dd-127">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="f23dd-127">Compliance administrator</span></span>
- <span data-ttu-id="f23dd-128">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="f23dd-128">Security administrator</span></span>
- <span data-ttu-id="f23dd-129">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="f23dd-129">Compliance data administrator</span></span>

## <a name="activity-type"></a><span data-ttu-id="f23dd-130">Tipo de atividade</span><span class="sxs-lookup"><span data-stu-id="f23dd-130">Activity type</span></span>

<span data-ttu-id="f23dd-131">O Microsoft 365 monitora e relata os tipos de atividades em todo o SharePoint Online e OneDrive como:</span><span class="sxs-lookup"><span data-stu-id="f23dd-131">Microsoft 365 monitors and reports on types of activities across SharePoint Online, and OneDrive like:</span></span>

- <span data-ttu-id="f23dd-132">rótulo foi aplicado</span><span class="sxs-lookup"><span data-stu-id="f23dd-132">label applied</span></span>
- <span data-ttu-id="f23dd-133">rótulo alterado (atualizado, regredido ou removido)</span><span class="sxs-lookup"><span data-stu-id="f23dd-133">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="f23dd-134">simulação de rotulação automática</span><span class="sxs-lookup"><span data-stu-id="f23dd-134">auto-labeling simulation</span></span>

<span data-ttu-id="f23dd-135">O vantagem de ficar sabendo que ações estão sendo tomadas com o conteúdo rotulado como confidencial é que você pode verificar se os controles que você já colocou em ação, tais como as [políticas de prevenção de perda de dados](data-loss-prevention-policies.md) estão sendo eficazes ou não.</span><span class="sxs-lookup"><span data-stu-id="f23dd-135">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention policies](data-loss-prevention-policies.md) are effective or not.</span></span> <span data-ttu-id="f23dd-136">Se elas não estiverem funcionando, ou se você descobrir algo inesperado, como um grande número de itens que foram rotulados `highly confidential` e regredidos `general`, você pode gerenciar suas diversas políticas e executar novas ações para restringir o comportamento indesejado.</span><span class="sxs-lookup"><span data-stu-id="f23dd-136">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="f23dd-137">O explorador de atividades não monitora atualmente as atividades de retenção do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f23dd-137">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="f23dd-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="f23dd-138">See also</span></span>
- [<span data-ttu-id="f23dd-139">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="f23dd-139">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="f23dd-140">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="f23dd-140">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="f23dd-141">Definições da entidade por tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="f23dd-141">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="f23dd-142">Visão geral de políticas de retenção</span><span class="sxs-lookup"><span data-stu-id="f23dd-142">Overview of retention policies</span></span>](retention-policies.md)
