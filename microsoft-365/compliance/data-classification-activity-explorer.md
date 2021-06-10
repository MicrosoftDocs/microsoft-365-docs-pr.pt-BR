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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: O explorador de atividade dá o toque final na funcionalidade do recurso de classificação de dados, permitindo que você veja e filtre as ações que os usuários estão executando no conteúdo rotulado.
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114003"
---
# <a name="get-started-with-activity-explorer"></a><span data-ttu-id="e63c6-103">Começar a usar o gerenciador de atividades</span><span class="sxs-lookup"><span data-stu-id="e63c6-103">Get started with activity explorer</span></span>

<span data-ttu-id="e63c6-104">A visão geral [](data-classification-content-explorer.md) da [classificação](data-classification-overview.md) de dados e as guias do explorador de conteúdo dão visibilidade de qual conteúdo foi descoberto e rotulado e onde está esse conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e63c6-104">The [data classification overview](data-classification-overview.md) and [content explorer](data-classification-content-explorer.md) tabs give you visibility into what content has been discovered and labeled, and where that content is.</span></span> <span data-ttu-id="e63c6-105">O explorador de atividade arremata esse pacote de funcionalidade permitindo monitorar o que está sendo feito com o conteúdo rotulado.</span><span class="sxs-lookup"><span data-stu-id="e63c6-105">Activity explorer rounds out this suite of functionality by allowing you to monitor what's being done with your labeled content.</span></span> <span data-ttu-id="e63c6-106">O explorador de atividades fornece uma exibição histórica das atividades em seu conteúdo rotulado.</span><span class="sxs-lookup"><span data-stu-id="e63c6-106">Activity explorer provides a historical view of activities on your labeled content.</span></span> <span data-ttu-id="e63c6-107">As informações de atividade são coletadas Microsoft 365 logs de auditoria unificados, transformados e disponibilizados na interface do usuário do Explorador de Atividades.</span><span class="sxs-lookup"><span data-stu-id="e63c6-107">The activity information is collected from the Microsoft 365 unified audit logs, transformed and made available in the Activity explorer UI.</span></span> 

![Visão geral da captura de tela do Explorador de atividades](../media/data-classification-activity-explorer-1.png)

<span data-ttu-id="e63c6-109">Há mais de 30 filtros diferentes disponíveis para uso, alguns são:</span><span class="sxs-lookup"><span data-stu-id="e63c6-109">There are over 30 different filters available for use, some are:</span></span>

- <span data-ttu-id="e63c6-110">intervalo de datas</span><span class="sxs-lookup"><span data-stu-id="e63c6-110">date range</span></span>
- <span data-ttu-id="e63c6-111">tipo de atividade</span><span class="sxs-lookup"><span data-stu-id="e63c6-111">activity type</span></span>
- <span data-ttu-id="e63c6-112">localização</span><span class="sxs-lookup"><span data-stu-id="e63c6-112">location</span></span>
- <span data-ttu-id="e63c6-113">usuário</span><span class="sxs-lookup"><span data-stu-id="e63c6-113">user</span></span>
- <span data-ttu-id="e63c6-114">rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="e63c6-114">sensitivity label</span></span>
- <span data-ttu-id="e63c6-115">rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="e63c6-115">retention label</span></span>
- <span data-ttu-id="e63c6-116">caminho do arquivo</span><span class="sxs-lookup"><span data-stu-id="e63c6-116">file path</span></span>
- <span data-ttu-id="e63c6-117">Política de DLP</span><span class="sxs-lookup"><span data-stu-id="e63c6-117">DLP policy</span></span>



## <a name="prerequisites"></a><span data-ttu-id="e63c6-118">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e63c6-118">Prerequisites</span></span>

<span data-ttu-id="e63c6-119">Toda conta que acessa e usa a classificação de dados deve ter uma licença atribuída a partir de uma destas assinaturas:</span><span class="sxs-lookup"><span data-stu-id="e63c6-119">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="e63c6-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="e63c6-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="e63c6-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="e63c6-121">Office 365 (E5)</span></span>
- <span data-ttu-id="e63c6-122">Complemento de Conformidade Avançada (E5)</span><span class="sxs-lookup"><span data-stu-id="e63c6-122">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="e63c6-123">Complemento Avançado de Inteligência contra Ameaças (E5)</span><span class="sxs-lookup"><span data-stu-id="e63c6-123">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="e63c6-124">Microsoft 365 E5/A5 Proteção e Governança da Informação</span><span class="sxs-lookup"><span data-stu-id="e63c6-124">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="e63c6-125">Conformidade Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="e63c6-125">Microsoft 365 E5/A5 Compliance</span></span>

