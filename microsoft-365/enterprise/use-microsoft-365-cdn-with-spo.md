---
title: Usar a CdN (Rede de Distribuição de Conteúdo) do Office 365 com o SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Saiba como usar a CdN (Rede de Entrega de Conteúdo) do Office 365 para acelerar a entrega dos ativos do SharePoint Online.
ms.openlocfilehash: 6b740fc1429613627e0597dc6ecf2e150c015989
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924811"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="a3da3-103">Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="a3da3-104">Você pode usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 integrado para proporcionar melhor desempenho a suas páginas do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a3da3-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="a3da3-105">A CDN do Office 365 melhora o desempenho ao armazenar em cache ativos estáticos mais próximos aos navegadores que os solicitaram, o que ajuda a acelerar downloads e reduzir a latência.</span><span class="sxs-lookup"><span data-stu-id="a3da3-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="a3da3-106">Além disso, a CDN do Office 365 usa o [protocolo HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) para compactação aprimorada e pipelinamento HTTP.</span><span class="sxs-lookup"><span data-stu-id="a3da3-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="a3da3-107">O serviço de CDN do Office 365 faz parte da assinatura do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a3da3-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="a3da3-108">A CDN do Office 365 só está disponível para locatários na nuvem **produção** (em todo o mundo).</span><span class="sxs-lookup"><span data-stu-id="a3da3-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="a3da3-109">Os locatários nas nuvens do Governo dos EUA, China e Alemanha atualmente não suportam a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3da3-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="a3da3-110">A CDN do Office 365 é composta por várias CDNs que permitem que você hospede ativos estáticos em vários locais ou _origens_ e sirva-os de redes globais de alta velocidade.</span><span class="sxs-lookup"><span data-stu-id="a3da3-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="a3da3-111">Dependendo do tipo de conteúdo você quiser hospedar na CDN do Office 365, você pode adicionar origens **públicas**, origens **privadas** ou ambas.</span><span class="sxs-lookup"><span data-stu-id="a3da3-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="a3da3-112">Confira [Escolher se cada origem deve ser pública](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) ou privada para obter mais informações sobre a diferença entre origens públicas e privadas.</span><span class="sxs-lookup"><span data-stu-id="a3da3-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="a3da3-113">![Diagrama conceitual da CDN do Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Diagrama conceitual da CDN do Office 365")</span><span class="sxs-lookup"><span data-stu-id="a3da3-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="a3da3-114">Se você já estiver familiarizado com a maneira como as CDNs funcionam, você só precisa concluir algumas etapas para habilitar a CDN do Office 365 para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="a3da3-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="a3da3-115">Este tópico descreve como.</span><span class="sxs-lookup"><span data-stu-id="a3da3-115">This topic describes how.</span></span> <span data-ttu-id="a3da3-116">Leia para obter informações sobre como começar a hospedar seus ativos estáticos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="a3da3-117">Há outras CDNs hospedadas pela Microsoft que podem ser usadas com o Office 365 para cenários de uso especializados, mas não são discutidas neste tópico porque elas estão fora do escopo da CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3da3-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="a3da3-118">Para obter mais informações, consulte [Outras CDNs da Microsoft](content-delivery-networks.md#other-microsoft-cdns).</span><span class="sxs-lookup"><span data-stu-id="a3da3-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="a3da3-119">**Volte para [o planejamento de rede e ajuste de desempenho do Office 365](./network-planning-and-performance.md).**</span><span class="sxs-lookup"><span data-stu-id="a3da3-119">**Head back to [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="a3da3-120">Visão geral do trabalho com a CDN do Office 365 no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="a3da3-121">Para configurar a CDN do Office 365 para sua organização, siga estas etapas básicas:</span><span class="sxs-lookup"><span data-stu-id="a3da3-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="a3da3-122">Planejar a implantação da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="a3da3-123">[Determine quais ativos estáticos você deseja hospedar na CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span><span class="sxs-lookup"><span data-stu-id="a3da3-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="a3da3-124">[Determine onde deseja armazenar seus ativos.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)</span><span class="sxs-lookup"><span data-stu-id="a3da3-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="a3da3-125">Esse local pode ser um site, biblioteca ou pasta do SharePoint e é chamado de _origem._</span><span class="sxs-lookup"><span data-stu-id="a3da3-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="a3da3-126">[Escolha se cada origem deve ser pública ou privada.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="a3da3-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="a3da3-127">Você pode adicionar várias origens de tipos públicos e privados.</span><span class="sxs-lookup"><span data-stu-id="a3da3-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="a3da3-128">Configurar e configurar a CDN usando o PowerShell ou a CLI do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="a3da3-129">Configurar e configurar a CDN usando o Shell de Gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="a3da3-130">Configurar e configurar a CDN usando o PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3da3-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="a3da3-131">Configurar e configurar a CDN usando a CLI do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="a3da3-132">Ao concluir esta etapa, você terá:</span><span class="sxs-lookup"><span data-stu-id="a3da3-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="a3da3-133">Habilitada a CDN para sua organização.</span><span class="sxs-lookup"><span data-stu-id="a3da3-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="a3da3-134">Adicionada suas origens, identificando cada origem como pública ou privada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="a3da3-135">Depois de terminar a instalação, você poderá Gerenciar a CDN do [Office 365](use-microsoft-365-cdn-with-spo.md#CDNManage) ao longo do tempo:</span><span class="sxs-lookup"><span data-stu-id="a3da3-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="a3da3-136">Adicionar, atualizar e remover ativos</span><span class="sxs-lookup"><span data-stu-id="a3da3-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="a3da3-137">Adicionar e remover origens</span><span class="sxs-lookup"><span data-stu-id="a3da3-137">Adding and removing origins</span></span>
+ <span data-ttu-id="a3da3-138">Configurando políticas de CDN</span><span class="sxs-lookup"><span data-stu-id="a3da3-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="a3da3-139">Se necessário, desabilitar a CDN</span><span class="sxs-lookup"><span data-stu-id="a3da3-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="a3da3-140">Por fim, [consulte Usando seus ativos CDN](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) para saber mais sobre como acessar seus ativos cdn de origens públicas e privadas.</span><span class="sxs-lookup"><span data-stu-id="a3da3-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="a3da3-141">Consulte [Solução de problemas da CDN do Office 365](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) para obter orientações sobre como resolver problemas comuns.</span><span class="sxs-lookup"><span data-stu-id="a3da3-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="a3da3-142">Planejar a implantação da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-143">Antes de implantar a CDN do Office 365 para seu locatário do Office 365, considere os seguintes fatores como parte do seu processo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="a3da3-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="a3da3-144">Determinar quais ativos estáticos você deseja hospedar na CDN</span><span class="sxs-lookup"><span data-stu-id="a3da3-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="a3da3-145">Determinar onde você deseja armazenar seus ativos</span><span class="sxs-lookup"><span data-stu-id="a3da3-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="a3da3-146">Escolha se cada origem deve ser pública ou privada</span><span class="sxs-lookup"><span data-stu-id="a3da3-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="a3da3-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="a3da3-148">Determinar quais ativos estáticos você deseja hospedar na CDN</span><span class="sxs-lookup"><span data-stu-id="a3da3-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="a3da3-149">Em geral, as CDNs são mais eficazes para hospedar ativos _estáticos_ ou ativos que não mudam com muita frequência.</span><span class="sxs-lookup"><span data-stu-id="a3da3-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="a3da3-150">Uma boa regra geral é identificar arquivos que atendem a algumas ou todas essas condições:</span><span class="sxs-lookup"><span data-stu-id="a3da3-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="a3da3-151">Arquivos estáticos inseridos em uma página (como scripts e imagens) que podem ter um impacto incremental significativo nos tempos de carregamento da página</span><span class="sxs-lookup"><span data-stu-id="a3da3-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="a3da3-152">Arquivos grandes, como executáveis e arquivos de instalação</span><span class="sxs-lookup"><span data-stu-id="a3da3-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="a3da3-153">Bibliotecas de recursos que suportam código do lado do cliente</span><span class="sxs-lookup"><span data-stu-id="a3da3-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="a3da3-154">Por exemplo, arquivos pequenos que são solicitados repetidamente, como imagens de site e scripts, podem melhorar significativamente o desempenho de renderização de site e reduzir incrementalmente a carga em seus sites do SharePoint Online quando você os adiciona a uma origem de CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="a3da3-155">Arquivos maiores, como executáveis de instalação, podem ser baixados da CDN, fornecendo um impacto positivo no desempenho e redução subsequente da carga em seu site do SharePoint Online, mesmo que eles não sejam acessados com a mesma frequência.</span><span class="sxs-lookup"><span data-stu-id="a3da3-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="a3da3-156">A melhoria de desempenho por arquivo depende de muitos fatores, incluindo a proximidade do cliente com o ponto de extremidade cdn mais próximo, condições transitórias na rede local e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="a3da3-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="a3da3-157">Muitos arquivos estáticos são muito pequenos e podem ser baixados do Office 365 em menos de um segundo.</span><span class="sxs-lookup"><span data-stu-id="a3da3-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="a3da3-158">No entanto, uma página da Web pode conter muitos arquivos incorporados com um tempo de download cumulativo de vários segundos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="a3da3-159">Atender a esses arquivos da CDN pode reduzir significativamente o tempo de carregamento geral da página.</span><span class="sxs-lookup"><span data-stu-id="a3da3-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="a3da3-160">Veja [Quais ganhos de desempenho uma CDN fornece?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) para um exemplo.</span><span class="sxs-lookup"><span data-stu-id="a3da3-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="a3da3-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="a3da3-162">Determinar onde você deseja armazenar seus ativos</span><span class="sxs-lookup"><span data-stu-id="a3da3-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="a3da3-163">A CDN busca seus ativos de um local chamado de _origem_.</span><span class="sxs-lookup"><span data-stu-id="a3da3-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="a3da3-164">Uma origem pode ser um site do SharePoint, uma biblioteca de documentos ou uma pasta acessível por uma URL.</span><span class="sxs-lookup"><span data-stu-id="a3da3-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="a3da3-165">Você tem uma grande flexibilidade ao especificar origens para sua organização.</span><span class="sxs-lookup"><span data-stu-id="a3da3-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="a3da3-166">Por exemplo, você pode especificar várias origens ou uma única origem onde deseja colocar todos os ativos cdn.</span><span class="sxs-lookup"><span data-stu-id="a3da3-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="a3da3-167">Você pode optar por ter origens públicas ou privadas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="a3da3-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="a3da3-168">A maioria das organizações optará por implementar uma combinação dos dois.</span><span class="sxs-lookup"><span data-stu-id="a3da3-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="a3da3-169">Você pode criar um novo contêiner para suas origens, como pastas ou bibliotecas de documentos, e adicionar arquivos que deseja disponibilizar a partir da CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="a3da3-170">Essa é uma boa abordagem se você tiver um conjunto específico de ativos que deseja estar disponível na CDN e quiser restringir o conjunto de ativos CDN apenas para esses arquivos no contêiner.</span><span class="sxs-lookup"><span data-stu-id="a3da3-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="a3da3-171">Você também pode configurar um conjunto de sites, site, biblioteca ou pasta existente como uma origem, o que disponibiliza todos os ativos qualificados no contêiner da CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="a3da3-172">Antes de adicionar um contêiner existente como origem, é importante ter certeza de que está ciente de seu conteúdo e permissões para que você não exponha inadvertidamente os ativos a acesso anônimo ou usuários não autorizados.</span><span class="sxs-lookup"><span data-stu-id="a3da3-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="a3da3-173">Você pode definir _políticas de CDN_ para excluir conteúdo em suas origens da CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="a3da3-174">As políticas de CDN excluem ativos  em origens públicas ou privadas por atributos como tipo de arquivo e classificação de _site_ e são aplicadas a todas as origens do CdnType (privado ou público) especificado na política.</span><span class="sxs-lookup"><span data-stu-id="a3da3-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="a3da3-175">Por exemplo, se você adicionar uma origem privada consistindo em um site que contenha  vários subsites, poderá definir uma política para excluir sites marcados como Confidencial para que o conteúdo de sites com essa classificação aplicada não seja atendido da CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="a3da3-176">A política se aplicará ao conteúdo de _todas as_ origens privadas adicionadas à CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="a3da3-177">Lembre-se de que quanto maior o número de origens, maior será o impacto no tempo que o serviço CDN leva para processar solicitações.</span><span class="sxs-lookup"><span data-stu-id="a3da3-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="a3da3-178">Recomendamos que você limite o número de origens o máximo possível.</span><span class="sxs-lookup"><span data-stu-id="a3da3-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="a3da3-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="a3da3-180">Escolha se cada origem deve ser pública ou privada</span><span class="sxs-lookup"><span data-stu-id="a3da3-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="a3da3-181">Ao identificar uma origem, especifique se ela deve ser _pública_ ou _privada._</span><span class="sxs-lookup"><span data-stu-id="a3da3-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="a3da3-182">O acesso aos ativos cdn em origens públicas é anônimo, e o conteúdo da CDN em origens privadas é protegido por tokens gerados dinamicamente para maior segurança.</span><span class="sxs-lookup"><span data-stu-id="a3da3-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="a3da3-183">Independentemente de qual opção você escolher, a Microsoft faz todo o trabalho pesado para você quando se trata de administração da PRÓPRIA CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="a3da3-184">Além disso, você pode mudar de ideia mais tarde, depois de configurar a CDN e identificar suas origens.</span><span class="sxs-lookup"><span data-stu-id="a3da3-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="a3da3-185">As opções públicas e privadas oferecem ganhos de desempenho semelhantes, mas cada uma delas tem atributos e vantagens exclusivos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="a3da3-186">**As** origens públicas na CDN do Office 365 são acessíveis anonimamente e os ativos hospedados podem ser acessados por qualquer pessoa que tenha a URL do ativo.</span><span class="sxs-lookup"><span data-stu-id="a3da3-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="a3da3-187">Como o acesso ao conteúdo de origens públicas é anônimo, você só deve usá-lo para o armazenamento em cache de conteúdo genérico e não sensível como arquivos javascript, scripts, ícones e imagens.</span><span class="sxs-lookup"><span data-stu-id="a3da3-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as javascript files, scripts, icons and images.</span></span>

<span data-ttu-id="a3da3-188">**As** origens privadas na CDN do Office 365 fornecem acesso privado ao conteúdo do usuário, como bibliotecas de documentos do SharePoint Online, sites e imagens proprietárias.</span><span class="sxs-lookup"><span data-stu-id="a3da3-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="a3da3-189">O acesso ao conteúdo em origens privadas é protegido por tokens gerados dinamicamente para que ele só possa ser acessado por usuários com permissões para a biblioteca de documentos original ou o local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="a3da3-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="a3da3-190">As origens privadas na CDN do Office 365 só podem ser usadas para conteúdo do SharePoint Online e você só pode acessar ativos em origens privadas por meio do redirecionamento do locatário do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a3da3-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="a3da3-191">Você pode ler mais sobre como o acesso de CDN a ativos em uma origem privada funciona em [Usar ativos em origens privadas.](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)</span><span class="sxs-lookup"><span data-stu-id="a3da3-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="a3da3-192">Atributos e vantagens de hospedar ativos em origens públicas</span><span class="sxs-lookup"><span data-stu-id="a3da3-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="a3da3-193">Os ativos exibidos em uma origem pública são acessíveis por todos os usuários anonimamente.</span><span class="sxs-lookup"><span data-stu-id="a3da3-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="a3da3-194">Você nunca deve colocar recursos que contenham informações do usuário ou sejam considerados confidenciais para sua organização em uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="a3da3-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>
+ <span data-ttu-id="a3da3-195">Se você remover um ativo de uma origem pública, ele pode seguir disponível em cache por até 30 dias; contudo, invalidaremos os links para o ativo na CDN em 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>
+ <span data-ttu-id="a3da3-196">Quando você hospeda folhas de estilo (arquivos CSS) em uma origem pública, você pode usar os caminhos relativos e URIs dentro do código.</span><span class="sxs-lookup"><span data-stu-id="a3da3-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="a3da3-197">Isso significa que você pode referenciar o local das imagens de fundo e outros objetos em relação ao local do ativo que faz a chamada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>
+ <span data-ttu-id="a3da3-198">Embora você possa construir uma URL de origem pública, você deve prosseguir com cautela e garantir que você utilize a propriedade de contexto de página e siga as diretrizes para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="a3da3-198">While you can construct a public origin's URL, you should proceed with caution and ensure you utilize the page context property and follow the guidance for doing so.</span></span> <span data-ttu-id="a3da3-199">O motivo é que se o acesso à CDN ficar indisponível, a URL não resolverá automaticamente para a sua organização no SharePoint Online e pode resultar em links quebrados e outros erros.</span><span class="sxs-lookup"><span data-stu-id="a3da3-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span> <span data-ttu-id="a3da3-200">A URL também está sujeita a alterações, razão pela qual ela não deve ser codificada apenas para seu valor atual.</span><span class="sxs-lookup"><span data-stu-id="a3da3-200">The URL is also subject to change wich is why it should not just be hard coded to its current value.</span></span>
+ <span data-ttu-id="a3da3-201">Os tipos de arquivo padrão incluídos para origens públicas são .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff e .woff2.</span><span class="sxs-lookup"><span data-stu-id="a3da3-201">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="a3da3-202">Você pode especificar tipos de arquivo adicionais.</span><span class="sxs-lookup"><span data-stu-id="a3da3-202">You can specify additional file types.</span></span>
+ <span data-ttu-id="a3da3-203">Você pode configurar uma política para excluir ativos que foram identificados pelas classificações de site que você especificar.</span><span class="sxs-lookup"><span data-stu-id="a3da3-203">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="a3da3-204">Por exemplo, você pode optar por excluir todos os ativos marcados como "restrito" ou "confidencial", mesmo que sejam um tipo de arquivo permitido e estejam localizados em uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="a3da3-204">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="a3da3-205">Atributos e vantagens de hospedar ativos em origens privadas</span><span class="sxs-lookup"><span data-stu-id="a3da3-205">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="a3da3-206">As origens privadas só podem ser usadas para ativos do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a3da3-206">Private origins can only be used for SharePoint Online assets.</span></span>
+ <span data-ttu-id="a3da3-207">Os usuários só poderão acessar os ativos de origem privada se eles têm permissões para acessar o contêiner.</span><span class="sxs-lookup"><span data-stu-id="a3da3-207">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="a3da3-208">O acesso anônimo a esses ativos é vetado.</span><span class="sxs-lookup"><span data-stu-id="a3da3-208">Anonymous access to these assets is prevented.</span></span>
+ <span data-ttu-id="a3da3-209">Os ativos de origem privada devem ser referenciados do locatário do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a3da3-209">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="a3da3-210">O acesso direto a ativos CDN privados não funciona.</span><span class="sxs-lookup"><span data-stu-id="a3da3-210">Direct access to private CDN assets does not work.</span></span>
+ <span data-ttu-id="a3da3-211">Se você remover um ativo da origem privada, o ativo poderá continuar disponível por até uma hora do cache; no entanto, invalidaremos links para o ativo na CDN dentro de 15 minutos após a remoção do ativo.</span><span class="sxs-lookup"><span data-stu-id="a3da3-211">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>
+ <span data-ttu-id="a3da3-212">Os tipos de arquivo padrão incluídos para origens privadas são .gif, .ico, .jpeg, .jpg, .js e .png.</span><span class="sxs-lookup"><span data-stu-id="a3da3-212">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="a3da3-213">Você pode especificar tipos de arquivo adicionais.</span><span class="sxs-lookup"><span data-stu-id="a3da3-213">You can specify additional file types.</span></span>
+ <span data-ttu-id="a3da3-214">Assim como com origens públicas, você pode configurar uma política para excluir ativos que foram identificados por classificações de site que você especifica, mesmo que você use curingas para incluir todos os ativos em uma pasta ou biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-214">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="a3da3-215">Para obter mais informações sobre por que usar a CDN do Office 365, os conceitos gerais da CDN e outras CDNs da Microsoft que você pode usar com seu locatário do Office 365, consulte [Redes](content-delivery-networks.md)de Entrega de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a3da3-215">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="a3da3-216">Origens padrão da CDN</span><span class="sxs-lookup"><span data-stu-id="a3da3-216">Default CDN origins</span></span>

<span data-ttu-id="a3da3-217">A menos que você especifique o contrário, o Office 365 configura algumas origens padrão para você ao habilitar a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3da3-217">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="a3da3-218">Se você optar inicialmente por não provisioná-las, poderá adicionar essas origens após concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="a3da3-218">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="a3da3-219">A menos que você entenda as consequências de ignorar a configuração de origens padrão e ter um motivo específico para fazer isso, você deve permitir que eles sejam criados quando você habilitar a CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-219">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="a3da3-220">Origens da CDN privada padrão:</span><span class="sxs-lookup"><span data-stu-id="a3da3-220">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="a3da3-221">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="a3da3-221">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="a3da3-222">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="a3da3-222">\*/siteassets</span></span>

<span data-ttu-id="a3da3-223">Origens de CDN pública padrão:</span><span class="sxs-lookup"><span data-stu-id="a3da3-223">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="a3da3-224">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="a3da3-224">\*/masterpage</span></span>
+ <span data-ttu-id="a3da3-225">\*/style library</span><span class="sxs-lookup"><span data-stu-id="a3da3-225">\*/style library</span></span>
+ <span data-ttu-id="a3da3-226">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="a3da3-226">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="a3da3-227">_clientsideassets_ é uma origem pública padrão que foi adicionada ao serviço CDN do Office 365 em dezembro de 2017.</span><span class="sxs-lookup"><span data-stu-id="a3da3-227">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="a3da3-228">Essa origem deve estar presente para que as soluções da Estrutura do SharePoint na CDN funcionem.</span><span class="sxs-lookup"><span data-stu-id="a3da3-228">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="a3da3-229">Se você habilitar a CDN do Office 365 antes de dezembro de 2017 ou se você ignorou a configuração de origens padrão ao habilitar a CDN, poderá adicionar manualmente essa origem.</span><span class="sxs-lookup"><span data-stu-id="a3da3-229">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="a3da3-230">Para obter mais informações, consulte [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span><span class="sxs-lookup"><span data-stu-id="a3da3-230">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="a3da3-231"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-231"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="a3da3-232">Configurar e configurar a CDN do Office 365 usando o Shell de Gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-232">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="a3da3-233">Os procedimentos nesta seção exigem que você use o Shell de Gerenciamento do SharePoint Online para se conectar ao SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a3da3-233">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="a3da3-234">Para obter instruções, [consulte Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="a3da3-234">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="a3da3-235">Conclua estas etapas para configurar e configurar a CDN para hospedar seus ativos no SharePoint Online usando o Shell de Gerenciamento do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a3da3-235">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="a3da3-236">Clique para expandir</span><span class="sxs-lookup"><span data-stu-id="a3da3-236">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="a3da3-237">Permitir que sua organização use a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-237">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-238">Antes de fazer alterações nas configurações de CDN do locatário, você deve recuperar o status atual da configuração da CDN privada em seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3da3-238">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="a3da3-239">Conecte-se ao seu locatário usando o Shell de Gerenciamento do SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="a3da3-239">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="a3da3-240">Agora use o cmdlet **Get-SPOTenantCdnEnabled** para recuperar as configurações de status da CDN do locatário:</span><span class="sxs-lookup"><span data-stu-id="a3da3-240">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="a3da3-241">O status da CDN do CdnType especificado será exibido na tela.</span><span class="sxs-lookup"><span data-stu-id="a3da3-241">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="a3da3-242">Use o cmdlet **Set-SPOTenantCdnEnabled** para permitir que sua organização use a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3da3-242">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="a3da3-243">Você pode permitir que sua organização use origens públicas, origens privadas ou ambas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="a3da3-243">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="a3da3-244">Você também pode configurar a CDN para ignorar a configuração de origens padrão ao habilita-la.</span><span class="sxs-lookup"><span data-stu-id="a3da3-244">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="a3da3-245">Você sempre pode adicionar essas origens mais tarde, conforme descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a3da3-245">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="a3da3-246">No Windows Powershell para SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="a3da3-246">In Windows Powershell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="a3da3-247">Por exemplo, para permitir que sua organização use origens públicas e privadas, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-247">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="a3da3-248">Para permitir que sua organização use origens públicas e privadas, mas ignore a configuração das origens padrão, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-248">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="a3da3-249">Consulte Origens de [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) padrão para obter informações sobre as origens provisionadas por padrão quando você habilita a CDN do Office 365 e o impacto potencial de ignorar a configuração de origens padrão.</span><span class="sxs-lookup"><span data-stu-id="a3da3-249">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="a3da3-250">Para permitir que sua organização use origens públicas, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-250">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="a3da3-251">Para permitir que sua organização use origens privadas, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-251">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="a3da3-252">Para obter mais informações sobre esse cmdlet, consulte [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span><span class="sxs-lookup"><span data-stu-id="a3da3-252">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

<span data-ttu-id="a3da3-253"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-253"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="a3da3-254">Alterar a lista de tipos de arquivo a incluir na CDN do Office 365 (Opcional)</span><span class="sxs-lookup"><span data-stu-id="a3da3-254">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="a3da3-255">Ao definir tipos de arquivo usando o cmdlet **Set-SPOTenantCdnPolicy,** você substitui a lista definida no momento.</span><span class="sxs-lookup"><span data-stu-id="a3da3-255">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="a3da3-256">Se você quiser adicionar tipos de arquivo adicionais à lista, use o cmdlet primeiro para descobrir quais tipos de arquivo já são permitidos e incluí-los na lista juntamente com os novos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-256">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="a3da3-257">Use o cmdlet **Set-SPOTenantCdnPolicy** para definir tipos de arquivo estáticos que podem ser hospedados por origens públicas e privadas na CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-257">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="a3da3-258">Por padrão, os tipos de ativos comuns são permitidos, por exemplo .css, .gif, .jpg e .js.</span><span class="sxs-lookup"><span data-stu-id="a3da3-258">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="a3da3-259">Em Windows PowerShell para SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="a3da3-259">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="a3da3-260">Por exemplo, para habilitar a CDN para hospedar arquivos .css e .png, você inseriria o comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-260">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="a3da3-261">Para ver quais tipos de arquivo atualmente são permitidos pela CDN, use o cmdlet **Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="a3da3-261">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="a3da3-262">Para obter mais informações sobre esses cmdlets, consulte [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) e [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span><span class="sxs-lookup"><span data-stu-id="a3da3-262">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="a3da3-263"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-263"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="a3da3-264">Alterar a lista de classificações de site que você deseja excluir da CDN do Office 365 (Opcional)</span><span class="sxs-lookup"><span data-stu-id="a3da3-264">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="a3da3-265">Ao excluir classificações de site usando o cmdlet **Set-SPOTenantCdnPolicy,** você substitui a lista definida no momento.</span><span class="sxs-lookup"><span data-stu-id="a3da3-265">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="a3da3-266">Se você quiser excluir classificações de site adicionais, use o cmdlet primeiro para descobrir quais classificações já estão excluídas e, em seguida, adicioná-las junto com as novas.</span><span class="sxs-lookup"><span data-stu-id="a3da3-266">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="a3da3-267">Use o cmdlet **Set-SPOTenantCdnPolicy** para excluir as classificações de site que não deseja disponibilizar na CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-267">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="a3da3-268">Por padrão, nenhuma classificação de sites é excluída.</span><span class="sxs-lookup"><span data-stu-id="a3da3-268">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="a3da3-269">Em Windows PowerShell para SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="a3da3-269">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="a3da3-270">Para ver quais classificações de site estão restritas no momento, use o cmdlet **Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="a3da3-270">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="a3da3-271">As propriedades que serão retornadas _são IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ e _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="a3da3-271">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="a3da3-272">A _propriedade IncludeFileExtensions_ contém a lista de extensões de arquivo que serão servidas da CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-272">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="a3da3-273">As extensões de arquivo padrão são diferentes entre público e privado.</span><span class="sxs-lookup"><span data-stu-id="a3da3-273">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="a3da3-274">A _propriedade ExcludeRestrictedSiteClassifications_ contém as classificações de site que você deseja excluir da CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-274">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="a3da3-275">Por exemplo, você pode excluir sites marcados como **Confidencial** para que o conteúdo de sites com essa classificação aplicada não seja servido da CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-275">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="a3da3-276">A _propriedade ExcludeIfNoScriptDisabled_ exclui o conteúdo da CDN com base nas configurações de atributo _NoScript_ no nível do site.</span><span class="sxs-lookup"><span data-stu-id="a3da3-276">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="a3da3-277">Por padrão, o atributo _NoScript_ é definido como **Habilitado para** Sites _Modernos_ e **Desabilitado** para sites _clássicos._</span><span class="sxs-lookup"><span data-stu-id="a3da3-277">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="a3da3-278">Isso depende das configurações do locatário.</span><span class="sxs-lookup"><span data-stu-id="a3da3-278">This depends on your tenant settings.</span></span>

<span data-ttu-id="a3da3-279">Para obter mais informações sobre esses cmdlets, consulte [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) e [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span><span class="sxs-lookup"><span data-stu-id="a3da3-279">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="a3da3-280"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-280"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="a3da3-281">Adicionar uma origem para seus ativos</span><span class="sxs-lookup"><span data-stu-id="a3da3-281">Add an origin for your assets</span></span>

<span data-ttu-id="a3da3-282">Use o cmdlet **Add-SPOTenantCdnOrigin** para definir uma origem.</span><span class="sxs-lookup"><span data-stu-id="a3da3-282">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="a3da3-283">Você pode definir várias origens.</span><span class="sxs-lookup"><span data-stu-id="a3da3-283">You can define multiple origins.</span></span> <span data-ttu-id="a3da3-284">A origem é uma URL que aponta para uma biblioteca ou pasta do SharePoint contendo os ativos que você deseja hospedar na CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-284">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a3da3-285">Você nunca deve colocar recursos que contenham informações do usuário ou sejam considerados confidenciais para sua organização em uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="a3da3-285">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="a3da3-286">O valor do _caminho_ é o caminho relativo para a biblioteca ou pasta que contém os ativos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-286">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="a3da3-287">Você pode usar caracteres curinga, além de caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-287">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="a3da3-288">As origens suportam curingas pré-anexados à URL.</span><span class="sxs-lookup"><span data-stu-id="a3da3-288">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="a3da3-289">Isso permite que você crie origens que abrangem vários sites.</span><span class="sxs-lookup"><span data-stu-id="a3da3-289">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="a3da3-290">Por exemplo, para incluir todos os ativos na pasta páginas mestras de todos os seus sites como uma origem pública dentro da CDN, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-290">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="a3da3-291">O modificador de caractere curinga \* só pode ser usado no início do caminho e corresponderá a todos os **/** segmentos de URL na URL especificada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-291">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="a3da3-292">O caminho pode apontar para uma biblioteca de documentos, pasta ou site.</span><span class="sxs-lookup"><span data-stu-id="a3da3-292">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="a3da3-293">Por exemplo, o caminho _\*/site1_ corresponderá a todas as bibliotecas de documentos no site.</span><span class="sxs-lookup"><span data-stu-id="a3da3-293">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="a3da3-294">Você pode adicionar uma origem com um caminho relativo específico.</span><span class="sxs-lookup"><span data-stu-id="a3da3-294">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="a3da3-295">Não é possível adicionar uma origem usando o caminho completo.</span><span class="sxs-lookup"><span data-stu-id="a3da3-295">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="a3da3-296">Este exemplo adiciona uma origem privada da biblioteca de sitesassets em um site específico:</span><span class="sxs-lookup"><span data-stu-id="a3da3-296">This example adds a private origin of the siteassets library on a specific site:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="a3da3-297">Este exemplo adiciona uma origem privada da _pasta1_ na biblioteca de ativos de site do conjunto de sites:</span><span class="sxs-lookup"><span data-stu-id="a3da3-297">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="a3da3-298">Se houver um espaço no caminho, você poderá cercar o caminho entre aspas duplas ou substituir o espaço pela codificação de URL %20.</span><span class="sxs-lookup"><span data-stu-id="a3da3-298">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="a3da3-299">Os exemplos a seguir adicionam uma origem privada da pasta _1_ na biblioteca de ativos de site do conjunto de sites:</span><span class="sxs-lookup"><span data-stu-id="a3da3-299">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="a3da3-300">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="a3da3-300">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

> [!NOTE]
> <span data-ttu-id="a3da3-301">Em origens privadas, os ativos compartilhados de uma origem devem ter uma versão principal publicada antes de serem acessados pela CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-301">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="a3da3-302">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="a3da3-302">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a3da3-303">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-303">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a3da3-304"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-304"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="a3da3-305">Exemplo: configurar uma origem pública para suas páginas mestras e para sua biblioteca de estilos para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-305">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="a3da3-306">Normalmente, essas origens são configuradas para você por padrão quando você habilita a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3da3-306">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="a3da3-307">No entanto, se você quiser habilita-los manualmente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a3da3-307">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="a3da3-308">Use o cmdlet **Add-SPOTenantCdnOrigin** para definir a biblioteca de estilos como uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="a3da3-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="a3da3-309">Use o cmdlet **Add-SPOTenantCdnOrigin** para definir as páginas mestras como uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="a3da3-309">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="a3da3-310">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="a3da3-310">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="a3da3-311">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="a3da3-311">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a3da3-312">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-312">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a3da3-313"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-313"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="a3da3-314">Exemplo: configurar uma origem privada para seus ativos de site, páginas de site e imagens de publicação para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-314">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="a3da3-315">Use o cmdlet **Add-SPOTenantCdnOrigin** para definir a pasta de ativos do site como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="a3da3-316">Use o cmdlet **Add-SPOTenantCdnOrigin** para definir a pasta de páginas do site como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="a3da3-317">Use o cmdlet **Add-SPOTenantCdnOrigin** para definir a pasta de imagens de publicação como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-317">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="a3da3-318">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="a3da3-318">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="a3da3-319">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="a3da3-319">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a3da3-320">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-320">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a3da3-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="a3da3-322">Exemplo: configurar uma origem privada para um conjunto de sites para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-322">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="a3da3-323">Use o cmdlet **Add-SPOTenantCdnOrigin** para definir um conjunto de sites como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-323">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="a3da3-324">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a3da3-324">For example:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="a3da3-325">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="a3da3-325">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>
  
<span data-ttu-id="a3da3-326">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="a3da3-326">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a3da3-327">Você pode ver uma _mensagem de configuração_ pendente que é esperada à medida que o locatário do SharePoint Online se conecta ao serviço CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-327">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="a3da3-328">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-328">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a3da3-329"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-329"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="a3da3-330">Gerenciar a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-330">Manage the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-331">Depois de configurar a CDN, você pode fazer alterações na configuração conforme atualiza o conteúdo ou conforme suas necessidades mudam, conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="a3da3-331">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="a3da3-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="a3da3-333">Adicionar, atualizar ou remover ativos da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-333">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-334">Depois de concluir as etapas de instalação, você pode adicionar novos ativos e atualizar ou remover ativos existentes sempre que quiser.</span><span class="sxs-lookup"><span data-stu-id="a3da3-334">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="a3da3-335">Basta fazer suas alterações nos ativos na pasta ou na biblioteca do SharePoint que você identificou como uma origem.</span><span class="sxs-lookup"><span data-stu-id="a3da3-335">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="a3da3-336">Se você adicionar um novo ativo, ele estará disponível por meio da CDN imediatamente.</span><span class="sxs-lookup"><span data-stu-id="a3da3-336">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="a3da3-337">No entanto, se você atualizar o ativo, levará até 15 minutos para que a nova cópia se propague e se torne disponível na CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-337">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="a3da3-338">Se você precisar recuperar o local da origem, poderá usar o cmdlet **Get-SPOTenantCdnOrigins.**</span><span class="sxs-lookup"><span data-stu-id="a3da3-338">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="a3da3-339">Para obter informações sobre como usar esse cmdlet, consulte [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span><span class="sxs-lookup"><span data-stu-id="a3da3-339">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span></span>

<span data-ttu-id="a3da3-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="a3da3-341">Remover uma origem da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-341">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-342">Você pode remover o acesso a uma pasta ou biblioteca do SharePoint que você identificou como uma origem.</span><span class="sxs-lookup"><span data-stu-id="a3da3-342">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="a3da3-343">Para fazer isso, use o cmdlet **Remove-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="a3da3-343">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="a3da3-344">Para obter informações sobre como usar esse cmdlet, consulte [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="a3da3-344">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="a3da3-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="a3da3-346">Modificar uma origem na CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-346">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-347">Não é possível modificar uma origem criada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-347">You cannot modify an origin you've created.</span></span> <span data-ttu-id="a3da3-348">Em vez disso, remova a origem e adicione um novo.</span><span class="sxs-lookup"><span data-stu-id="a3da3-348">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="a3da3-349">Para obter mais informações, consulte Para remover uma origem da CDN do [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) e Para adicionar uma [origem para seus ativos](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span><span class="sxs-lookup"><span data-stu-id="a3da3-349">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="a3da3-350"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-350"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="a3da3-351">Desabilitar a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-351">Disable the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-352">Use o cmdlet **Set-SPOTenantCdnEnabled para** desabilitar a CDN da sua organização.</span><span class="sxs-lookup"><span data-stu-id="a3da3-352">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="a3da3-353">Se você tiver as origens públicas e privadas habilitadas para a CDN, será necessário executar o cmdlet duas vezes, conforme mostrado nos exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="a3da3-353">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="a3da3-354">Para desabilitar o uso de origens públicas na CDN, insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-354">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="a3da3-355">Para desabilitar o uso das origens privadas na CDN, insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-355">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="a3da3-356">Para obter mais informações sobre esse cmdlet, consulte [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span><span class="sxs-lookup"><span data-stu-id="a3da3-356">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

</details>

<span data-ttu-id="a3da3-357"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-357"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="a3da3-358">Configurar e configurar a CDN do Office 365 usando o PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3da3-358">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="a3da3-359">Os procedimentos nesta seção exigem que você use o PnP PowerShell para se conectar ao SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a3da3-359">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="a3da3-360">Para obter instruções, consulte [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span><span class="sxs-lookup"><span data-stu-id="a3da3-360">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="a3da3-361">Conclua estas etapas para configurar e configurar a CDN para hospedar seus ativos no SharePoint Online usando o PnP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3da3-361">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="a3da3-362">Clique para expandir</span><span class="sxs-lookup"><span data-stu-id="a3da3-362">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="a3da3-363">Permitir que sua organização use a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-363">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-364">Antes de fazer alterações nas configurações de CDN do locatário, você deve recuperar o status atual da configuração da CDN privada em seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3da3-364">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="a3da3-365">Conecte-se ao locatário usando o PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a3da3-365">Connect to your tenant using PnP PowerShell:</span></span>

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="a3da3-366">Agora use o cmdlet **Get-PnPTenantCdnEnabled** para recuperar as configurações de status da CDN do locatário:</span><span class="sxs-lookup"><span data-stu-id="a3da3-366">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="a3da3-367">O status da CDN do CdnType especificado será exibido na tela.</span><span class="sxs-lookup"><span data-stu-id="a3da3-367">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="a3da3-368">Use o cmdlet **Set-PnPTenantCdnEnabled** para permitir que sua organização use a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3da3-368">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="a3da3-369">Você pode permitir que sua organização use origens públicas, origens privadas ou ambas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="a3da3-369">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="a3da3-370">Você também pode configurar a CDN para ignorar a configuração de origens padrão ao habilita-la.</span><span class="sxs-lookup"><span data-stu-id="a3da3-370">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="a3da3-371">Você sempre pode adicionar essas origens mais tarde, conforme descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="a3da3-371">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="a3da3-372">No PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a3da3-372">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="a3da3-373">Por exemplo, para permitir que sua organização use origens públicas e privadas, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-373">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="a3da3-374">Para permitir que sua organização use origens públicas e privadas, mas ignore a configuração das origens padrão, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-374">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="a3da3-375">Consulte Origens de [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) padrão para obter informações sobre as origens provisionadas por padrão quando você habilita a CDN do Office 365 e o impacto potencial de ignorar a configuração de origens padrão.</span><span class="sxs-lookup"><span data-stu-id="a3da3-375">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="a3da3-376">Para permitir que sua organização use origens públicas, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-376">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="a3da3-377">Para permitir que sua organização use origens privadas, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-377">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="a3da3-378">Para obter mais informações sobre esse cmdlet, consulte [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span><span class="sxs-lookup"><span data-stu-id="a3da3-378">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="a3da3-379"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-379"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="a3da3-380">Alterar a lista de tipos de arquivo a incluir na CDN do Office 365 (Opcional)</span><span class="sxs-lookup"><span data-stu-id="a3da3-380">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="a3da3-381">Ao definir tipos de arquivo usando o cmdlet **Set-PnPTenantCdnPolicy,** você substitui a lista definida no momento.</span><span class="sxs-lookup"><span data-stu-id="a3da3-381">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="a3da3-382">Se você quiser adicionar tipos de arquivo adicionais à lista, use o cmdlet primeiro para descobrir quais tipos de arquivo já são permitidos e incluí-los na lista juntamente com os novos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-382">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="a3da3-383">Use o cmdlet **Set-PnPTenantCdnPolicy** para definir tipos de arquivo estáticos que podem ser hospedados por origens públicas e privadas na CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-383">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="a3da3-384">Por padrão, os tipos de ativos comuns são permitidos, por exemplo .css, .gif, .jpg e .js.</span><span class="sxs-lookup"><span data-stu-id="a3da3-384">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="a3da3-385">No PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a3da3-385">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="a3da3-386">Por exemplo, para habilitar a CDN para hospedar arquivos .css e .png, você inseriria o comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-386">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="a3da3-387">Para ver quais tipos de arquivo atualmente são permitidos pela CDN, use o cmdlet **Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="a3da3-387">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="a3da3-388">Para obter mais informações sobre esses cmdlets, consulte [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="a3da3-388">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="a3da3-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="a3da3-390">Alterar a lista de classificações de site que você deseja excluir da CDN do Office 365 (Opcional)</span><span class="sxs-lookup"><span data-stu-id="a3da3-390">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="a3da3-391">Quando você exclui classificações de site usando o cmdlet **Set-PnPTenantCdnPolicy,** substitui a lista definida no momento.</span><span class="sxs-lookup"><span data-stu-id="a3da3-391">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="a3da3-392">Se você quiser excluir classificações de site adicionais, use o cmdlet primeiro para descobrir quais classificações já estão excluídas e, em seguida, adicioná-las junto com as novas.</span><span class="sxs-lookup"><span data-stu-id="a3da3-392">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="a3da3-393">Use o cmdlet **Set-PnPTenantCdnPolicy** para excluir classificações de site que você não deseja disponibilizar pela CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-393">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="a3da3-394">Por padrão, nenhuma classificação de sites é excluída.</span><span class="sxs-lookup"><span data-stu-id="a3da3-394">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="a3da3-395">No PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a3da3-395">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="a3da3-396">Para ver quais classificações de site estão restritas no momento, use o cmdlet **Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="a3da3-396">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="a3da3-397">As propriedades que serão retornadas _são IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ e _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="a3da3-397">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="a3da3-398">A _propriedade IncludeFileExtensions_ contém a lista de extensões de arquivo que serão servidas da CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-398">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="a3da3-399">As extensões de arquivo padrão são diferentes entre público e privado.</span><span class="sxs-lookup"><span data-stu-id="a3da3-399">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="a3da3-400">A _propriedade ExcludeRestrictedSiteClassifications_ contém as classificações de site que você deseja excluir da CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-400">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="a3da3-401">Por exemplo, você pode excluir sites marcados como **Confidencial** para que o conteúdo de sites com essa classificação aplicada não seja servido da CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-401">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="a3da3-402">A _propriedade ExcludeIfNoScriptDisabled_ exclui o conteúdo da CDN com base nas configurações de atributo _NoScript_ no nível do site.</span><span class="sxs-lookup"><span data-stu-id="a3da3-402">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="a3da3-403">Por padrão, o atributo _NoScript_ é definido como **Habilitado para** Sites _Modernos_ e **Desabilitado** para sites _clássicos._</span><span class="sxs-lookup"><span data-stu-id="a3da3-403">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="a3da3-404">Isso depende das configurações do locatário.</span><span class="sxs-lookup"><span data-stu-id="a3da3-404">This depends on your tenant settings.</span></span>

<span data-ttu-id="a3da3-405">Para obter mais informações sobre esses cmdlets, consulte [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="a3da3-405">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="a3da3-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="a3da3-407">Adicionar uma origem para seus ativos</span><span class="sxs-lookup"><span data-stu-id="a3da3-407">Add an origin for your assets</span></span>

<span data-ttu-id="a3da3-408">Use o cmdlet **Add-PnPTenantCdnOrigin** para definir uma origem.</span><span class="sxs-lookup"><span data-stu-id="a3da3-408">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="a3da3-409">Você pode definir várias origens.</span><span class="sxs-lookup"><span data-stu-id="a3da3-409">You can define multiple origins.</span></span> <span data-ttu-id="a3da3-410">A origem é uma URL que aponta para uma biblioteca ou pasta do SharePoint contendo os ativos que você deseja hospedar na CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-410">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a3da3-411">Você nunca deve colocar recursos que contenham informações do usuário ou sejam considerados confidenciais para sua organização em uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="a3da3-411">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="a3da3-412">O valor do _caminho_ é o caminho relativo para a biblioteca ou pasta que contém os ativos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-412">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="a3da3-413">Você pode usar caracteres curinga, além de caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-413">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="a3da3-414">As origens suportam curingas pré-anexados à URL.</span><span class="sxs-lookup"><span data-stu-id="a3da3-414">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="a3da3-415">Isso permite que você crie origens que abrangem vários sites.</span><span class="sxs-lookup"><span data-stu-id="a3da3-415">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="a3da3-416">Por exemplo, para incluir todos os ativos na pasta páginas mestras de todos os seus sites como uma origem pública dentro da CDN, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-416">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="a3da3-417">O modificador de caractere curinga \* só pode ser usado no início do caminho e corresponderá a todos os **/** segmentos de URL na URL especificada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-417">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="a3da3-418">O caminho pode apontar para uma biblioteca de documentos, pasta ou site.</span><span class="sxs-lookup"><span data-stu-id="a3da3-418">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="a3da3-419">Por exemplo, o caminho _\*/site1_ corresponderá a todas as bibliotecas de documentos no site.</span><span class="sxs-lookup"><span data-stu-id="a3da3-419">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="a3da3-420">Você pode adicionar uma origem com um caminho relativo específico.</span><span class="sxs-lookup"><span data-stu-id="a3da3-420">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="a3da3-421">Não é possível adicionar uma origem usando o caminho completo.</span><span class="sxs-lookup"><span data-stu-id="a3da3-421">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="a3da3-422">Este exemplo adiciona uma origem privada da biblioteca de ativos do site em um site específico:</span><span class="sxs-lookup"><span data-stu-id="a3da3-422">This example adds a private origin of the site assets library on a specific site:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="a3da3-423">Este exemplo adiciona uma origem privada da _pasta1_ na biblioteca de ativos de site do conjunto de sites:</span><span class="sxs-lookup"><span data-stu-id="a3da3-423">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="a3da3-424">Se houver um espaço no caminho, você poderá cercar o caminho entre aspas duplas ou substituir o espaço pela codificação de URL %20.</span><span class="sxs-lookup"><span data-stu-id="a3da3-424">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="a3da3-425">Os exemplos a seguir adicionam uma origem privada da pasta _1_ na biblioteca de ativos de site do conjunto de sites:</span><span class="sxs-lookup"><span data-stu-id="a3da3-425">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="a3da3-426">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="a3da3-426">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="a3da3-427">Em origens privadas, os ativos compartilhados de uma origem devem ter uma versão principal publicada antes de serem acessados pela CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-427">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="a3da3-428">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="a3da3-428">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a3da3-429">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-429">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a3da3-430"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-430"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="a3da3-431">Exemplo: configurar uma origem pública para suas páginas mestras e para sua biblioteca de estilos para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-431">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="a3da3-432">Normalmente, essas origens são configuradas para você por padrão quando você habilita a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3da3-432">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="a3da3-433">No entanto, se você quiser habilita-los manualmente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a3da3-433">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="a3da3-434">Use o cmdlet **Add-PnPTenantCdnOrigin** para definir a biblioteca de estilos como uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="a3da3-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="a3da3-435">Use o cmdlet **Add-PnPTenantCdnOrigin** para definir as páginas mestras como uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="a3da3-435">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="a3da3-436">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="a3da3-436">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="a3da3-437">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="a3da3-437">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a3da3-438">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-438">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a3da3-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="a3da3-440">Exemplo: configurar uma origem privada para seus ativos de site, páginas de site e imagens de publicação para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-440">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="a3da3-441">Use o cmdlet **Add-PnPTenantCdnOrigin** para definir a pasta de ativos do site como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="a3da3-442">Use o cmdlet **Add-PnPTenantCdnOrigin** para definir a pasta de páginas do site como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="a3da3-443">Use o cmdlet **Add-PnPTenantCdnOrigin** para definir a pasta de imagens de publicação como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-443">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="a3da3-444">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="a3da3-444">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="a3da3-445">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="a3da3-445">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a3da3-446">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-446">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a3da3-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="a3da3-448">Exemplo: configurar uma origem privada para um conjunto de sites para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-448">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="a3da3-449">Use o cmdlet **Add-PnPTenantCdnOrigin** para definir um conjunto de sites como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-449">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="a3da3-450">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a3da3-450">For example:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="a3da3-451">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="a3da3-451">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="a3da3-452">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="a3da3-452">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="a3da3-453">Você pode ver uma _mensagem de configuração_ pendente que é esperada à medida que o locatário do SharePoint Online se conecta ao serviço CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-453">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="a3da3-454">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-454">This can take up to 15 minutes.</span></span>

<span data-ttu-id="a3da3-455"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-455"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="a3da3-456">Gerenciar a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-456">Manage the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-457">Depois de configurar a CDN, você pode fazer alterações na configuração conforme atualiza o conteúdo ou conforme suas necessidades mudam, conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="a3da3-457">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="a3da3-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="a3da3-459">Adicionar, atualizar ou remover ativos da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-459">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-460">Depois de concluir as etapas de instalação, você pode adicionar novos ativos e atualizar ou remover ativos existentes sempre que quiser.</span><span class="sxs-lookup"><span data-stu-id="a3da3-460">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="a3da3-461">Basta fazer suas alterações nos ativos na pasta ou na biblioteca do SharePoint que você identificou como uma origem.</span><span class="sxs-lookup"><span data-stu-id="a3da3-461">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="a3da3-462">Se você adicionar um novo ativo, ele estará disponível por meio da CDN imediatamente.</span><span class="sxs-lookup"><span data-stu-id="a3da3-462">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="a3da3-463">No entanto, se você atualizar o ativo, levará até 15 minutos para que a nova cópia se propague e se torne disponível na CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-463">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="a3da3-464">Se você precisar recuperar o local da origem, poderá usar o cmdlet **Get-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="a3da3-464">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="a3da3-465">Para obter informações sobre como usar esse cmdlet, consulte [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="a3da3-465">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="a3da3-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="a3da3-467">Remover uma origem da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-467">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-468">Você pode remover o acesso a uma pasta ou biblioteca do SharePoint que você identificou como uma origem.</span><span class="sxs-lookup"><span data-stu-id="a3da3-468">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="a3da3-469">Para fazer isso, use o cmdlet **Remove-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="a3da3-469">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="a3da3-470">Para obter informações sobre como usar esse cmdlet, consulte [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="a3da3-470">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="a3da3-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="a3da3-472">Modificar uma origem na CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-472">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-473">Não é possível modificar uma origem criada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-473">You cannot modify an origin you've created.</span></span> <span data-ttu-id="a3da3-474">Em vez disso, remova a origem e adicione um novo.</span><span class="sxs-lookup"><span data-stu-id="a3da3-474">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="a3da3-475">Para obter mais informações, consulte Para remover uma origem da CDN do [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) e Para adicionar uma [origem para seus ativos](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span><span class="sxs-lookup"><span data-stu-id="a3da3-475">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="a3da3-476"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-476"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="a3da3-477">Desabilitar a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-477">Disable the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-478">Use o cmdlet **Set-PnPTenantCdnEnabled** para desabilitar a CDN da sua organização.</span><span class="sxs-lookup"><span data-stu-id="a3da3-478">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="a3da3-479">Se você tiver as origens públicas e privadas habilitadas para a CDN, será necessário executar o cmdlet duas vezes, conforme mostrado nos exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="a3da3-479">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="a3da3-480">Para desabilitar o uso de origens públicas na CDN, insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-480">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="a3da3-481">Para desabilitar o uso das origens privadas na CDN, insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a3da3-481">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="a3da3-482">Para obter mais informações sobre esse cmdlet, consulte [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span><span class="sxs-lookup"><span data-stu-id="a3da3-482">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="a3da3-483"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-483"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="a3da3-484">Instalação e configuração da CDN do Office 365 usando a CLI do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-484">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="a3da3-485">Os procedimentos nesta seção exigem que você tenha instalado a CLI do [Office 365](https://aka.ms/o365cli).</span><span class="sxs-lookup"><span data-stu-id="a3da3-485">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="a3da3-486">Em seguida, conecte-se ao locatário do Office 365 usando o [comando de logon.](https://pnp.github.io/office365-cli/cmd/login/)</span><span class="sxs-lookup"><span data-stu-id="a3da3-486">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="a3da3-487">Conclua estas etapas para configurar e configurar a CDN para hospedar seus ativos no SharePoint Online usando a CLI do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3da3-487">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="a3da3-488">Clique para expandir</span><span class="sxs-lookup"><span data-stu-id="a3da3-488">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="a3da3-489">Habilitar a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-489">Enable the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-490">Você pode gerenciar o estado da CDN do Office 365 no locatário usando o comando [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/).</span><span class="sxs-lookup"><span data-stu-id="a3da3-490">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="a3da3-491">Para habilitar a CDN pública do Office 365 no locatário:</span><span class="sxs-lookup"><span data-stu-id="a3da3-491">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```sh
spo cdn set --type Public --enabled true
```

<span data-ttu-id="a3da3-492">Para habilitar a CDN do SharePoint do Office 365, execute:</span><span class="sxs-lookup"><span data-stu-id="a3da3-492">To enable the Office 365 SharePoint CDN, execute:</span></span>

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="a3da3-493">Exiba o status atual da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-493">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-494">Para verificar se o tipo específico de CDN do Office 365 está habilitado ou desabilitado, use o comando [spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)</span><span class="sxs-lookup"><span data-stu-id="a3da3-494">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="a3da3-495">Para verificar se a CDN pública do Office 365 está habilitada:</span><span class="sxs-lookup"><span data-stu-id="a3da3-495">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="a3da3-496">Exibir as origens da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-496">View the Office 365 CDN origins</span></span>

<span data-ttu-id="a3da3-497">Para exibir as origens de CDN pública do Office 365 configuradas no momento:</span><span class="sxs-lookup"><span data-stu-id="a3da3-497">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```sh
spo cdn origin list --type Public
```

<span data-ttu-id="a3da3-498">Consulte [Origens padrão da CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) para obter informações sobre as origens provisionadas por padrão ao habilitar a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a3da3-498">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="a3da3-499">Adicionar uma origem cdn do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-499">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3da3-500">Você nunca deve colocar recursos considerados confidenciais para sua organização em uma biblioteca de documentos do SharePoint configurada como uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="a3da3-500">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="a3da3-501">Use o adicionar comando [spo cdn origem ](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) para definir uma origem de CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-501">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="a3da3-502">Você pode definir várias origens.</span><span class="sxs-lookup"><span data-stu-id="a3da3-502">You can define multiple origins.</span></span> <span data-ttu-id="a3da3-503">A origem é uma URL que aponta para uma biblioteca ou pasta do SharePoint contendo os ativos que você deseja hospedar na CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-503">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="a3da3-504">Onde `path` está o caminho relativo para a pasta que contém os ativos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-504">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="a3da3-505">Você pode usar caracteres curinga, além de caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-505">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="a3da3-506">Para incluir todos os ativos na **Galeria de Páginas Mestras** de todos os sites como uma origem pública, execute:</span><span class="sxs-lookup"><span data-stu-id="a3da3-506">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```sh
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="a3da3-507">Para configurar uma origem privada para um conjunto de sites específico:</span><span class="sxs-lookup"><span data-stu-id="a3da3-507">To configure a private origin for a specific site collection, execute:</span></span>

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="a3da3-508">Após adicionar uma origem de CDN, pode levar até 15 minutos para que você possa recuperar arquivos por meio do serviço de CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-508">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="a3da3-509">Você pode verificar se a origem específica já foi ativada usando o comando [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/).</span><span class="sxs-lookup"><span data-stu-id="a3da3-509">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="a3da3-510">Remover uma origem da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-510">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="a3da3-511">Use o comando [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) para remover uma origem de CDN para o tipo de CDN especificado.</span><span class="sxs-lookup"><span data-stu-id="a3da3-511">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="a3da3-512">Para remover uma origem pública da configuração da CDN, execute:</span><span class="sxs-lookup"><span data-stu-id="a3da3-512">To remove a public origin from the CDN configuration, execute:</span></span>

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="a3da3-513">Remover uma origem da CDN não afeta os arquivos armazenados em qualquer biblioteca de documentos que corresponde a essa origem.</span><span class="sxs-lookup"><span data-stu-id="a3da3-513">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="a3da3-514">Se esses ativos foram referenciados usando a URL do SharePoint, o SharePoint alterna automaticamente para a URL original apontando para a biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-514">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="a3da3-515">No entanto, se os ativos foram referenciados usando uma URL de CDN pública, remover a origem quebrará o link e você precisará alterá-los manualmente.</span><span class="sxs-lookup"><span data-stu-id="a3da3-515">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="a3da3-516">Modificar uma origem da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-516">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="a3da3-517">Não é possível alterar uma origem de CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-517">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="a3da3-518">Em vez disso, você deve remover a origem de CDN definida anteriormente usando o comando `spo cdn origin remove` e adicionar outro usando o comando `spo cdn origin add`.</span><span class="sxs-lookup"><span data-stu-id="a3da3-518">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="a3da3-519">Alterar os tipos de arquivos a incluir na CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-519">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-520">Por padrão, os seguintes tipos de arquivo são incluídos na CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff e .woff2_.</span><span class="sxs-lookup"><span data-stu-id="a3da3-520">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="a3da3-521">Se precisar incluir outros tipos de arquivo na CDN, você pode alterar a configuração de CDN usando o comando [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/).</span><span class="sxs-lookup"><span data-stu-id="a3da3-521">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="a3da3-522">Ao alterar a lista de tipos de arquivo, você substitui a lista definida no momento.</span><span class="sxs-lookup"><span data-stu-id="a3da3-522">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="a3da3-523">Se quiser incluir outros tipos de arquivo, primeiro use o comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) para descobrir quais tipos de arquivo estão configurados no momento.</span><span class="sxs-lookup"><span data-stu-id="a3da3-523">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="a3da3-524">Para adicionar o _tipo de arquivo JSON_ à lista padrão de tipos de arquivo incluídos na CDN pública, execute:</span><span class="sxs-lookup"><span data-stu-id="a3da3-524">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="a3da3-525">Altere a lista de classificações de site que você deseja excluir da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-525">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-526">Use o comando [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) para excluir as classificações de site que não deseja disponibilizar na CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-526">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="a3da3-527">Por padrão, nenhuma classificação de sites é excluída.</span><span class="sxs-lookup"><span data-stu-id="a3da3-527">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="a3da3-528">Ao alterar a lista de classificações de sites excluída, você substitui a lista definida no momento.</span><span class="sxs-lookup"><span data-stu-id="a3da3-528">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="a3da3-529">Se desejar excluir outras classificações, primeiro use o comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) para descobrir quais classificações estão configuradas no momento.</span><span class="sxs-lookup"><span data-stu-id="a3da3-529">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="a3da3-530">Para excluir sites classificados como _HBI_ da CDN pública, execute</span><span class="sxs-lookup"><span data-stu-id="a3da3-530">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="a3da3-531">Desabilitar a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-531">Disable the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-532">Para desabilitar a CDN do Office 365, use o comando `spo cdn set`, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a3da3-532">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="a3da3-533">Usando seus ativos CDN</span><span class="sxs-lookup"><span data-stu-id="a3da3-533">Using your CDN assets</span></span>

<span data-ttu-id="a3da3-534">Agora que você habilitar a CDN e configurou origens e políticas, você pode começar a usar seus ativos cdn.</span><span class="sxs-lookup"><span data-stu-id="a3da3-534">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="a3da3-535">Esta seção ajudará você a entender como usar URLs de CDN em suas páginas e conteúdo do SharePoint para que o SharePoint redirecione solicitações de ativos em origens públicas e privadas para a CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-535">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="a3da3-536">Atualizando links para ativos CDN</span><span class="sxs-lookup"><span data-stu-id="a3da3-536">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="a3da3-537">Usando ativos em origens públicas</span><span class="sxs-lookup"><span data-stu-id="a3da3-537">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="a3da3-538">Usando ativos em origens privadas</span><span class="sxs-lookup"><span data-stu-id="a3da3-538">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="a3da3-539">Para obter informações sobre como usar a CDN para hospedar web parts do lado do cliente, consulte o tópico Hospedar sua Web Part do lado do cliente da CDN do [Office 365 (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span><span class="sxs-lookup"><span data-stu-id="a3da3-539">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="a3da3-540">Se você adicionar a _pasta ClientSideAssets_ à lista de origens da **CDN** privada, as Web Parts personalizadas hospedadas pela CDN falharão ao renderizar.</span><span class="sxs-lookup"><span data-stu-id="a3da3-540">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="a3da3-541">Os arquivos usados pelas Web Parts SPFX só podem utilizar a CDN pública e a pasta ClientSideAssets é uma origem padrão para a CDN pública.</span><span class="sxs-lookup"><span data-stu-id="a3da3-541">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="a3da3-542">Atualizando links para ativos CDN</span><span class="sxs-lookup"><span data-stu-id="a3da3-542">Updating links to CDN assets</span></span>

<span data-ttu-id="a3da3-543">Para usar ativos adicionados a uma origem, basta atualizar links para o arquivo original com o caminho para o arquivo na origem.</span><span class="sxs-lookup"><span data-stu-id="a3da3-543">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="a3da3-544">Edite a página ou o conteúdo que contém links para ativos que você adicionou a uma origem.</span><span class="sxs-lookup"><span data-stu-id="a3da3-544">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="a3da3-545">Você também pode usar um dos vários métodos para pesquisar globalmente e substituir links em um site de entrada ou conjunto de sites se quiser atualizar o link para um determinado ativo em todos os lugares em que ele aparecer.</span><span class="sxs-lookup"><span data-stu-id="a3da3-545">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="a3da3-546">Para cada link para um ativo em uma origem, substitua o caminho pelo caminho para o arquivo na origem da CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-546">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="a3da3-547">Você pode usar caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-547">You can use relative paths.</span></span>
+ <span data-ttu-id="a3da3-548">Salve a página ou o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a3da3-548">Save the page or content.</span></span>

<span data-ttu-id="a3da3-549">Por exemplo, considere a imagem _/site/SiteAssets/images/image.png_, que você copiou para a pasta da biblioteca de documentos _/site/CDN_origins/public/_.</span><span class="sxs-lookup"><span data-stu-id="a3da3-549">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="a3da3-550">Para usar o ativo CDN, substitua o caminho original para o local do arquivo de imagem pelo caminho para a origem para tornar a nova URL _/site/CDN_origins/public/image.png_.</span><span class="sxs-lookup"><span data-stu-id="a3da3-550">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="a3da3-551">Se você quiser usar a URL completa para o ativo em vez de um caminho relativo, construa o link assim:</span><span class="sxs-lookup"><span data-stu-id="a3da3-551">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="a3da3-552">Em geral, você não deve codificar URLs diretamente para ativos na CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-552">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="a3da3-553">No entanto, você pode construir manualmente URLs para ativos em origens públicas, se necessário.</span><span class="sxs-lookup"><span data-stu-id="a3da3-553">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="a3da3-554">Para obter mais informações, consulte [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span><span class="sxs-lookup"><span data-stu-id="a3da3-554">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="a3da3-555">Para saber mais sobre como verificar se os ativos estão sendo atendidos na CDN, consulte Como confirmar se os ativos estão sendo atendidos pela [CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) na seção Solução de problemas da CDN do [Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="a3da3-555">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in the [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) section.</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="a3da3-556">Usando ativos em origens públicas</span><span class="sxs-lookup"><span data-stu-id="a3da3-556">Using assets in public origins</span></span>

<span data-ttu-id="a3da3-557">O **recurso de** publicação no SharePoint Online regrava automaticamente URLs de ativos armazenados em origens públicas para seus equivalentes de CDN para que os ativos sejam atendidos do serviço CDN em vez do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a3da3-557">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="a3da3-558">Se sua origem estiver em um site com o recurso de Publicação habilitado e os ativos que você deseja descarregar para a CDN estão em uma das seguintes categorias, o SharePoint reescreverá automaticamente URLs para ativos na origem, desde que o ativo não tenha sido excluído por uma política de CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-558">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="a3da3-559">Mostramos a seguir uma visão geral dos links reescritos automaticamente pelo recurso de Publicação do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="a3da3-559">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="a3da3-560">URLs IMG/LINK/CSS em respostas de HTML de página de publicação clássica</span><span class="sxs-lookup"><span data-stu-id="a3da3-560">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="a3da3-561">Incluem-se imagens adicionadas por autores no conteúdo HTML de uma página</span><span class="sxs-lookup"><span data-stu-id="a3da3-561">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="a3da3-562">URLs de imagem da web part Apresentação de Slides da Biblioteca de Imagens</span><span class="sxs-lookup"><span data-stu-id="a3da3-562">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="a3da3-563">Campos de imagem nos resultados da API REST SPList (RenderListDataAsStream)</span><span class="sxs-lookup"><span data-stu-id="a3da3-563">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="a3da3-564">Use a nova _propriedade ImageFieldsToTryRewriteToCdnUrls_ para fornecer uma lista separada de vírgulas de campos</span><span class="sxs-lookup"><span data-stu-id="a3da3-564">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="a3da3-565">Oferece suporte a campos de hiperlink e campos PublishingImage</span><span class="sxs-lookup"><span data-stu-id="a3da3-565">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="a3da3-566">Representações de imagem do SharePoint</span><span class="sxs-lookup"><span data-stu-id="a3da3-566">SharePoint image renditions</span></span>

<span data-ttu-id="a3da3-567">O diagrama a seguir ilustra o fluxo de trabalho quando o SharePoint recebe uma solicitação de uma página contendo ativos de origem pública.</span><span class="sxs-lookup"><span data-stu-id="a3da3-567">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="a3da3-568">![Diagrama de fluxo de trabalho: recuperando ativos cdn do Office 365 de origem pública](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Fluxo de trabalho: recuperando ativos cdn do Office 365 de origem pública")</span><span class="sxs-lookup"><span data-stu-id="a3da3-568">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="a3da3-569">Se você quiser desabilitar a reescrita automática para URLs específicas em uma página, pode fazer check-out da página e adicionar o parâmetro de cadeia de caracteres de **consulta? NoAutoReWrites=true** até o final de cada link que você deseja desabilitar.</span><span class="sxs-lookup"><span data-stu-id="a3da3-569">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="constructing-cdn-urls-for-public-assets"></a><span data-ttu-id="a3da3-570">Construir URLs de CDN para ativos públicos</span><span class="sxs-lookup"><span data-stu-id="a3da3-570">Constructing CDN URLs for public assets</span></span>

<span data-ttu-id="a3da3-571">Se o recurso _de_ Publicação não estiver habilitado para uma origem pública ou o ativo não for um dos tipos de link suportados pelo recurso de reescrita automática do serviço CDN, você poderá construir manualmente URLs para o local da CDN dos ativos e usar essas URLs em seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a3da3-571">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="a3da3-572">Você não pode codificar ou construir URLs de CDN para ativos em uma origem privada porque o token de acesso necessário que forma a última seção da URL é gerado no momento em que o recurso é solicitado.</span><span class="sxs-lookup"><span data-stu-id="a3da3-572">You cannot hardcode or construct CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span> <span data-ttu-id="a3da3-573">Você pode construir a URL para CDN pública e a URL não deve ser codificada com dificuldade, pois ela está sujeita a alterações.</span><span class="sxs-lookup"><span data-stu-id="a3da3-573">You can construct the URL for Public CDN and the URL should not be hard coded as it is subject to change.</span></span>

<span data-ttu-id="a3da3-574">Para ativos públicos de CDN, o formato URL terá a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="a3da3-574">For public CDN assets, the URL format will look like the following:</span></span>

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="a3da3-575">Substitua **TenantHostName** pelo nome do locatário.</span><span class="sxs-lookup"><span data-stu-id="a3da3-575">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="a3da3-576">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="a3da3-576">Example:</span></span>

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```
> [!NOTE]
> <span data-ttu-id="a3da3-577">A propriedade de contexto de página deve ser usada para construir o prefixo em vez de codificação " https://publiccdn.sharepointonline.com ".</span><span class="sxs-lookup"><span data-stu-id="a3da3-577">The page context property should be used to construct the prefix instead of hard coding "https://publiccdn.sharepointonline.com".</span></span> <span data-ttu-id="a3da3-578">A URL está sujeita a alterações e não deve ser codificada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-578">The URL is subject to change and should not be hard coded.</span></span> <span data-ttu-id="a3da3-579">Se você estiver usando modelos de exibição com o SharePoint Online clássico, poderá usar a propriedade "window._spPageContextInfo.publicCdnBaseUrl" em seu modelo de exibição para o prefixo da URL.</span><span class="sxs-lookup"><span data-stu-id="a3da3-579">If you are using display templates with Classic SharePoint Online then you can use the property "window._spPageContextInfo.publicCdnBaseUrl" in your display template for the prefix of the URL.</span></span> <span data-ttu-id="a3da3-580">Se você for Web Parts SPFx para o SharePoint moderno e clássico, poderá utilizar a propriedade "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span><span class="sxs-lookup"><span data-stu-id="a3da3-580">If you are SPFx web parts for modern and classic SharePoint the you can utilize the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span></span> <span data-ttu-id="a3da3-581">Isso fornecerá o prefixo para que, se for alterado, sua implementação será atualizada com ele.</span><span class="sxs-lookup"><span data-stu-id="a3da3-581">This will provide the prefix so that if it is changed then your implementation will update with it.</span></span> <span data-ttu-id="a3da3-582">Como exemplo para SPFx, a URL pode ser construída usando a propriedade "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL para o item".</span><span class="sxs-lookup"><span data-stu-id="a3da3-582">As an example for SPFx, the URL can be constructed using the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item".</span></span> <span data-ttu-id="a3da3-583">Confira [Usando a CDN no código do lado](https://youtu.be/IH1RbQlbhIA) do cliente que faz parte da série de desempenho da [1ª temporada](https://aka.ms/sppnp-perfvideos)</span><span class="sxs-lookup"><span data-stu-id="a3da3-583">Please see [Using CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) which is part of the [season 1 performance series](https://aka.ms/sppnp-perfvideos)</span></span>


### <a name="using-assets-in-private-origins"></a><span data-ttu-id="a3da3-584">Usando ativos em origens privadas</span><span class="sxs-lookup"><span data-stu-id="a3da3-584">Using assets in private origins</span></span>

<span data-ttu-id="a3da3-585">Nenhuma configuração adicional é necessária para usar ativos em origens privadas.</span><span class="sxs-lookup"><span data-stu-id="a3da3-585">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="a3da3-586">O SharePoint Online reescreve automaticamente URLs para ativos em origens privadas, portanto, as solicitações para esses ativos sempre serão atendidas da CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-586">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="a3da3-587">Você não pode criar manualmente URLs para ativos CDN em origens privadas porque essas URLs contêm tokens que devem ser gerados automaticamente pelo SharePoint Online no momento em que o ativo é solicitado.</span><span class="sxs-lookup"><span data-stu-id="a3da3-587">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="a3da3-588">O acesso a ativos em origens privadas é protegido por tokens gerados dinamicamente com base nas permissões do usuário para a origem, com as advertências descritas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="a3da3-588">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="a3da3-589">Os usuários devem ter pelo menos **acesso de** leitura às origens da CDN para renderizar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a3da3-589">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="a3da3-590">O diagrama a seguir ilustra o fluxo de trabalho quando o SharePoint recebe uma solicitação de uma página contendo ativos de origem privada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-590">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="a3da3-591">![Diagrama de fluxo de trabalho: recuperando ativos cdn do Office 365 de origem privada](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Fluxo de trabalho: recuperando ativos cdn do Office 365 de origem privada")</span><span class="sxs-lookup"><span data-stu-id="a3da3-591">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="a3da3-592">Autorização baseada em token em origens privadas</span><span class="sxs-lookup"><span data-stu-id="a3da3-592">Token-based authorization in private origins</span></span>

<span data-ttu-id="a3da3-593">O acesso a ativos em origens privadas na CDN do Office 365 é concedido por tokens gerados pelo SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a3da3-593">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="a3da3-594">Os usuários que já têm permissão para acessar a pasta ou biblioteca designada pela origem são automaticamente concedidos tokens que permitem que o usuário acesse o arquivo com base em seu nível de permissão.</span><span class="sxs-lookup"><span data-stu-id="a3da3-594">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="a3da3-595">Esses tokens de acesso são válidos de 30 a 90 minutos depois que são gerados para ajudar a evitar ataques de repetição de token.</span><span class="sxs-lookup"><span data-stu-id="a3da3-595">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="a3da3-596">Depois que o token de acesso é gerado, o SharePoint Online retorna um URI personalizado para o cliente que contém dois _parâmetros_ de autorização como (token de autorização de borda) e _aveia_ (token de autorização de origem).</span><span class="sxs-lookup"><span data-stu-id="a3da3-596">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="a3da3-597">A estrutura de cada token é< tempo de expiração no formato época de _>__<'secure signature'>_.</span><span class="sxs-lookup"><span data-stu-id="a3da3-597">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="a3da3-598">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a3da3-598">For example:</span></span>

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="a3da3-599">Qualquer pessoa que tenha o token pode acessar o recurso na CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-599">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="a3da3-600">No entanto, as URLs que contêm esses tokens de acesso são compartilhadas somente por HTTPS, portanto, a menos que a URL seja explicitamente compartilhada por um usuário final antes que o token expire, o ativo não estará acessível a usuários não autorizados.</span><span class="sxs-lookup"><span data-stu-id="a3da3-600">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="a3da3-601">Permissões de nível de item não são suportadas para ativos em origens privadas</span><span class="sxs-lookup"><span data-stu-id="a3da3-601">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="a3da3-602">É importante observar que o SharePoint Online não dá suporte a permissões de nível de item para ativos em origens privadas.</span><span class="sxs-lookup"><span data-stu-id="a3da3-602">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="a3da3-603">Por exemplo, para um arquivo localizado em , os usuários têm acesso efetivo ao `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` arquivo dadas as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="a3da3-603">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="a3da3-604">User</span><span class="sxs-lookup"><span data-stu-id="a3da3-604">User</span></span>  |<span data-ttu-id="a3da3-605">Permissões</span><span class="sxs-lookup"><span data-stu-id="a3da3-605">Permissions</span></span>  |<span data-ttu-id="a3da3-606">Acesso efetivo</span><span class="sxs-lookup"><span data-stu-id="a3da3-606">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a3da3-607">Usuário 1</span><span class="sxs-lookup"><span data-stu-id="a3da3-607">User 1</span></span>     |<span data-ttu-id="a3da3-608">Tem acesso à pasta1</span><span class="sxs-lookup"><span data-stu-id="a3da3-608">Has access to folder1</span></span>         |<span data-ttu-id="a3da3-609">Pode acessar image1.jpg da CDN</span><span class="sxs-lookup"><span data-stu-id="a3da3-609">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="a3da3-610">Usuário 2</span><span class="sxs-lookup"><span data-stu-id="a3da3-610">User 2</span></span>     |<span data-ttu-id="a3da3-611">Não tem acesso à pasta1</span><span class="sxs-lookup"><span data-stu-id="a3da3-611">Does not have access to folder1</span></span>         |<span data-ttu-id="a3da3-612">Não é possível acessar image1.jpg da CDN</span><span class="sxs-lookup"><span data-stu-id="a3da3-612">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="a3da3-613">Usuário 3</span><span class="sxs-lookup"><span data-stu-id="a3da3-613">User 3</span></span>     |<span data-ttu-id="a3da3-614">Não tem acesso à pasta1, mas tem permissão explícita para acessar image1.jpg no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-614">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="a3da3-615">Pode acessar o ativo image1.jpg diretamente do SharePoint Online, mas não da CDN</span><span class="sxs-lookup"><span data-stu-id="a3da3-615">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="a3da3-616">Usuário 4</span><span class="sxs-lookup"><span data-stu-id="a3da3-616">User 4</span></span>     |<span data-ttu-id="a3da3-617">Tem acesso à pasta1, mas foi explicitamente negado o acesso image1.jpg no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-617">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="a3da3-618">Não é possível acessar o ativo do SharePoint Online, mas pode acessar o ativo da CDN apesar de ter sido negado o acesso ao arquivo no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-618">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="a3da3-619"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-619"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="a3da3-620">Solução de problemas da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-620">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="a3da3-621"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="a3da3-621"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="a3da3-622">Como confirmar se os ativos estão sendo atendidos pela CDN?</span><span class="sxs-lookup"><span data-stu-id="a3da3-622">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="a3da3-623">Depois de adicionar links a ativos cdn a uma página, você pode confirmar se o ativo está sendo servido da CDN navegando até a página, clicando com o botão direito do mouse na imagem depois que ele renderizou e revisou a URL da imagem.</span><span class="sxs-lookup"><span data-stu-id="a3da3-623">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="a3da3-624">Você também pode usar as ferramentas de desenvolvedor do navegador para exibir a URL de cada ativo em uma página ou usar uma ferramenta de rastreamento de rede de terceiros.</span><span class="sxs-lookup"><span data-stu-id="a3da3-624">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="a3da3-625">Se você usar uma ferramenta de rede como o Fiddler para testar seus ativos fora da renderização do ativo de uma página do SharePoint, você deve adicionar manualmente o header do referer "Referer: " à solicitação GET onde a URL é a URL raiz do locatário do `https://yourdomain.sharepoint.com` SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a3da3-625">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="a3da3-626">Não é possível testar URLs de CDN diretamente em um navegador da Web porque você deve ter um referer vindo do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a3da3-626">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="a3da3-627">No entanto, se você adicionar a URL do ativo CDN a uma página do SharePoint e abrir a página em um navegador, você verá o ativo CDN renderizado na página.</span><span class="sxs-lookup"><span data-stu-id="a3da3-627">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="a3da3-628">Para obter mais informações sobre como usar as ferramentas de desenvolvedor no navegador do Microsoft Edge, consulte [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span><span class="sxs-lookup"><span data-stu-id="a3da3-628">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="a3da3-629">Para assistir a um vídeo curto hospedado no canal do [SharePoint Developer Patterns and Practices do YouTube](https://aka.ms/sppnp-videos) demonstrando como verificar se a CDN está funcionando, consulte Verifying your [CDN usage](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)and ensuring optimal network connectivity .</span><span class="sxs-lookup"><span data-stu-id="a3da3-629">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="a3da3-630">Por que os ativos de uma nova origem estão indisponíveis?</span><span class="sxs-lookup"><span data-stu-id="a3da3-630">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="a3da3-631">Os ativos em novas origens não estarão disponíveis imediatamente para uso, pois leva tempo para que o registro se propague pela CDN e para que os ativos sejam carregados da origem para o armazenamento da CDN.</span><span class="sxs-lookup"><span data-stu-id="a3da3-631">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="a3da3-632">O tempo necessário para que os ativos sejam disponibilizados na CDN depende de quantos ativos e tamanhos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="a3da3-632">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="a3da3-633">Minha web part do lado do cliente ou a solução da Estrutura do SharePoint não está funcionando</span><span class="sxs-lookup"><span data-stu-id="a3da3-633">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="a3da3-634">Quando você habilita a CDN do Office 365 para origens públicas, o serviço CDN cria automaticamente essas origens padrão:</span><span class="sxs-lookup"><span data-stu-id="a3da3-634">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="a3da3-635">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="a3da3-635">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="a3da3-636">BIBLIOTECA \*/STYLE</span><span class="sxs-lookup"><span data-stu-id="a3da3-636">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="a3da3-637">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="a3da3-637">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="a3da3-638">Se a origem \*/clientsideassets estiver ausente, as soluções da Estrutura do SharePoint falharão e nenhuma mensagem de aviso ou erro será gerada.</span><span class="sxs-lookup"><span data-stu-id="a3da3-638">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="a3da3-639">Essa origem pode estar ausente porque a CDN foi habilitada com o parâmetro _-NoDefaultOrigins_ definido como $true , ou porque **a** origem foi excluída manualmente.</span><span class="sxs-lookup"><span data-stu-id="a3da3-639">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="a3da3-640">Você pode verificar quais origens estão presentes com o seguinte comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a3da3-640">You can check to see which origins are present with the following PowerShell command:</span></span>

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="a3da3-641">Ou você pode verificar com a CLI do Office 365:</span><span class="sxs-lookup"><span data-stu-id="a3da3-641">Or you can check with the Office 365 CLI:</span></span>

``` powershell
spo cdn origin list
```

<span data-ttu-id="a3da3-642">Para adicionar a origem no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a3da3-642">To add the origin in PowerShell:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="a3da3-643">Para adicionar a origem na CLI do Office 365:</span><span class="sxs-lookup"><span data-stu-id="a3da3-643">To add the origin in the Office 365 CLI:</span></span>

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="a3da3-644">Quais módulos e shells de CLI do PowerShell preciso para trabalhar com a CDN do Office 365?</span><span class="sxs-lookup"><span data-stu-id="a3da3-644">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="a3da3-645">Você pode optar por trabalhar com a CDN do Office 365 usando o módulo do Shell de Gerenciamento do **SharePoint Online** do PowerShell ou a **CLI do Office 365.**</span><span class="sxs-lookup"><span data-stu-id="a3da3-645">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="a3da3-646">Introdução ao Shell de Gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a3da3-646">Getting started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="a3da3-647">Instalar a CLI do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-647">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="a3da3-648">Confira também</span><span class="sxs-lookup"><span data-stu-id="a3da3-648">See also</span></span>

[<span data-ttu-id="a3da3-649">Redes de Distribuição de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="a3da3-649">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="a3da3-650">Planejamento de rede e ajuste de desempenho para o Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-650">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="a3da3-651">Série de desempenho do SharePoint - Série de vídeo CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3da3-651">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)