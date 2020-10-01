---
title: Início rápido da rede de distribuição de conteúdo (CDN) do Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- M365initiative-CoreDeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Início rápido da rede de distribuição de conteúdo (CDN) do Office 365
ms.openlocfilehash: e9975721b5cfaaed2c9ad7562c47f12c7a5a5bc3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326884"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="980a9-103">Início rápido da rede de distribuição de conteúdo (CDN) do Office 365</span><span class="sxs-lookup"><span data-stu-id="980a9-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="980a9-104">Você pode usar a **rede de distribuição de conteúdo (CDN) do Office 365** interna para hospedar ativos estáticos (imagens, JavaScript, folhas de estilos, arquivos do WOFF) para fornecer melhor desempenho para suas páginas do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="980a9-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="980a9-105">A CDN do Office 365 melhora o desempenho ao armazenar em cache ativos estáticos mais próximos aos navegadores que os solicitaram, o que ajuda a acelerar downloads e reduzir a latência.</span><span class="sxs-lookup"><span data-stu-id="980a9-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="980a9-106">Além disso, a CDN do Office 365 usa o protocolo HTTP/2 para maior compactação e canalização HTTP.</span><span class="sxs-lookup"><span data-stu-id="980a9-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="980a9-107">O serviço de CDN do Office 365 faz parte da assinatura do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="980a9-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="980a9-108">Para obter diretrizes de informações mais detalhadas, consulte [usar a rede de distribuição de conteúdo (CDN) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="980a9-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="980a9-109">A CDN do Office 365 só está disponível para locatários na nuvem de produção (internacional).</span><span class="sxs-lookup"><span data-stu-id="980a9-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="980a9-110">Os locatários nas nuvens do governo dos EUA, da China e da Alemanha não suportam atualmente a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="980a9-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="980a9-111">Usar a ferramenta diagnóstico de página para SharePoint para identificar os itens que não estão na CDN</span><span class="sxs-lookup"><span data-stu-id="980a9-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="980a9-112">Você pode usar a extensão de **diagnóstico de página para a ferramenta do SharePoint** para listar facilmente os ativos em suas páginas do SharePoint Online que podem ser adicionadas a uma origem de CDN.</span><span class="sxs-lookup"><span data-stu-id="980a9-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="980a9-113">A **ferramenta diagnóstico de página do SharePoint** é uma extensão de navegador para o novo Microsoft Edge ( https://www.microsoft.com/edge) e navegadores Chrome que analisa o portal moderno do SharePoint Online e as páginas do site de publicação clássica.</span><span class="sxs-lookup"><span data-stu-id="980a9-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="980a9-114">A ferramenta fornece um relatório para cada página analisada que mostra o desempenho da página em relação a um conjunto definido de critérios de desempenho.</span><span class="sxs-lookup"><span data-stu-id="980a9-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="980a9-115">Para instalar e saber mais sobre a ferramenta Diagnóstico de Página para SharePoint, acesse [Usar a ferramenta Diagnóstico de Página para SharePoint Online](https://aka.ms/perftool).</span><span class="sxs-lookup"><span data-stu-id="980a9-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](https://aka.ms/perftool).</span></span>

<span data-ttu-id="980a9-116">Ao executar a ferramenta diagnóstico de página para SharePoint em uma página do SharePoint Online, você pode clicar na guia **testes de diagnóstico** para ver uma lista de ativos que não estão sendo hospedados pela CDN.</span><span class="sxs-lookup"><span data-stu-id="980a9-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="980a9-117">Esses ativos serão listados na lista de **CDN (rede de distribuição de conteúdo)** de título, conforme mostrado na captura de tela abaixo.</span><span class="sxs-lookup"><span data-stu-id="980a9-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![Diagnóstico de página](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="980a9-119">A ferramenta de Diagnóstico de Página só funciona com o SharePoint Online e não pode ser usada em uma página do sistema do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="980a9-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="980a9-120">Visão geral da CDN</span><span class="sxs-lookup"><span data-stu-id="980a9-120">CDN Overview</span></span>

<span data-ttu-id="980a9-121">A CDN do Office 365 foi projetada para otimizar o desempenho de usuários, distribuindo objetos acessados com frequência, como imagens e arquivos JavaScript, em uma rede global de alta velocidade, reduzindo o tempo de carregamento da página e fornecendo acesso a objetos hospedados o mais próximo possível do usuário.</span><span class="sxs-lookup"><span data-stu-id="980a9-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="980a9-122">A CDN busca seus ativos de um local chamado _origem_.</span><span class="sxs-lookup"><span data-stu-id="980a9-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="980a9-123">Uma origem pode ser um site do SharePoint, uma biblioteca de documentos ou uma pasta que possa ser acessada por uma URL.</span><span class="sxs-lookup"><span data-stu-id="980a9-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="980a9-124">A CDN do Office 365 é separada em dois tipos básicos:</span><span class="sxs-lookup"><span data-stu-id="980a9-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="980a9-125">A **CDN pública** foi projetada para ser usada para o JS (JavaScript), CSS (folhas de estilo), arquivo de fontes da Web (WOFF, WOFF2) e imagens não proprietárias, como logotipos da empresa.</span><span class="sxs-lookup"><span data-stu-id="980a9-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="980a9-126">A **CDN privada** foi projetada para ser usada para imagens (png, jpg, JPEG, etc.).</span><span class="sxs-lookup"><span data-stu-id="980a9-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="980a9-127">Você pode optar por ter origens públicas ou privadas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="980a9-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="980a9-128">A maioria das organizações optará por implementar uma combinação dos dois.</span><span class="sxs-lookup"><span data-stu-id="980a9-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="980a9-129">As opções pública e privada fornecem ganhos de desempenho semelhantes, mas cada um tem atributos e vantagens exclusivos.</span><span class="sxs-lookup"><span data-stu-id="980a9-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="980a9-130">Para obter mais informações sobre origens de CDN públicas e privadas, consulte [escolher se cada origem deve ser pública ou privada](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span><span class="sxs-lookup"><span data-stu-id="980a9-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="980a9-131">Como habilitar a CDN pública e privada com a configuração padrão</span><span class="sxs-lookup"><span data-stu-id="980a9-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="980a9-132">Antes de fazer alterações nas configurações de CDN do locatário, verifique se ela atende às políticas de conformidade, segurança e privacidade da sua organização.</span><span class="sxs-lookup"><span data-stu-id="980a9-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="980a9-133">Para saber mais sobre definições de configuração ou se você já habilitou a CDN e deseja adicionar locais adicionais (origens), confira a seção [configurar e configurar a CDN do Office 365 usando o Shell de gerenciamento do SharePoint Online](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span><span class="sxs-lookup"><span data-stu-id="980a9-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="980a9-134">Conecte-se ao seu locatário usando o Shell de gerenciamento do SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="980a9-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="980a9-135">Para permitir que sua organização Use origens públicas e privadas com a configuração padrão, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="980a9-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="980a9-136">A saída desses cmdlets deve ser semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="980a9-136">Output of these cmdlets should look like the following:</span></span>

![Saída de Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="980a9-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="980a9-138">See also</span></span>

[<span data-ttu-id="980a9-139">Usar a ferramenta diagnóstico de página para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="980a9-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](https://aka.ms/perftool)

[<span data-ttu-id="980a9-140">Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="980a9-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="980a9-141">Redes de Distribuição de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="980a9-141">Content Delivery Networks</span></span>](https://aka.ms/o365cdns)

[<span data-ttu-id="980a9-142">Planejamento de rede e ajuste de desempenho para o Office 365</span><span class="sxs-lookup"><span data-stu-id="980a9-142">Network planning and performance tuning for Office 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="980a9-143">Série de desempenho do SharePoint-série de vídeo de CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="980a9-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