### <a name="permissions"></a><span data-ttu-id="e63c6-126">Permissões</span><span class="sxs-lookup"><span data-stu-id="e63c6-126">Permissions</span></span>

 <span data-ttu-id="e63c6-127">Para obter acesso à guia explorador de atividades, uma conta deve ser atribuída explicitamente à associação em qualquer um desses grupos de função ou explicitamente concedida à função.</span><span class="sxs-lookup"><span data-stu-id="e63c6-127">In order to get access to the activity explorer tab, an account must be explicitly assigned membership in any one of these role groups or explicitly granted the role.</span></span>

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

<span data-ttu-id="e63c6-128">**Grupos de funções do Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="e63c6-128">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="e63c6-129">Administrador global</span><span class="sxs-lookup"><span data-stu-id="e63c6-129">Global administrator</span></span>
- <span data-ttu-id="e63c6-130">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="e63c6-130">Compliance administrator</span></span>
- <span data-ttu-id="e63c6-131">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="e63c6-131">Security administrator</span></span>
- <span data-ttu-id="e63c6-132">Administrador de dados de conformidade</span><span class="sxs-lookup"><span data-stu-id="e63c6-132">Compliance data administrator</span></span>

<span data-ttu-id="e63c6-133">**Microsoft 365 funções**</span><span class="sxs-lookup"><span data-stu-id="e63c6-133">**Microsoft 365 roles**</span></span>

- <span data-ttu-id="e63c6-134">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="e63c6-134">Compliance administrator</span></span>
- <span data-ttu-id="e63c6-135">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="e63c6-135">Security administrator</span></span>

## <a name="activity-types"></a><span data-ttu-id="e63c6-136">Tipos de atividade</span><span class="sxs-lookup"><span data-stu-id="e63c6-136">Activity types</span></span>

<span data-ttu-id="e63c6-137">O explorador de atividades coleta informações de atividade dos logs de auditoria em várias fontes de atividades.</span><span class="sxs-lookup"><span data-stu-id="e63c6-137">Activity explorer gathers activity information from the audit logs on multiple sources of activities.</span></span> <span data-ttu-id="e63c6-138">Para obter informações mais detalhadas sobre qual atividade de rotulagem o torna no Explorador de Atividades, consulte [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).</span><span class="sxs-lookup"><span data-stu-id="e63c6-138">For more detailed information on what labeling activity makes it to Activity explorer, see [Labeling events available in Activity explorer](data-classification-activity-explorer-available-events.md).</span></span>

<span data-ttu-id="e63c6-139">**Atividades de** rótulo  de sensibilidade e atividades de rotulagem de retenção de aplicativos nativos do Office, do add-in da Proteção de Informações do Azure, SharePoint Online, Exchange Online (somente rótulos de sensibilidade) e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e63c6-139">**Sensitivity label activities** and **Retention labeling activities** from Office native applications, Azure Information Protection add-in, SharePoint Online, Exchange Online (sensitivity labels only) and OneDrive.</span></span> <span data-ttu-id="e63c6-140">Alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="e63c6-140">Some examples are:</span></span>

- <span data-ttu-id="e63c6-141">rótulo foi aplicado</span><span class="sxs-lookup"><span data-stu-id="e63c6-141">label applied</span></span>
- <span data-ttu-id="e63c6-142">rótulo alterado (atualizado, regredido ou removido)</span><span class="sxs-lookup"><span data-stu-id="e63c6-142">label changed (upgraded, downgraded, or removed)</span></span>
- <span data-ttu-id="e63c6-143">simulação de rotulação automática</span><span class="sxs-lookup"><span data-stu-id="e63c6-143">auto-labeling simulation</span></span>
- <span data-ttu-id="e63c6-144">leitura de arquivo</span><span class="sxs-lookup"><span data-stu-id="e63c6-144">file read</span></span> 

<span data-ttu-id="e63c6-145">**Scanner e clientes AIP (Proteção de Informações do Azure)**</span><span class="sxs-lookup"><span data-stu-id="e63c6-145">**Azure Information Protection (AIP) scanner and AIP clients**</span></span>

- <span data-ttu-id="e63c6-146">proteção aplicada</span><span class="sxs-lookup"><span data-stu-id="e63c6-146">protection applied</span></span>
- <span data-ttu-id="e63c6-147">protection changed</span><span class="sxs-lookup"><span data-stu-id="e63c6-147">protection changed</span></span>
- <span data-ttu-id="e63c6-148">protection removed</span><span class="sxs-lookup"><span data-stu-id="e63c6-148">protection removed</span></span>
- <span data-ttu-id="e63c6-149">arquivos descobertos</span><span class="sxs-lookup"><span data-stu-id="e63c6-149">files discovered</span></span> 

