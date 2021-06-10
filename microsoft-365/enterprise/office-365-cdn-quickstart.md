---
title: Office 365 Rede de Distribuição de Conteúdo (CDN) Início rápido
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
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 Rede de Distribuição de Conteúdo (CDN) Início rápido
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921589"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="abad9-103">Office 365 Rede de Distribuição de Conteúdo (CDN) Início rápido</span><span class="sxs-lookup"><span data-stu-id="abad9-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="abad9-104">Você pode usar o Office 365 Rede de Distribuição de Conteúdo **(CDN)** para hospedar ativos estáticos (imagens, JavaScript, folhas de estilo, arquivos WOFF) para fornecer melhor desempenho para suas páginas SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="abad9-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="abad9-105">A CDN do Office 365 melhora o desempenho ao armazenar em cache ativos estáticos mais próximos aos navegadores que os solicitaram, o que ajuda a acelerar downloads e reduzir a latência.</span><span class="sxs-lookup"><span data-stu-id="abad9-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="abad9-106">Além disso, o Office 365 CDN usa o protocolo HTTP/2 para compactação aprimorada e pipelização HTTP.</span><span class="sxs-lookup"><span data-stu-id="abad9-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="abad9-107">O serviço de CDN do Office 365 faz parte da assinatura do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="abad9-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="abad9-108">Para obter orientações de informações mais detalhadas, [consulte Use the Office 365 Rede de Distribuição de Conteúdo (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="abad9-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="abad9-109">O Office 365 CDN está disponível apenas para locatários na nuvem de produção (em todo o mundo).</span><span class="sxs-lookup"><span data-stu-id="abad9-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="abad9-110">Os locatários nas nuvens do Governo dos EUA, China e Alemanha atualmente não suportam o Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="abad9-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="abad9-111">Use a ferramenta Diagnóstico de Página SharePoint para identificar itens que não estão CDN</span><span class="sxs-lookup"><span data-stu-id="abad9-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="abad9-112">Você pode usar a extensão diagnóstico de página para SharePoint do navegador de ferramentas para listar facilmente ativos em suas páginas do SharePoint Online que podem ser **adicionados** a uma origem CDN.</span><span class="sxs-lookup"><span data-stu-id="abad9-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="abad9-113">A **ferramenta Diagnóstico de Página para** SharePoint é uma extensão do navegador para o novo Microsoft Edge ( e navegadores do Chrome que analisam o portal moderno do SharePoint Online e páginas de sites de publicação https://www.microsoft.com/edge) clássicas.</span><span class="sxs-lookup"><span data-stu-id="abad9-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="abad9-114">A ferramenta fornece um relatório para cada página analisada que mostra o desempenho da página em relação a um conjunto definido de critérios de desempenho.</span><span class="sxs-lookup"><span data-stu-id="abad9-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="abad9-115">Para instalar e saber mais sobre a ferramenta Diagnóstico de Página para SharePoint, acesse [Usar a ferramenta Diagnóstico de Página para SharePoint Online](./page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="abad9-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](./page-diagnostics-for-spo.md).</span></span>

<span data-ttu-id="abad9-116">Ao executar a ferramenta Diagnóstico de Página para SharePoint em uma página do  SharePoint Online, você pode clicar na guia Testes de Diagnóstico para ver uma lista de ativos que não estão sendo hospedados pelo CDN.</span><span class="sxs-lookup"><span data-stu-id="abad9-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="abad9-117">Esses ativos serão listados na Rede de Distribuição de Conteúdo **(CDN) conforme** mostrado na captura de tela abaixo.</span><span class="sxs-lookup"><span data-stu-id="abad9-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![Diagnóstico de página](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="abad9-119">A ferramenta de Diagnóstico de Página só funciona com o SharePoint Online e não pode ser usada em uma página do sistema do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="abad9-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="abad9-120">CDN Visão geral</span><span class="sxs-lookup"><span data-stu-id="abad9-120">CDN Overview</span></span>

<span data-ttu-id="abad9-121">O Office 365 CDN foi projetado para otimizar o desempenho dos usuários distribuindo objetos acessados com frequência, como imagens e arquivos javascript em uma rede global de alta velocidade, reduzindo o tempo de carregamento da página e fornecendo acesso aos objetos hospedados o mais próximo possível do usuário.</span><span class="sxs-lookup"><span data-stu-id="abad9-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="abad9-122">O CDN busca seus ativos de um local chamado de _origem_.</span><span class="sxs-lookup"><span data-stu-id="abad9-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="abad9-123">Uma origem pode ser um site SharePoint, biblioteca de documentos ou pasta acessível por uma URL.</span><span class="sxs-lookup"><span data-stu-id="abad9-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="abad9-124">O Office 365 CDN é separado em dois tipos básicos:</span><span class="sxs-lookup"><span data-stu-id="abad9-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="abad9-125">**O CDN** público foi projetado para ser usado para JS (JavaScript), CSS (StyleSheets), Arquivo de Fonte da Web (WOFF, WOFF2) e imagens não proprietárias, como logotipos da empresa.</span><span class="sxs-lookup"><span data-stu-id="abad9-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="abad9-126">**A CDN** privada foi projetada para ser usada para imagens (PNG, JPG, JPEG, etc.).</span><span class="sxs-lookup"><span data-stu-id="abad9-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="abad9-127">Você pode optar por ter origens públicas ou privadas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="abad9-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="abad9-128">A maioria das organizações optará por implementar uma combinação dos dois.</span><span class="sxs-lookup"><span data-stu-id="abad9-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="abad9-129">As opções públicas e privadas oferecem ganhos de desempenho semelhantes, mas cada uma delas tem atributos e vantagens exclusivos.</span><span class="sxs-lookup"><span data-stu-id="abad9-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="abad9-130">Para obter mais informações sobre origens CDN públicas e privadas, consulte [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span><span class="sxs-lookup"><span data-stu-id="abad9-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="abad9-131">Como habilitar o serviço público e CDN com a configuração padrão</span><span class="sxs-lookup"><span data-stu-id="abad9-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="abad9-132">Antes de fazer alterações nas configurações CDN locatários, verifique se ele atende às políticas de conformidade, segurança e privacidade da sua organização.</span><span class="sxs-lookup"><span data-stu-id="abad9-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="abad9-133">Para obter configurações mais detalhadas ou se você já tiver habilitado o CDN e quiser adicionar locais adicionais (origens), consulte a seção Configurar e configurar o Office 365 CDN usando o Shell de Gerenciamento do [SharePoint Online](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span><span class="sxs-lookup"><span data-stu-id="abad9-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="abad9-134">Conexão seu locatário usando o Shell de Gerenciamento SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="abad9-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="abad9-135">Para permitir que sua organização use origens públicas e privadas com a configuração padrão, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="abad9-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="abad9-136">A saída desses cmdlets deve ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="abad9-136">Output of these cmdlets should look like the following:</span></span>

![Saída de Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="abad9-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="abad9-138">See also</span></span>

[<span data-ttu-id="abad9-139">Use a ferramenta Diagnóstico de Página para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="abad9-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](./page-diagnostics-for-spo.md)

[<span data-ttu-id="abad9-140">Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="abad9-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="abad9-141">Redes de Distribuição de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="abad9-141">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="abad9-142">Planejamento de rede e ajuste de desempenho para o Office 365</span><span class="sxs-lookup"><span data-stu-id="abad9-142">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="abad9-143">SharePoint Série de desempenho - Office 365 CDN de vídeo</span><span class="sxs-lookup"><span data-stu-id="abad9-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)