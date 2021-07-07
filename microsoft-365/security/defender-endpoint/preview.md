---
title: Recursos de visualização do Microsoft Defender para Ponto de Extremidade
description: Saiba como acessar os recursos de visualização do Microsoft Defender for Endpoint.
keywords: visualização, experiência de visualização, Microsoft Defender para Ponto de Extremidade, recursos, atualizações
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0ed494cc29eb990430be590e62db5f0365ace494
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322420"
---
# <a name="microsoft-defender-for-endpoint-preview-features"></a><span data-ttu-id="6a2ba-104">Recursos de visualização do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6a2ba-104">Microsoft Defender for Endpoint preview features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a2ba-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6a2ba-105">**Applies to:**</span></span>
- [<span data-ttu-id="6a2ba-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6a2ba-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6a2ba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a2ba-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6a2ba-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="6a2ba-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6a2ba-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="6a2ba-110">O serviço Defender para Ponto de Extremidade está constantemente sendo atualizado para incluir novos aprimoramentos e recursos de recursos.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-110">The Defender for Endpoint service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="6a2ba-111">Saiba mais sobre os novos recursos na versão de visualização do Defender para Ponto de Extremidade e entre os primeiros a experimentar os recursos futuros, ligando a experiência de visualização.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-111">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

>[!TIP]
><span data-ttu-id="6a2ba-112">Receba notificado quando esta página for atualizada copiando e colar a seguinte URL no leitor de feed: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span><span class="sxs-lookup"><span data-stu-id="6a2ba-112">Get notified when this page is updated by copying and pasting the following URL into your feed reader: `/api/search/rss?search=%22In+the+navigation+pane%2C+select+Settings+%3E+Advanced+features+%3E+Preview+features.%22&locale=en-us&facet=`</span></span>

<span data-ttu-id="6a2ba-113">Para obter mais informações sobre novos recursos que geralmente estão disponíveis, consulte [Novidades no Defender para Ponto de Extremidade](whats-new-in-microsoft-defender-atp.md).</span><span class="sxs-lookup"><span data-stu-id="6a2ba-113">For more information on new capabilities that are generally available, see [What's new in Defender for Endpoint](whats-new-in-microsoft-defender-atp.md).</span></span>

 ## <a name="what-you-need-to-know"></a><span data-ttu-id="6a2ba-114">O que você precisa saber</span><span class="sxs-lookup"><span data-stu-id="6a2ba-114">What you need to know</span></span>

<span data-ttu-id="6a2ba-115">Ao trabalhar com recursos na visualização pública, esses recursos:</span><span class="sxs-lookup"><span data-stu-id="6a2ba-115">When working with features in public preview, these features:</span></span>

- <span data-ttu-id="6a2ba-116">Pode ter funcionalidade restrita ou limitada.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-116">May have restricted or limited functionality.</span></span> <span data-ttu-id="6a2ba-117">Por exemplo, o recurso só pode se aplicar a uma plataforma.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-117">For example, the feature may only apply to one platform.</span></span>
- <span data-ttu-id="6a2ba-118">Normalmente, passam por alterações de recursos antes de elas geralmente disponíveis (GA).</span><span class="sxs-lookup"><span data-stu-id="6a2ba-118">Typically go through feature changes before they're generally available (GA).</span></span>
- <span data-ttu-id="6a2ba-119">São totalmente suportados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-119">Are fully supported by Microsoft.</span></span>
- <span data-ttu-id="6a2ba-120">Só pode estar disponível em regiões geográficas ou ambientes de nuvem selecionados.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-120">May only be available in selected geographic regions or cloud environments.</span></span> <span data-ttu-id="6a2ba-121">Por exemplo, o recurso pode não existir na nuvem governamental.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-121">For example, the feature may not exist in the government cloud.</span></span>
- <span data-ttu-id="6a2ba-122">Recursos individuais na visualização podem ter mais restrições de uso e suporte.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-122">Individual features in preview may have more usage and support restrictions.</span></span> <span data-ttu-id="6a2ba-123">Nesse caso, essas informações geralmente são notadas na documentação do recurso.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-123">If so, this information is typically noted in the feature documentation.</span></span>
- <span data-ttu-id="6a2ba-124">As versões de visualização são fornecidas com um nível de suporte padrão e são recomendadas para cargas de trabalho de produção.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-124">The preview versions are provided with a standard support level, and it is recommended for production workloads.</span></span> 



## <a name="turn-on-preview-features"></a><span data-ttu-id="6a2ba-125">Habilitar recursos de prévia</span><span class="sxs-lookup"><span data-stu-id="6a2ba-125">Turn on preview features</span></span>

<span data-ttu-id="6a2ba-126">Você terá acesso aos recursos futuros que você pode fornecer comentários para ajudar a melhorar a experiência geral antes que os recursos geralmente estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-126">You'll have access to upcoming features that you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="6a2ba-127">Ative a configuração de experiência de visualização para ser uma das primeiras pessoas a experimentar os recursos futuros.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-127">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="6a2ba-128">No painel de navegação, **selecione** Configurações  >  **recursos avançados**  >  **De visualização.**</span><span class="sxs-lookup"><span data-stu-id="6a2ba-128">In the navigation pane, select **Settings** > **Advanced features** > **Preview features**.</span></span>

2. <span data-ttu-id="6a2ba-129">Alterne a configuração **entre On** e **Off** e selecione **Salvar preferências**.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-129">Toggle the setting between **On** and **Off** and select **Save preferences**.</span></span>

## <a name="preview-features"></a><span data-ttu-id="6a2ba-130">Visualização prévia de recursos</span><span class="sxs-lookup"><span data-stu-id="6a2ba-130">Preview features</span></span>

<span data-ttu-id="6a2ba-131">Os seguintes novos recursos estão incluídos na visualização prévia:</span><span class="sxs-lookup"><span data-stu-id="6a2ba-131">The following features are included in the preview release:</span></span>

- [<span data-ttu-id="6a2ba-132">Filtragem de Conteúdo da Web</span><span class="sxs-lookup"><span data-stu-id="6a2ba-132">Web Content Filtering</span></span>](web-content-filtering.md) <br> <span data-ttu-id="6a2ba-133">A filtragem de conteúdo da Web faz parte dos recursos de proteção da Web no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-133">Web content filtering is part of web protection capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6a2ba-134">Ele permite que sua organização acompanhe e regular o acesso a sites com base em suas categorias de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-134">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="6a2ba-135">Muitos desses sites, embora não sejam mal-intencionados, podem ser problemáticos devido a regulamentos de conformidade, uso de largura de banda ou outras preocupações.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-135">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

- [<span data-ttu-id="6a2ba-136">Relatório de integridade e conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="6a2ba-136">Device health and compliance report</span></span>](machine-reports.md) <br/> <span data-ttu-id="6a2ba-137">O relatório de conformidade e saúde do dispositivo fornece informações de alto nível sobre os dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-137">The device health and compliance report provides high-level information about the devices in your organization.</span></span>

> [!TIP] 
> <span data-ttu-id="6a2ba-138">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="6a2ba-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6a2ba-139">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="6a2ba-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-preview-belowfoldlink)  
