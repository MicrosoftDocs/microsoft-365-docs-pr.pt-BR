---
title: Criar indicadores
ms.reviewer: ''
description: Crie indicadores para um hash de arquivo, endereço IP, URLs ou domínios que definem a detecção, a prevenção e a exclusão de entidades.
keywords: gerenciar, permitido, bloqueado, bloquear, limpar, mal-intencionado, hash de arquivo, endereço ip, urls, domínio
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d54ab8eaa1e17be82752c480c963d3a24af56389
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187572"
---
# <a name="create-indicators"></a><span data-ttu-id="6c60f-104">Criar indicadores</span><span class="sxs-lookup"><span data-stu-id="6c60f-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6c60f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6c60f-105">**Applies to:**</span></span>
- [<span data-ttu-id="6c60f-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6c60f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6c60f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c60f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="6c60f-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="6c60f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6c60f-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="6c60f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="6c60f-110">O indicador de correspondência de comprometimento (IoCs) é um recurso essencial em todas as soluções de proteção de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="6c60f-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="6c60f-111">Essa funcionalidade oferece a SecOps a capacidade de definir uma lista de indicadores para detecção e bloqueio (prevenção e resposta).</span><span class="sxs-lookup"><span data-stu-id="6c60f-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="6c60f-112">Crie indicadores que definem a detecção, a prevenção e a exclusão de entidades.</span><span class="sxs-lookup"><span data-stu-id="6c60f-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="6c60f-113">Você pode definir a ação a ser tomada, bem como a duração para quando aplicar a ação, bem como o escopo do grupo de dispositivos ao qual aplicá-la.</span><span class="sxs-lookup"><span data-stu-id="6c60f-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="6c60f-114">As fontes atualmente suportadas são o mecanismo de detecção de nuvem do Defender for Endpoint, o mecanismo automatizado de investigação e correção e o mecanismo de prevenção de ponto de extremidade (Microsoft Defender AV).</span><span class="sxs-lookup"><span data-stu-id="6c60f-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender AV).</span></span>

<span data-ttu-id="6c60f-115">**Mecanismo de detecção de nuvem**</span><span class="sxs-lookup"><span data-stu-id="6c60f-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="6c60f-116">O mecanismo de detecção de nuvem do Defender para Ponto de Extremidade verifica regularmente os dados coletados e tenta corresponder aos indicadores definidos.</span><span class="sxs-lookup"><span data-stu-id="6c60f-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="6c60f-117">Quando houver uma combinação, a ação será tomada de acordo com as configurações especificadas para o IoC.</span><span class="sxs-lookup"><span data-stu-id="6c60f-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="6c60f-118">**Mecanismo de prevenção do ponto de extremidade**</span><span class="sxs-lookup"><span data-stu-id="6c60f-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="6c60f-119">A mesma lista de indicadores é adida pelo agente de prevenção.</span><span class="sxs-lookup"><span data-stu-id="6c60f-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="6c60f-120">Ou seja, se o Microsoft Defender AV for o AV principal configurado, os indicadores matched serão tratados de acordo com as configurações.</span><span class="sxs-lookup"><span data-stu-id="6c60f-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="6c60f-121">Por exemplo, se a ação for "Alerta e Bloquear", o Microsoft Defender AV impedirá execuções de arquivo (bloquear e remediar) e um alerta correspondente será gerado.</span><span class="sxs-lookup"><span data-stu-id="6c60f-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="6c60f-122">Por outro lado, se a Ação estiver definida como "Permitir", o Microsoft Defender AV não detectará nem impedirá que o arquivo seja executado.</span><span class="sxs-lookup"><span data-stu-id="6c60f-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="6c60f-123">**Mecanismo automatizado de investigação e correção**</span><span class="sxs-lookup"><span data-stu-id="6c60f-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="6c60f-124">A investigação automatizada e a correção se comportam da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="6c60f-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="6c60f-125">Se um indicador for definido como "Permitir", a investigação automatizada e a correção ignorarão um veredito "ruim" para ele.</span><span class="sxs-lookup"><span data-stu-id="6c60f-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="6c60f-126">Se definido como "Bloquear", a investigação automatizada e a correção a tratarão como "ruim".</span><span class="sxs-lookup"><span data-stu-id="6c60f-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>


<span data-ttu-id="6c60f-127">As ações com suporte atuais são:</span><span class="sxs-lookup"><span data-stu-id="6c60f-127">The current supported actions are:</span></span>
- <span data-ttu-id="6c60f-128">Permitir</span><span class="sxs-lookup"><span data-stu-id="6c60f-128">Allow</span></span>
- <span data-ttu-id="6c60f-129">Somente alerta</span><span class="sxs-lookup"><span data-stu-id="6c60f-129">Alert only</span></span>
- <span data-ttu-id="6c60f-130">Alerta e bloqueio</span><span class="sxs-lookup"><span data-stu-id="6c60f-130">Alert and block</span></span>


<span data-ttu-id="6c60f-131">Você pode criar um indicador para:</span><span class="sxs-lookup"><span data-stu-id="6c60f-131">You can create an indicator for:</span></span>
- [<span data-ttu-id="6c60f-132">Files</span><span class="sxs-lookup"><span data-stu-id="6c60f-132">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="6c60f-133">Endereços IP, URLs/domínios</span><span class="sxs-lookup"><span data-stu-id="6c60f-133">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="6c60f-134">Certificados</span><span class="sxs-lookup"><span data-stu-id="6c60f-134">Certificates</span></span>](indicator-certificates.md)


>[!NOTE]
><span data-ttu-id="6c60f-135">Há um limite de 15.000 indicadores por locatário.</span><span class="sxs-lookup"><span data-stu-id="6c60f-135">There is a limit of 15,000 indicators per tenant.</span></span>


## <a name="related-topics"></a><span data-ttu-id="6c60f-136">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6c60f-136">Related topics</span></span>

- [<span data-ttu-id="6c60f-137">Criar IoC contextual</span><span class="sxs-lookup"><span data-stu-id="6c60f-137">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="6c60f-138">Usar a API de indicadores de ponto de extremidade do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6c60f-138">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="6c60f-139">Usar soluções integradas a parceiros</span><span class="sxs-lookup"><span data-stu-id="6c60f-139">Use partner integrated solutions</span></span>](partner-applications.md)