<span data-ttu-id="e63c6-150">O Explorador de Atividades também coleta a política **de DLP** que corresponde a eventos de Exchange Online, SharePoint Online, OneDrive, chat e canal do Teams (visualização), pastas e bibliotecas do SharePoint local e compartilhamentos de arquivos locais e dispositivos Windows 10 via **DLP (prevenção** contra perda de dados do ponto de extremidade).</span><span class="sxs-lookup"><span data-stu-id="e63c6-150">Activity explorer also gathers **DLP policy matches** events from Exchange Online, SharePoint Online, OneDrive, Teams Chat and Channel (preview), on-premises SharePoint folders and libraries, and on-premises file shares, and Windows 10 devices via **Endpoint data loss prevention (DLP)**.</span></span> <span data-ttu-id="e63c6-151">Alguns exemplos de eventos de Windows 10 dispositivos são o arquivo:</span><span class="sxs-lookup"><span data-stu-id="e63c6-151">Some examples events from Windows 10 devices are file:</span></span>

- <span data-ttu-id="e63c6-152">exclusões</span><span class="sxs-lookup"><span data-stu-id="e63c6-152">deletions</span></span>
- <span data-ttu-id="e63c6-153">criações</span><span class="sxs-lookup"><span data-stu-id="e63c6-153">creations</span></span>
- <span data-ttu-id="e63c6-154">copiado para área de transferência</span><span class="sxs-lookup"><span data-stu-id="e63c6-154">copied to clipboard</span></span>
- <span data-ttu-id="e63c6-155">modificadas</span><span class="sxs-lookup"><span data-stu-id="e63c6-155">modified</span></span>
- <span data-ttu-id="e63c6-156">leitura</span><span class="sxs-lookup"><span data-stu-id="e63c6-156">read</span></span>
- <span data-ttu-id="e63c6-157">impresso</span><span class="sxs-lookup"><span data-stu-id="e63c6-157">printed</span></span>
- <span data-ttu-id="e63c6-158">renomeado</span><span class="sxs-lookup"><span data-stu-id="e63c6-158">renamed</span></span>
- <span data-ttu-id="e63c6-159">copiado para compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="e63c6-159">copied to network share</span></span>
- <span data-ttu-id="e63c6-160">acessado por aplicativo não reatado</span><span class="sxs-lookup"><span data-stu-id="e63c6-160">accessed by unallowed app</span></span> 

<span data-ttu-id="e63c6-161">O valor de entender quais ações estão sendo tomadas com seu conteúdo rotulado confidenciais é que [](dlp-learn-about-dlp.md) você pode ver se os controles que você já colocou em vigor, como a prevenção de perda de dados são efetivos ou não.</span><span class="sxs-lookup"><span data-stu-id="e63c6-161">The value of understanding what actions are being taken with your sensitive labeled content is that you can see if the controls that you have already put into place, such as [data loss prevention](dlp-learn-about-dlp.md) are effective or not.</span></span> <span data-ttu-id="e63c6-162">Se elas não estiverem funcionando, ou se você descobrir algo inesperado, como um grande número de itens que foram rotulados `highly confidential` e regredidos `general`, você pode gerenciar suas diversas políticas e executar novas ações para restringir o comportamento indesejado.</span><span class="sxs-lookup"><span data-stu-id="e63c6-162">If not, or if you discover something unexpected, such as a large number of items that are labeled `highly confidential` and are downgraded `general`, you can manage your various policies and take new actions to restrict the undesired behavior.</span></span>

> [!NOTE]
> <span data-ttu-id="e63c6-163">O explorador de atividades não monitora atualmente as atividades de retenção do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e63c6-163">Activity explorer doesn't currently monitor retention activities for Exchange Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="e63c6-164">Confira também</span><span class="sxs-lookup"><span data-stu-id="e63c6-164">See also</span></span>

- [<span data-ttu-id="e63c6-165">Saiba mais sobre rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="e63c6-165">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="e63c6-166">Saiba mais sobre as políticas de retenção e os rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="e63c6-166">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="e63c6-167">Aprenda sobre os tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="e63c6-167">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="e63c6-168">Saiba mais sobre a classificação de dados</span><span class="sxs-lookup"><span data-stu-id="e63c6-168">Learn about data classification</span></span>](data-classification-overview.md)
