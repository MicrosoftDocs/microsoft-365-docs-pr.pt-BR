---
title: Investigar alertas do Microsoft Defender para Pontos de Extremidade
description: Use as opções de investigação para obter detalhes sobre alertas que afetam sua rede, o que significam e como resolvê-los.
keywords: investigar, investigação, dispositivos, dispositivo, fila de alertas, painel, endereço IP, arquivo, envio, envios, análise profunda, linha do tempo, pesquisa, domínio, URL, IP
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 626be9e949170fcda1f0bcf2a88e1b9780bbe764
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841085"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="208bd-104">Investigar alertas no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="208bd-104">Investigate alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="208bd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="208bd-105">**Applies to:**</span></span>
- [<span data-ttu-id="208bd-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="208bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="208bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="208bd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="208bd-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="208bd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="208bd-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="208bd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

<span data-ttu-id="208bd-110">Investigue alertas que estão afetando sua rede, entenda o que significam e como resolvê-los.</span><span class="sxs-lookup"><span data-stu-id="208bd-110">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>

<span data-ttu-id="208bd-111">Selecione um alerta na fila de alertas para ir para a página de alerta.</span><span class="sxs-lookup"><span data-stu-id="208bd-111">Select an alert from the alerts queue to go to alert page.</span></span> <span data-ttu-id="208bd-112">Essa exibição contém o título do alerta, os ativos afetados, o painel de detalhes e o texto do alerta.</span><span class="sxs-lookup"><span data-stu-id="208bd-112">This view contains the alert title, the affected assets, the details side pane, and the alert story.</span></span>

<span data-ttu-id="208bd-113">Na página de alerta, comece sua investigação selecionando os ativos afetados ou qualquer uma das entidades sob a exibição da árvore de histórias de alerta.</span><span class="sxs-lookup"><span data-stu-id="208bd-113">From the alert page, begin your investigation by selecting the affected assets or any of the entities under the alert story tree view.</span></span> <span data-ttu-id="208bd-114">O painel de detalhes preenche automaticamente com mais informações sobre o que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="208bd-114">The details pane automatically populates with further information about what you selected.</span></span> <span data-ttu-id="208bd-115">Para ver que tipo de informação você pode exibir aqui, leia [Review alerts in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/review-alerts).</span><span class="sxs-lookup"><span data-stu-id="208bd-115">To see what kind of information you can view here, read [Review alerts in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/review-alerts).</span></span>

## <a name="investigate-using-the-alert-story"></a><span data-ttu-id="208bd-116">Investigar usando o artigo de alerta</span><span class="sxs-lookup"><span data-stu-id="208bd-116">Investigate using the alert story</span></span>

<span data-ttu-id="208bd-117">O story de alerta detalha por que o alerta foi disparado, eventos relacionados que aconteceram antes e depois, bem como outras entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="208bd-117">The alert story details why the alert was triggered, related events that happened before and after, as well as other related entities.</span></span>

<span data-ttu-id="208bd-118">As entidades são clicáveis e todas as entidades que não são um alerta podem ser expandidas usando o ícone de expansão no lado direito do cartão dessa entidade.</span><span class="sxs-lookup"><span data-stu-id="208bd-118">Entities are clickable and every entity that isn't an alert is expandable using the expand icon on the right side of that entity's card.</span></span> <span data-ttu-id="208bd-119">A entidade em foco será indicada por uma faixa azul no lado esquerdo do cartão dessa entidade, com o alerta no título em foco inicialmente.</span><span class="sxs-lookup"><span data-stu-id="208bd-119">The entity in focus will be indicated by a blue stripe to the left side of that entity's card, with the alert in the title being in focus at first.</span></span>

<span data-ttu-id="208bd-120">Expanda entidades para exibir detalhes rapidamente.</span><span class="sxs-lookup"><span data-stu-id="208bd-120">Expand entities to view details at a glance.</span></span> <span data-ttu-id="208bd-121">Selecionar uma entidade alterna o contexto do painel de detalhes para essa entidade e permitirá que você revise mais informações, bem como gerencie essa entidade.</span><span class="sxs-lookup"><span data-stu-id="208bd-121">Selecting an entity will switch the context of the details pane to this entity, and will allow you to review further information, as well as manage that entity.</span></span> <span data-ttu-id="208bd-122">Selecionar *...* à direita do cartão de entidade revelará todas as ações disponíveis para essa entidade.</span><span class="sxs-lookup"><span data-stu-id="208bd-122">Selecting *...* to the right of the entity card will reveal all actions available for that entity.</span></span> <span data-ttu-id="208bd-123">Essas mesmas ações aparecem no painel de detalhes quando essa entidade está em foco.</span><span class="sxs-lookup"><span data-stu-id="208bd-123">These same actions appear in the details pane when that entity is in focus.</span></span>

> [!NOTE]
> <span data-ttu-id="208bd-124">A seção de texto do alerta pode conter mais de um alerta, com alertas adicionais relacionados à mesma árvore de execução que aparece antes ou depois do alerta selecionado.</span><span class="sxs-lookup"><span data-stu-id="208bd-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

![Um exemplo de um artigo de alerta com um alerta em foco e alguns cartões expandidos](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a><span data-ttu-id="208bd-126">Tomar medidas do painel de detalhes</span><span class="sxs-lookup"><span data-stu-id="208bd-126">Take action from the details pane</span></span>

<span data-ttu-id="208bd-127">Depois de selecionar uma entidade de interesse, o painel de detalhes mudará para exibir informações sobre o tipo de  entidade selecionado, informações históricas quando estiver disponível e oferecer controles para tomar medidas nessa entidade diretamente na página de alerta.</span><span class="sxs-lookup"><span data-stu-id="208bd-127">Once you've selected an entity of interest, the details pane will change to display information about the selected entity type, historic information when it's available, and offer controls to **take action** on this entity directly from the alert page.</span></span>

<span data-ttu-id="208bd-128">Depois de terminar de investigar, volte para o alerta que você começou com, marque o status do alerta como **Resolvido** e classifique-o como alerta **False** ou **True.**</span><span class="sxs-lookup"><span data-stu-id="208bd-128">Once you're done investigating, go back to the alert you started with, mark the alert's status as **Resolved** and classify it as either **False alert** or **True alert**.</span></span> <span data-ttu-id="208bd-129">Classificar alertas ajuda a ajustar esse recurso para fornecer alertas mais verdadeiros e menos alertas falsos.</span><span class="sxs-lookup"><span data-stu-id="208bd-129">Classifying alerts helps tune this capability to provide more true alerts and less false alerts.</span></span>

<span data-ttu-id="208bd-130">Se você classificá-lo como um alerta verdadeiro, também poderá selecionar uma determinação, conforme mostrado na imagem abaixo.</span><span class="sxs-lookup"><span data-stu-id="208bd-130">If you classify it as a true alert, you can also select a determination, as shown in the image below.</span></span>

![Um trecho do painel de detalhes com um alerta resolvido e o drop-down de determinação expandido](images/alert-details-resolved-true.png)

<span data-ttu-id="208bd-132">Se você estiver enfrentando um alerta falso com um aplicativo de linha de negócios, crie uma regra de supressão para evitar esse tipo de alerta no futuro.</span><span class="sxs-lookup"><span data-stu-id="208bd-132">If you are experiencing a false alert with a line-of-business application, create a suppression rule to avoid this type of alert in the future.</span></span>

![ações e classificação no painel de detalhes com a regra de supressão realçada](images/alert-false-suppression-rule.png)

> [!TIP]
> <span data-ttu-id="208bd-134">Se você estiver enfrentando problemas não descritos acima, use o botão para fornecer 🙂 comentários ou abrir um tíquete de suporte.</span><span class="sxs-lookup"><span data-stu-id="208bd-134">If you're experiencing any issues not described above, use the 🙂 button to provide feedback or open a support ticket.</span></span>


## <a name="related-topics"></a><span data-ttu-id="208bd-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="208bd-135">Related topics</span></span>
- [<span data-ttu-id="208bd-136">Exibir e organizar a fila de alertas do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="208bd-136">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="208bd-137">Gerenciar alertas do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="208bd-137">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="208bd-138">Investigar um arquivo associado a um alerta do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="208bd-138">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="208bd-139">Investigar dispositivos na lista Defender para Dispositivos de Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="208bd-139">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="208bd-140">Investigar um endereço IP associado a um alerta do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="208bd-140">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="208bd-141">Investigar um domínio associado a um alerta do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="208bd-141">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="208bd-142">Investigar uma conta de usuário no Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="208bd-142">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)


