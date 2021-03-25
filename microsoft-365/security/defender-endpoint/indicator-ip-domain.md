---
title: Criar indicadores para IPs e URLs/domínios
ms.reviewer: ''
description: Crie indicadores para IPs e URLs/domínios que definem a detecção, prevenção e exclusão de entidades.
keywords: ip, url, domínio, gerenciar, permitido, bloqueado, bloqueado, limpo, mal-intencionado, hash de arquivo, endereço ip, urls, domínio
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
ms.openlocfilehash: d468a77d2c1ab4f1b363e2e91b6e8507a5390d93
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198478"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="0b7f5-104">Criar indicadores para IPs e URLs/domínios</span><span class="sxs-lookup"><span data-stu-id="0b7f5-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0b7f5-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0b7f5-105">**Applies to:**</span></span>
- [<span data-ttu-id="0b7f5-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0b7f5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0b7f5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b7f5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> <span data-ttu-id="0b7f5-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="0b7f5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0b7f5-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="0b7f5-110">O Defender for Endpoint pode bloquear o que a Microsoft considera como IPs/URLs mal-intencionadas, por meio do Windows Defender SmartScreen para navegadores Microsoft e por meio da Proteção de Rede para navegadores que não são da Microsoft ou chamadas feitas fora de um navegador.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="0b7f5-111">O conjunto de dados de inteligência de ameaças para isso foi gerenciado pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="0b7f5-112">Ao criar indicadores para IPs e URLs ou domínios, agora você pode permitir ou bloquear IPs, URLs ou domínios com base em sua própria inteligência contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="0b7f5-113">Você pode fazer isso por meio da página de configurações ou por grupos de máquinas se você considera que determinados grupos estão mais ou menos em risco do que outros.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="0b7f5-114">Não há suporte Inter-Domain de roteamento sem classe (CIDR) para endereços IP.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="0b7f5-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0b7f5-115">Before you begin</span></span>
<span data-ttu-id="0b7f5-116">É importante entender os seguintes pré-requisitos antes da criação de indicadores para IPS, URLs ou domínios:</span><span class="sxs-lookup"><span data-stu-id="0b7f5-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="0b7f5-117">A URL/IP permite e bloqueia depende da Proteção de Rede do componente Defender for Endpoint a ser habilitada no modo de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="0b7f5-118">Para obter mais informações sobre as instruções de configuração e proteção de rede, consulte [Enable network protection](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="0b7f5-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="0b7f5-119">A versão do cliente Antimalware deve ser 4.18.1906.x ou posterior.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="0b7f5-120">Suportado em computadores no Windows 10, versão 1709 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="0b7f5-121">Verifique se **os indicadores de rede personalizados** estão habilitados no Centro de Segurança do **Microsoft Defender > Configurações > recursos avançados.**</span><span class="sxs-lookup"><span data-stu-id="0b7f5-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="0b7f5-122">Para obter mais informações, consulte [Recursos avançados](advanced-features.md).</span><span class="sxs-lookup"><span data-stu-id="0b7f5-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="0b7f5-123">Para dar suporte a indicadores no iOS, consulte [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span><span class="sxs-lookup"><span data-stu-id="0b7f5-123">For support of indicators on iOS, see [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="0b7f5-124">Somente IPs externos podem ser adicionados à lista de indicadores.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="0b7f5-125">Os indicadores não podem ser criados para IPs internos.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="0b7f5-126">Para cenários de proteção da Web, recomendamos usar os recursos integrados no Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="0b7f5-127">O Microsoft Edge aproveita a [Proteção de Rede](network-protection.md) para inspecionar o tráfego de rede e permite blocos para TCP, HTTP e HTTPS (TLS).</span><span class="sxs-lookup"><span data-stu-id="0b7f5-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="0b7f5-128">Se houver políticas de indicador de URL conflitantes, o caminho mais longo será aplicado.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-128">If there are conflicting URL indicator policies, the longer path is applied.</span></span> <span data-ttu-id="0b7f5-129">Por exemplo, a política de indicador de URL `https:\\support.microsoft.com/en-us/office` tem precedência sobre a política de indicador de URL `https:\\support.microsoft.com` .</span><span class="sxs-lookup"><span data-stu-id="0b7f5-129">For example, the URL indicator policy `https:\\support.microsoft.com/en-us/office` takes precedence over the URL indicator policy `https:\\support.microsoft.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="0b7f5-130">Para todos os outros processos, os cenários de proteção da Web aproveitam a Proteção de Rede para inspeção e imposição:</span><span class="sxs-lookup"><span data-stu-id="0b7f5-130">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> 
> - <span data-ttu-id="0b7f5-131">O IP tem suporte para todos os três protocolos</span><span class="sxs-lookup"><span data-stu-id="0b7f5-131">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="0b7f5-132">Somente endereços IP únicos são suportados (sem blocos CIDR ou intervalos IP)</span><span class="sxs-lookup"><span data-stu-id="0b7f5-132">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="0b7f5-133">URLs criptografadas (caminho completo) só podem ser bloqueadas em navegadores de primeira parte (Internet Explorer, Borda)</span><span class="sxs-lookup"><span data-stu-id="0b7f5-133">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="0b7f5-134">URLS criptografadas (somente FQDN) podem ser bloqueadas fora de navegadores de primeira parte (Internet Explorer, Borda)</span><span class="sxs-lookup"><span data-stu-id="0b7f5-134">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="0b7f5-135">Os blocos de caminho de URL completos podem ser aplicados no nível de domínio e em todas as URLs não criptografadas</span><span class="sxs-lookup"><span data-stu-id="0b7f5-135">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="0b7f5-136">Pode haver até 2 horas de latência (geralmente menos) entre o momento em que a ação é realizada e a URL e o IP sendo bloqueados.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-136">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="0b7f5-137">Criar um indicador para IPs, URLs ou domínios na página de configurações</span><span class="sxs-lookup"><span data-stu-id="0b7f5-137">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="0b7f5-138">No painel de navegação, selecione **Indicadores de**  >  **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-138">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="0b7f5-139">Selecione a **guia Endereços IP ou URLs/Domínios.**</span><span class="sxs-lookup"><span data-stu-id="0b7f5-139">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="0b7f5-140">Selecione **Adicionar item**.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-140">Select **Add item**.</span></span>

4. <span data-ttu-id="0b7f5-141">Especifique os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="0b7f5-141">Specify the following details:</span></span>
   - <span data-ttu-id="0b7f5-142">Indicador - Especifique os detalhes da entidade e defina a expiração do indicador.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-142">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="0b7f5-143">Ação - Especifique a ação a ser tomada e forneça uma descrição.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-143">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="0b7f5-144">Escopo - Definir o escopo do grupo de máquinas.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-144">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="0b7f5-145">Revise os detalhes na guia Resumo e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0b7f5-145">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0b7f5-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="0b7f5-146">Related topics</span></span>
- [<span data-ttu-id="0b7f5-147">Criar indicadores</span><span class="sxs-lookup"><span data-stu-id="0b7f5-147">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="0b7f5-148">Criar indicadores para arquivos</span><span class="sxs-lookup"><span data-stu-id="0b7f5-148">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="0b7f5-149">Criar indicadores com base em certificados</span><span class="sxs-lookup"><span data-stu-id="0b7f5-149">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="0b7f5-150">Gerenciar indicadores</span><span class="sxs-lookup"><span data-stu-id="0b7f5-150">Manage indicators</span></span>](indicator-manage.md)
