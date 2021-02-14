---
title: Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online
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
description: Saiba como usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 para acelerar a entrega dos ativos do SharePoint Online.
ms.openlocfilehash: 0ef7922f4e8881065f97a5fdeb4f21242c2b6467
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686941"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="d545e-103">Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="d545e-104">Você pode usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 integrado para proporcionar melhor desempenho a suas páginas do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d545e-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="d545e-105">A CDN do Office 365 melhora o desempenho ao armazenar em cache ativos estáticos mais próximos aos navegadores que os solicitaram, o que ajuda a acelerar downloads e reduzir a latência.</span><span class="sxs-lookup"><span data-stu-id="d545e-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="d545e-106">Além disso, a CDN do Office 365 usa o [protocolo HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) para maior compactação e canalização HTTP.</span><span class="sxs-lookup"><span data-stu-id="d545e-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="d545e-107">O serviço de CDN do Office 365 faz parte da assinatura do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d545e-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="d545e-108">A CDN do Office 365 só está disponível para locatários na nuvem **de produção** (em todo o mundo).</span><span class="sxs-lookup"><span data-stu-id="d545e-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="d545e-109">Locatários nas nuvens do Governo dos EUA, China e Alemanha não têm suporte atualmente para a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d545e-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="d545e-110">A CDN do Office 365 é composta por várias CDNs que permitem que você hospede ativos estáticos em vários locais ou _origens_ e sirva-os de redes globais de alta velocidade.</span><span class="sxs-lookup"><span data-stu-id="d545e-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="d545e-111">Dependendo do tipo de conteúdo você quiser hospedar na CDN do Office 365, você pode adicionar origens **públicas**, origens **privadas** ou ambas.</span><span class="sxs-lookup"><span data-stu-id="d545e-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="d545e-112">Consulte [Escolher se cada origem deve ser pública](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) ou privada para obter mais informações sobre a diferença entre origens públicas e privadas.</span><span class="sxs-lookup"><span data-stu-id="d545e-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="d545e-113">![Diagrama conceitual da CDN do Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Diagrama conceitual da CDN do Office 365")</span><span class="sxs-lookup"><span data-stu-id="d545e-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="d545e-114">Se você já estiver familiarizado com a maneira como as CDNs funcionam, só precisa concluir algumas etapas para habilitar a CDN do Office 365 para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="d545e-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="d545e-115">Este tópico descreve como.</span><span class="sxs-lookup"><span data-stu-id="d545e-115">This topic describes how.</span></span> <span data-ttu-id="d545e-116">Continue lendo para obter informações sobre como começar a hospedar seus ativos estáticos.</span><span class="sxs-lookup"><span data-stu-id="d545e-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="d545e-117">Há outras CDNs hospedadas pela Microsoft que podem ser usadas com o Office 365 para cenários de uso especializado, mas não são discutidas neste tópico porque elas estão fora do escopo da CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d545e-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="d545e-118">Para obter mais informações, consulte [Outras CDNs da Microsoft.](content-delivery-networks.md#other-microsoft-cdns)</span><span class="sxs-lookup"><span data-stu-id="d545e-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="d545e-119">**Volte para o [planejamento de rede e ajuste de desempenho do Office 365.](https://aka.ms/tune)**</span><span class="sxs-lookup"><span data-stu-id="d545e-119">**Head back to [Network planning and performance tuning for Office 365](https://aka.ms/tune).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="d545e-120">Visão geral de como trabalhar com a CDN do Office 365 no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="d545e-121">Para configurar a CDN do Office 365 para sua organização, siga estas etapas básicas:</span><span class="sxs-lookup"><span data-stu-id="d545e-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="d545e-122">Planejar a implantação da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="d545e-123">[Determine quais ativos estáticos você deseja hospedar na CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)</span><span class="sxs-lookup"><span data-stu-id="d545e-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="d545e-124">[Determine onde você deseja armazenar seus ativos.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)</span><span class="sxs-lookup"><span data-stu-id="d545e-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="d545e-125">Esse local pode ser um site, biblioteca ou pasta do SharePoint e é chamado de _origem._</span><span class="sxs-lookup"><span data-stu-id="d545e-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="d545e-126">[Escolha se cada origem deve ser pública ou privada.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="d545e-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="d545e-127">Você pode adicionar várias origens de tipos públicos e privados.</span><span class="sxs-lookup"><span data-stu-id="d545e-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="d545e-128">Configurar e configurar a CDN usando o PowerShell ou a CLI do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="d545e-129">Configurar e configurar a CDN usando o Shell de Gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="d545e-130">Configurar e configurar a CDN usando PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="d545e-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="d545e-131">Configurar e configurar a CDN usando a CLI do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="d545e-132">Ao concluir esta etapa, você terá:</span><span class="sxs-lookup"><span data-stu-id="d545e-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="d545e-133">Habilitada a CDN para sua organização.</span><span class="sxs-lookup"><span data-stu-id="d545e-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="d545e-134">Suas origens foram adicionadas, identificando cada origem como pública ou privada.</span><span class="sxs-lookup"><span data-stu-id="d545e-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="d545e-135">Quando terminar a instalação, você poderá gerenciar a CDN do [Office 365](use-microsoft-365-cdn-with-spo.md#CDNManage) ao longo do tempo:</span><span class="sxs-lookup"><span data-stu-id="d545e-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="d545e-136">Adicionar, atualizar e remover ativos</span><span class="sxs-lookup"><span data-stu-id="d545e-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="d545e-137">Adicionando e removendo origens</span><span class="sxs-lookup"><span data-stu-id="d545e-137">Adding and removing origins</span></span>
+ <span data-ttu-id="d545e-138">Configurando políticas da CDN</span><span class="sxs-lookup"><span data-stu-id="d545e-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="d545e-139">Se necessário, desabilitar a CDN</span><span class="sxs-lookup"><span data-stu-id="d545e-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="d545e-140">Por fim, [consulte Usando seus ativos da CDN](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) para saber mais sobre como acessar seus ativos de CDN de origens públicas e privadas.</span><span class="sxs-lookup"><span data-stu-id="d545e-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="d545e-141">Confira [a solução de problemas da CDN do Office 365](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) para obter orientação sobre como resolver problemas comuns.</span><span class="sxs-lookup"><span data-stu-id="d545e-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="d545e-142">Planejar a implantação da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="d545e-143">Antes de implantar a CDN do Office 365 para seu locatário do Office 365, você deve considerar os seguintes fatores como parte do seu processo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="d545e-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="d545e-144">Determinar quais ativos estáticos você deseja hospedar na CDN</span><span class="sxs-lookup"><span data-stu-id="d545e-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="d545e-145">Determinar onde você deseja armazenar seus ativos</span><span class="sxs-lookup"><span data-stu-id="d545e-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="d545e-146">Escolha se cada origem deve ser pública ou privada</span><span class="sxs-lookup"><span data-stu-id="d545e-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="d545e-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="d545e-148">Determinar quais ativos estáticos você deseja hospedar na CDN</span><span class="sxs-lookup"><span data-stu-id="d545e-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="d545e-149">Em geral, as CDNs são mais eficazes para hospedar _ativos_ estáticos ou ativos que não mudam com frequência.</span><span class="sxs-lookup"><span data-stu-id="d545e-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="d545e-150">Uma boa regra geral é identificar arquivos que atendem a algumas ou todas essas condições:</span><span class="sxs-lookup"><span data-stu-id="d545e-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="d545e-151">Arquivos estáticos incorporados em uma página (como scripts e imagens) que podem ter um impacto incremental significativo nos tempos de carregamento da página</span><span class="sxs-lookup"><span data-stu-id="d545e-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="d545e-152">Arquivos grandes, como executáveis e arquivos de instalação</span><span class="sxs-lookup"><span data-stu-id="d545e-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="d545e-153">Bibliotecas de recursos que suportam código do lado do cliente</span><span class="sxs-lookup"><span data-stu-id="d545e-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="d545e-154">Por exemplo, arquivos pequenos solicitados repetidamente, como imagens e scripts de site, podem melhorar significativamente o desempenho de renderização do site e reduzir incrementalmente a carga nos sites do SharePoint Online quando você os adiciona a uma origem de CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="d545e-155">Arquivos maiores, como executáveis de instalação, podem ser baixados da CDN, proporcionando um impacto positivo no desempenho e redução subsequente da carga em seu site do SharePoint Online, mesmo que eles não sejam acessados com a mesma frequência.</span><span class="sxs-lookup"><span data-stu-id="d545e-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="d545e-156">A melhoria de desempenho por arquivo depende de muitos fatores, incluindo a proximidade do cliente com o ponto de extremidade da CDN mais próximo, condições transitórias na rede local e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="d545e-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="d545e-157">Muitos arquivos estáticos são muito pequenos e podem ser baixados do Office 365 em menos de um segundo.</span><span class="sxs-lookup"><span data-stu-id="d545e-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="d545e-158">No entanto, uma página da Web pode conter muitos arquivos incorporados com um tempo de download cumulativo de vários segundos.</span><span class="sxs-lookup"><span data-stu-id="d545e-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="d545e-159">Atender a esses arquivos da CDN pode reduzir significativamente o tempo de carregamento geral da página.</span><span class="sxs-lookup"><span data-stu-id="d545e-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="d545e-160">Veja [quais ganhos de desempenho uma CDN fornece?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) para um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d545e-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="d545e-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="d545e-162">Determinar onde você deseja armazenar seus ativos</span><span class="sxs-lookup"><span data-stu-id="d545e-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="d545e-163">A CDN busca seus ativos de um local chamado _origem._</span><span class="sxs-lookup"><span data-stu-id="d545e-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="d545e-164">Uma origem pode ser um site do SharePoint, uma biblioteca de documentos ou uma pasta acessível por uma URL.</span><span class="sxs-lookup"><span data-stu-id="d545e-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="d545e-165">Você tem grande flexibilidade ao especificar origens para sua organização.</span><span class="sxs-lookup"><span data-stu-id="d545e-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="d545e-166">Por exemplo, você pode especificar várias origens ou uma única origem onde deseja colocar todos os ativos da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="d545e-167">Você pode optar por ter origens públicas ou privadas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="d545e-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="d545e-168">A maioria das organizações optará por implementar uma combinação dos dois.</span><span class="sxs-lookup"><span data-stu-id="d545e-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="d545e-169">Você pode criar um novo contêiner para suas origens, como pastas ou bibliotecas de documentos, e adicionar arquivos que deseja disponibilizar na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="d545e-170">Essa é uma boa abordagem se você tiver um conjunto específico de ativos que deseja disponibilizar na CDN e deseja restringir o conjunto de ativos da CDN apenas aos arquivos no contêiner.</span><span class="sxs-lookup"><span data-stu-id="d545e-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="d545e-171">Você também pode configurar um conjunto de sites, um site, uma biblioteca ou uma pasta existente como origem, o que disponibiliza todos os ativos qualificados no contêiner na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="d545e-172">Antes de adicionar um contêiner existente como origem, é importante garantir que você esteja ciente de seu conteúdo e permissões para não expor inadvertidamente os ativos a acesso anônimo ou usuários não autorizados.</span><span class="sxs-lookup"><span data-stu-id="d545e-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="d545e-173">Você pode definir _políticas de CDN_ para excluir o conteúdo de suas origens da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="d545e-174">As políticas de CDN excluem ativos  em origens públicas ou privadas por atributos como tipo de arquivo e classificação de _site_ e são aplicadas a todas as origens do CdnType (particular ou público) que você especificar na política.</span><span class="sxs-lookup"><span data-stu-id="d545e-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="d545e-175">Por exemplo, se você adicionar uma origem privada consistindo em um site que contenha  vários subsites, poderá definir uma política para excluir sites marcados como Confidenciais para que o conteúdo de sites com essa classificação aplicada não seja servido da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="d545e-176">A política será aplicada ao conteúdo de _todas as_ origens privadas que você adicionou à CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="d545e-177">Tenha em mente que quanto maior o número de origens, maior o impacto sobre o tempo que o serviço da CDN leva para processar solicitações.</span><span class="sxs-lookup"><span data-stu-id="d545e-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="d545e-178">Recomendamos que você limite o número de origens o máximo possível.</span><span class="sxs-lookup"><span data-stu-id="d545e-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="d545e-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="d545e-180">Escolha se cada origem deve ser pública ou privada</span><span class="sxs-lookup"><span data-stu-id="d545e-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="d545e-181">Ao identificar uma origem, especifique se ela deve ser _pública_ ou _privada._</span><span class="sxs-lookup"><span data-stu-id="d545e-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="d545e-182">O acesso a ativos de CDN em origens públicas é anônimo, e o conteúdo da CDN em origens privadas é protegido por tokens gerados dinamicamente para maior segurança.</span><span class="sxs-lookup"><span data-stu-id="d545e-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="d545e-183">Independentemente da opção escolhida, a Microsoft faz todo o trabalho pesado para você quando se trata de administração da CDN em si.</span><span class="sxs-lookup"><span data-stu-id="d545e-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="d545e-184">Além disso, você pode mudar de ideia mais tarde, depois de configurar a CDN e identificar suas origens.</span><span class="sxs-lookup"><span data-stu-id="d545e-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="d545e-185">As opções públicas e privadas oferecem ganhos de desempenho semelhantes, mas cada uma tem vantagens e atributos exclusivos.</span><span class="sxs-lookup"><span data-stu-id="d545e-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="d545e-186">**Origens** públicas na CDN do Office 365 são acessíveis anonimamente e os ativos hospedados podem ser acessados por qualquer pessoa que tenha a URL do ativo.</span><span class="sxs-lookup"><span data-stu-id="d545e-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="d545e-187">Como o acesso ao conteúdo de origens públicas é anônimo, você só deve usá-lo para o armazenamento em cache de conteúdo genérico e não sensível como arquivos javascript, scripts, ícones e imagens.</span><span class="sxs-lookup"><span data-stu-id="d545e-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as javascript files, scripts, icons and images.</span></span>

<span data-ttu-id="d545e-188">**Origens** privadas na CDN do Office 365 fornecem acesso privado ao conteúdo do usuário, como bibliotecas de documentos do SharePoint Online, sites e imagens proprietárias.</span><span class="sxs-lookup"><span data-stu-id="d545e-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="d545e-189">O acesso ao conteúdo em origens privadas é protegido por tokens gerados dinamicamente para que ele só possa ser acessado por usuários com permissões para a biblioteca de documentos original ou o local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="d545e-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="d545e-190">Origens privadas na CDN do Office 365 só podem ser usadas para conteúdo do SharePoint Online, e você só pode acessar ativos em origens privadas por meio do redirecionamento de seu locatário do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d545e-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="d545e-191">Você pode ler mais sobre como o acesso à CDN a ativos em uma origem privada funciona em Usar [ativos em origens privadas.](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)</span><span class="sxs-lookup"><span data-stu-id="d545e-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="d545e-192">Atributos e vantagens da hospedagem de ativos em origens públicas</span><span class="sxs-lookup"><span data-stu-id="d545e-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="d545e-193">Os ativos exibidos em uma origem pública são acessíveis por todos os usuários anonimamente.</span><span class="sxs-lookup"><span data-stu-id="d545e-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="d545e-194">Você nunca deve colocar recursos que contenham informações do usuário ou sejam considerados confidenciais para sua organização em uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="d545e-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>
+ <span data-ttu-id="d545e-195">Se você remover um ativo de uma origem pública, ele pode seguir disponível em cache por até 30 dias; contudo, invalidaremos os links para o ativo na CDN em 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="d545e-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>
+ <span data-ttu-id="d545e-196">Quando você hospeda folhas de estilo (arquivos CSS) em uma origem pública, você pode usar os caminhos relativos e URIs dentro do código.</span><span class="sxs-lookup"><span data-stu-id="d545e-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="d545e-197">Isso significa que você pode referenciar o local das imagens de fundo e outros objetos em relação ao local do ativo que faz a chamada.</span><span class="sxs-lookup"><span data-stu-id="d545e-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>
+ <span data-ttu-id="d545e-198">Por mais que você possa codificar uma URL de origem pública, isto não é recomendável.</span><span class="sxs-lookup"><span data-stu-id="d545e-198">While you can hard code a public origin's URL, doing so is not recommended.</span></span> <span data-ttu-id="d545e-199">O motivo é que se o acesso à CDN ficar indisponível, a URL não resolverá automaticamente para a sua organização no SharePoint Online e pode resultar em links quebrados e outros erros.</span><span class="sxs-lookup"><span data-stu-id="d545e-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span>
+ <span data-ttu-id="d545e-200">Os tipos de arquivo padrão incluídos para origens públicas são .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff e .woff2.</span><span class="sxs-lookup"><span data-stu-id="d545e-200">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="d545e-201">Você pode especificar tipos de arquivo adicionais.</span><span class="sxs-lookup"><span data-stu-id="d545e-201">You can specify additional file types.</span></span>
+ <span data-ttu-id="d545e-202">Você pode configurar uma política para excluir ativos que foram identificados por classificações de site que você especificar.</span><span class="sxs-lookup"><span data-stu-id="d545e-202">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="d545e-203">Por exemplo, você pode optar por excluir todos os ativos marcados como "restrito" ou "confidencial", mesmo que sejam um tipo de arquivo permitido e estejam localizados em uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="d545e-203">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="d545e-204">Atributos e vantagens da hospedagem de ativos em origens privadas</span><span class="sxs-lookup"><span data-stu-id="d545e-204">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="d545e-205">Origens privadas só podem ser usadas para ativos do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d545e-205">Private origins can only be used for SharePoint Online assets.</span></span>
+ <span data-ttu-id="d545e-206">Os usuários só poderão acessar os ativos de uma origem privada se eles têm permissões para acessar o contêiner.</span><span class="sxs-lookup"><span data-stu-id="d545e-206">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="d545e-207">O acesso anônimo a esses ativos é vetado.</span><span class="sxs-lookup"><span data-stu-id="d545e-207">Anonymous access to these assets is prevented.</span></span>
+ <span data-ttu-id="d545e-208">Os ativos em origens privadas devem ser referidos do locatário do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d545e-208">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="d545e-209">O acesso direto aos ativos da CDN privada não funciona.</span><span class="sxs-lookup"><span data-stu-id="d545e-209">Direct access to private CDN assets does not work.</span></span>
+ <span data-ttu-id="d545e-210">Se você remover um ativo da origem privada, ele poderá continuar disponível por até uma hora do cache; No entanto, invalidaremos os links para o ativo na CDN dentro de 15 minutos após a remoção do ativo.</span><span class="sxs-lookup"><span data-stu-id="d545e-210">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>
+ <span data-ttu-id="d545e-211">Os tipos de arquivo padrão incluídos para origens privadas são .gif, .ico, .jpeg, .jpg, .js e .png.</span><span class="sxs-lookup"><span data-stu-id="d545e-211">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="d545e-212">Você pode especificar tipos de arquivo adicionais.</span><span class="sxs-lookup"><span data-stu-id="d545e-212">You can specify additional file types.</span></span>
+ <span data-ttu-id="d545e-213">Assim como nas origens públicas, você pode configurar uma política para excluir ativos identificados por classificações de site que você especificar, mesmo que use curingas para incluir todos os ativos em uma pasta ou biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="d545e-213">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="d545e-214">Para saber mais sobre por que usar a CDN do Office 365, os conceitos gerais de CDN e outras CDNs da Microsoft que você pode usar com seu locatário do Office 365, confira Redes de Distribuição de [Conteúdo.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="d545e-214">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="d545e-215">Origens de CDN padrão</span><span class="sxs-lookup"><span data-stu-id="d545e-215">Default CDN origins</span></span>

<span data-ttu-id="d545e-216">A menos que você especifique o contrário, o Office 365 configura algumas origens padrão quando você habilita a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d545e-216">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="d545e-217">Se você optar inicialmente por não provisioná-las, poderá adicionar essas origens após concluir a configuração.</span><span class="sxs-lookup"><span data-stu-id="d545e-217">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="d545e-218">A menos que você entenda as consequências de ignorar a configuração de origens padrão e tiver um motivo específico para fazer isso, você deve permitir que elas sejam criadas quando você habilitar a CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-218">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="d545e-219">Origens padrão da CDN privada:</span><span class="sxs-lookup"><span data-stu-id="d545e-219">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="d545e-220">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="d545e-220">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="d545e-221">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="d545e-221">\*/siteassets</span></span>

<span data-ttu-id="d545e-222">Origens de CDN pública padrão:</span><span class="sxs-lookup"><span data-stu-id="d545e-222">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="d545e-223">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="d545e-223">\*/masterpage</span></span>
+ <span data-ttu-id="d545e-224">\*/style library</span><span class="sxs-lookup"><span data-stu-id="d545e-224">\*/style library</span></span>
+ <span data-ttu-id="d545e-225">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="d545e-225">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="d545e-226">_clientsideassets_ é uma origem pública padrão que foi adicionada ao serviço CDN do Office 365 em dezembro de 2017.</span><span class="sxs-lookup"><span data-stu-id="d545e-226">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="d545e-227">Essa origem deve estar presente para que as soluções da Estrutura do SharePoint na CDN funcionem.</span><span class="sxs-lookup"><span data-stu-id="d545e-227">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="d545e-228">Se você habilitar a CDN do Office 365 antes de dezembro de 2017 ou se tiver ignorado a configuração de origens padrão ao habilitar a CDN, poderá adicionar manualmente essa origem.</span><span class="sxs-lookup"><span data-stu-id="d545e-228">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="d545e-229">Para saber mais, confira Minha Web Part do lado do [cliente ou a solução da Estrutura do SharePoint não está funcionando.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)</span><span class="sxs-lookup"><span data-stu-id="d545e-229">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="d545e-230"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-230"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="d545e-231">Configurar e configurar a CDN do Office 365 usando o Shell de Gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-231">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="d545e-232">Os procedimentos nesta seção exigem que você use o Shell de Gerenciamento do SharePoint Online para se conectar ao SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d545e-232">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="d545e-233">Para obter instruções, [confira Conectar-se ao PowerShell do SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="d545e-233">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="d545e-234">Conclua estas etapas para configurar a CDN para hospedar seus ativos no SharePoint Online usando o Shell de Gerenciamento do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d545e-234">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="d545e-235">Clique para expandir</span><span class="sxs-lookup"><span data-stu-id="d545e-235">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="d545e-236">Permitir que sua organização use a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-236">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="d545e-237">Antes de fazer alterações nas configurações da CDN do locatário, você deve recuperar o status atual da configuração da CDN privada em seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d545e-237">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="d545e-238">Conecte-se ao seu locatário usando o Shell de Gerenciamento do SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="d545e-238">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="d545e-239">Agora, use o cmdlet **Get-SPOTenantCdnEnabled** para recuperar as configurações de status da CDN do locatário:</span><span class="sxs-lookup"><span data-stu-id="d545e-239">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="d545e-240">O status da CDN do CdnType especificado será exibido na tela.</span><span class="sxs-lookup"><span data-stu-id="d545e-240">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="d545e-241">Use o cmdlet **Set-SPOTenantCdnEnabled** para permitir que sua organização use a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d545e-241">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="d545e-242">Você pode permitir que sua organização use origens públicas, origens privadas ou ambas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="d545e-242">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="d545e-243">Você também pode configurar a CDN para ignorar a configuração de origens padrão ao habilita-la.</span><span class="sxs-lookup"><span data-stu-id="d545e-243">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="d545e-244">Você sempre pode adicionar essas origens posteriormente, conforme descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="d545e-244">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="d545e-245">No Windows Powershell para SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="d545e-245">In Windows Powershell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="d545e-246">Por exemplo, para permitir que sua organização use origens públicas e privadas, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-246">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="d545e-247">Para permitir que sua organização use origens públicas e privadas, mas ignore a configuração das origens padrão, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-247">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="d545e-248">Confira as origens de [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) padrão para obter informações sobre as origens provisionadas por padrão quando você habilita a CDN do Office 365 e o impacto potencial de ignorar a configuração de origens padrão.</span><span class="sxs-lookup"><span data-stu-id="d545e-248">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="d545e-249">Para permitir que sua organização use origens públicas, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-249">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="d545e-250">Para permitir que sua organização use origens privadas, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-250">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="d545e-251">Para obter mais informações sobre esse cmdlet, consulte [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span><span class="sxs-lookup"><span data-stu-id="d545e-251">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span></span>

<span data-ttu-id="d545e-252"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-252"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="d545e-253">Alterar a lista de tipos de arquivo para incluir na CDN do Office 365 (opcional)</span><span class="sxs-lookup"><span data-stu-id="d545e-253">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="d545e-254">Ao definir tipos de arquivo usando o cmdlet **Set-SPOTenantCdnPolicy,** você substitui a lista definida no momento.</span><span class="sxs-lookup"><span data-stu-id="d545e-254">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="d545e-255">Se você quiser adicionar outros tipos de arquivo à lista, use o cmdlet primeiro para descobrir quais tipos de arquivo já são permitidos e incluí-los na lista juntamente com os novos.</span><span class="sxs-lookup"><span data-stu-id="d545e-255">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="d545e-256">Use o cmdlet **Set-SPOTenantCdnPolicy** para definir tipos de arquivo estáticos que podem ser hospedados por origens públicas e privadas na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-256">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="d545e-257">Por padrão, tipos de ativos comuns são permitidos, por exemplo.css, .gif, .jpg e .js.</span><span class="sxs-lookup"><span data-stu-id="d545e-257">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="d545e-258">No Windows PowerShell para SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="d545e-258">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="d545e-259">Por exemplo, para habilitar a CDN para hospedar arquivos .css e .png, digite o comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-259">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="d545e-260">Para ver quais tipos de arquivo atualmente são permitidos pela CDN, use o cmdlet **Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="d545e-260">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="d545e-261">Para obter mais informações sobre esses cmdlets, consulte [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) e [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span><span class="sxs-lookup"><span data-stu-id="d545e-261">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span></span>

<span data-ttu-id="d545e-262"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-262"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="d545e-263">Alterar a lista de classificações de site que você deseja excluir da CDN do Office 365 (opcional)</span><span class="sxs-lookup"><span data-stu-id="d545e-263">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="d545e-264">Ao excluir classificações de site usando o cmdlet **Set-SPOTenantCdnPolicy,** você substitui a lista definida no momento.</span><span class="sxs-lookup"><span data-stu-id="d545e-264">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="d545e-265">Se você quiser excluir classificações de site adicionais, use o cmdlet primeiro para descobrir quais classificações já foram excluídas e, em seguida, adicione-as com as novas.</span><span class="sxs-lookup"><span data-stu-id="d545e-265">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="d545e-266">Use o cmdlet **Set-SPOTenantCdnPolicy** para excluir as classificações de site que não deseja disponibilizar na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-266">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="d545e-267">Por padrão, nenhuma classificação de sites é excluída.</span><span class="sxs-lookup"><span data-stu-id="d545e-267">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="d545e-268">No Windows PowerShell para SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="d545e-268">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="d545e-269">Para ver quais classificações de site estão restritas no momento, use o cmdlet **Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="d545e-269">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="d545e-270">As propriedades que serão retornadas _são IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ e _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="d545e-270">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="d545e-271">A _propriedade IncludeFileExtensions_ contém a lista de extensões de arquivo que serão fornecidas pela CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-271">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="d545e-272">As extensões de arquivo padrão são diferentes entre públicas e privadas.</span><span class="sxs-lookup"><span data-stu-id="d545e-272">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="d545e-273">A _propriedade ExcludeRestrictedSiteClassifications_ contém as classificações de site que você deseja excluir da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-273">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="d545e-274">Por exemplo, você pode  excluir sites marcados como Confidenciais para que o conteúdo de sites com essa classificação aplicada não seja servido da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-274">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="d545e-275">A _propriedade ExcludeIfNoScriptDisabled_ exclui o conteúdo da CDN com base nas configurações do atributo _NoScript_ no nível do site.</span><span class="sxs-lookup"><span data-stu-id="d545e-275">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="d545e-276">Por padrão, o atributo _NoScript_ é definido como **Habilitado para** _sites_ modernos e **Desabilitado** para sites _clássicos._</span><span class="sxs-lookup"><span data-stu-id="d545e-276">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="d545e-277">Isso depende das configurações do locatário.</span><span class="sxs-lookup"><span data-stu-id="d545e-277">This depends on your tenant settings.</span></span>

<span data-ttu-id="d545e-278">Para obter mais informações sobre esses cmdlets, consulte [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) e [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span><span class="sxs-lookup"><span data-stu-id="d545e-278">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span></span>

<span data-ttu-id="d545e-279"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-279"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="d545e-280">Adicionar uma origem para seus ativos</span><span class="sxs-lookup"><span data-stu-id="d545e-280">Add an origin for your assets</span></span>

<span data-ttu-id="d545e-281">Use o cmdlet **Add-SPOTenantCdnOrigin** para definir uma origem.</span><span class="sxs-lookup"><span data-stu-id="d545e-281">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="d545e-282">Você pode definir várias origens.</span><span class="sxs-lookup"><span data-stu-id="d545e-282">You can define multiple origins.</span></span> <span data-ttu-id="d545e-283">A origem é uma URL que aponta para uma biblioteca ou pasta do SharePoint contendo os ativos que você deseja hospedar na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-283">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d545e-284">Você nunca deve colocar recursos que contenham informações do usuário ou sejam considerados confidenciais para sua organização em uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="d545e-284">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="d545e-285">O valor do _caminho é_ o caminho relativo para a biblioteca ou pasta que contém os ativos.</span><span class="sxs-lookup"><span data-stu-id="d545e-285">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="d545e-286">Você pode usar caracteres curinga, além de caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="d545e-286">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="d545e-287">As origens suportam caracteres curinga anexados à URL.</span><span class="sxs-lookup"><span data-stu-id="d545e-287">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="d545e-288">Isso permite que você crie origens que abrangem vários sites.</span><span class="sxs-lookup"><span data-stu-id="d545e-288">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="d545e-289">Por exemplo, para incluir todos os ativos na pasta páginas mestras de todos os seus sites como uma origem pública dentro da CDN, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-289">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="d545e-290">O modificador curinga \* só pode ser usado no início do caminho e corresponderá a todos os segmentos de **/** URL sob a URL especificada.</span><span class="sxs-lookup"><span data-stu-id="d545e-290">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="d545e-291">O caminho pode apontar para uma biblioteca de documentos, pasta ou site.</span><span class="sxs-lookup"><span data-stu-id="d545e-291">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="d545e-292">Por exemplo, o caminho _\*/site1_ corresponderá a todas as bibliotecas de documentos no site.</span><span class="sxs-lookup"><span data-stu-id="d545e-292">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="d545e-293">Você pode adicionar uma origem com um caminho relativo específico.</span><span class="sxs-lookup"><span data-stu-id="d545e-293">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="d545e-294">Você não pode adicionar uma origem usando o caminho completo.</span><span class="sxs-lookup"><span data-stu-id="d545e-294">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="d545e-295">Este exemplo adiciona uma origem privada da biblioteca siteassets a um site específico:</span><span class="sxs-lookup"><span data-stu-id="d545e-295">This example adds a private origin of the siteassets library on a specific site:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="d545e-296">Este exemplo adiciona uma origem privada _da pasta folder1_ à biblioteca de ativos do site do conjunto de sites:</span><span class="sxs-lookup"><span data-stu-id="d545e-296">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="d545e-297">Se houver um espaço no caminho, você pode cercar o caminho entre aspas duplas ou substituir o espaço pela CODIFICAção de URL %20.</span><span class="sxs-lookup"><span data-stu-id="d545e-297">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="d545e-298">Os exemplos a seguir adicionam uma origem privada da pasta _1_ na biblioteca de ativos do site do conjunto de sites:</span><span class="sxs-lookup"><span data-stu-id="d545e-298">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="d545e-299">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="d545e-299">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="d545e-300">Em origens privadas, os ativos compartilhados de uma origem devem ter uma versão principal publicada antes que possam ser acessados a partir da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-300">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="d545e-301">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="d545e-301">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="d545e-302">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="d545e-302">This can take up to 15 minutes.</span></span>

<span data-ttu-id="d545e-303"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-303"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="d545e-304">Exemplo: configurar uma origem pública para suas páginas mestras e para sua biblioteca de estilos para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-304">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="d545e-305">Normalmente, essas origens são configuradas para você por padrão quando você habilita a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d545e-305">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="d545e-306">No entanto, se você quiser habilita-los manualmente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d545e-306">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="d545e-307">Use o cmdlet **Add-SPOTenantCdnOrigin** para definir a biblioteca de estilos como uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="d545e-307">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="d545e-308">Use o cmdlet **Add-SPOTenantCdnOrigin** para definir as páginas mestras como uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="d545e-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="d545e-309">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="d545e-309">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

<span data-ttu-id="d545e-310">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="d545e-310">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="d545e-311">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="d545e-311">This can take up to 15 minutes.</span></span>

<span data-ttu-id="d545e-312"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-312"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="d545e-313">Exemplo: Configurar uma origem privada para os ativos do site, páginas do site e imagens de publicação do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-313">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="d545e-314">Use o cmdlet **Add-SPOTenantCdnOrigin** para definir a pasta de ativos do site como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="d545e-314">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="d545e-315">Use o cmdlet **Add-SPOTenantCdnOrigin** para definir a pasta de páginas do site como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="d545e-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="d545e-316">Use o cmdlet **Add-SPOTenantCdnOrigin** para definir a pasta de imagens de publicação como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="d545e-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="d545e-317">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="d545e-317">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

<span data-ttu-id="d545e-318">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="d545e-318">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="d545e-319">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="d545e-319">This can take up to 15 minutes.</span></span>

<span data-ttu-id="d545e-320"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-320"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="d545e-321">Exemplo: Configurar uma origem privada para um conjunto de sites para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-321">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="d545e-322">Use o cmdlet **Add-SPOTenantCdnOrigin** para definir um conjunto de sites como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="d545e-322">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="d545e-323">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d545e-323">For example:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="d545e-324">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span><span class="sxs-lookup"><span data-stu-id="d545e-324">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>
  
<span data-ttu-id="d545e-325">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="d545e-325">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="d545e-326">Você pode ver uma mensagem _pendente de_ Configuração que é esperada à medida que o locatário do SharePoint Online se conecta ao serviço da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-326">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="d545e-327">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="d545e-327">This can take up to 15 minutes.</span></span>

<span data-ttu-id="d545e-328"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-328"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="d545e-329">Gerenciar a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-329">Manage the Office 365 CDN</span></span>

<span data-ttu-id="d545e-330">Depois de configurar a CDN, você pode fazer alterações em sua configuração à medida que atualiza o conteúdo ou conforme suas necessidades mudam, conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="d545e-330">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="d545e-331"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-331"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="d545e-332">Adicionar, atualizar ou remover ativos da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-332">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="d545e-333">Depois de concluir as etapas de configuração, você pode adicionar novos ativos e atualizar ou remover ativos existentes sempre que quiser.</span><span class="sxs-lookup"><span data-stu-id="d545e-333">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="d545e-334">Basta fazer suas alterações nos ativos na pasta ou na biblioteca do SharePoint que você identificou como origem.</span><span class="sxs-lookup"><span data-stu-id="d545e-334">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="d545e-335">Se você adicionar um novo ativo, ele estará disponível imediatamente por meio da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-335">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="d545e-336">No entanto, se você atualizar o ativo, levará até 15 minutos para que a nova cópia se propague e se torne disponível na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-336">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="d545e-337">Se você precisar recuperar o local da origem, poderá usar o cmdlet **Get-SPOTenantCdnOrigins.**</span><span class="sxs-lookup"><span data-stu-id="d545e-337">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="d545e-338">Para obter informações sobre como usar esse cmdlet, consulte [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx).</span><span class="sxs-lookup"><span data-stu-id="d545e-338">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx).</span></span>

<span data-ttu-id="d545e-339"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-339"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="d545e-340">Remover uma origem da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-340">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="d545e-341">Você pode remover o acesso a uma pasta ou biblioteca do SharePoint que você identificou como uma origem.</span><span class="sxs-lookup"><span data-stu-id="d545e-341">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="d545e-342">Para fazer isso, use o cmdlet **Remove-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="d545e-342">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="d545e-343">Para obter informações sobre como usar esse cmdlet, consulte [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).</span><span class="sxs-lookup"><span data-stu-id="d545e-343">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).</span></span>

<span data-ttu-id="d545e-344"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-344"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="d545e-345">Modificar uma origem na CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-345">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="d545e-346">Não é possível modificar uma origem que você criou.</span><span class="sxs-lookup"><span data-stu-id="d545e-346">You cannot modify an origin you've created.</span></span> <span data-ttu-id="d545e-347">Em vez disso, remova a origem e adicione uma nova.</span><span class="sxs-lookup"><span data-stu-id="d545e-347">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="d545e-348">Para saber mais, confira Para remover uma origem da CDN do [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) e adicionar uma [origem para seus ativos.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)</span><span class="sxs-lookup"><span data-stu-id="d545e-348">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="d545e-349"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-349"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="d545e-350">Desabilitar a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-350">Disable the Office 365 CDN</span></span>

<span data-ttu-id="d545e-351">Use o cmdlet **Set-SPOTenantCdnEnabled** para desabilitar a CDN da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d545e-351">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="d545e-352">Se você tiver as origens pública e privada habilitadas para a CDN, será necessário executar o cmdlet duas vezes, conforme mostrado nos exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="d545e-352">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="d545e-353">Para desabilitar o uso de origens públicas na CDN, insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-353">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="d545e-354">Para desabilitar o uso das origens privadas na CDN, insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-354">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="d545e-355">Para obter mais informações sobre esse cmdlet, consulte [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span><span class="sxs-lookup"><span data-stu-id="d545e-355">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span></span>

</details>

<span data-ttu-id="d545e-356"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-356"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="d545e-357">Configurar e configurar a CDN do Office 365 usando PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="d545e-357">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="d545e-358">Os procedimentos nesta seção exigem que você use o PnP PowerShell para se conectar ao SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d545e-358">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="d545e-359">Para obter instruções, [consulte Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span><span class="sxs-lookup"><span data-stu-id="d545e-359">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="d545e-360">Conclua estas etapas para configurar a CDN para hospedar seus ativos no SharePoint Online usando PnP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d545e-360">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="d545e-361">Clique para expandir</span><span class="sxs-lookup"><span data-stu-id="d545e-361">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="d545e-362">Permitir que sua organização use a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-362">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="d545e-363">Antes de fazer alterações nas configurações da CDN do locatário, você deve recuperar o status atual da configuração da CDN privada em seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d545e-363">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="d545e-364">Conecte-se ao seu locatário usando o PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d545e-364">Connect to your tenant using PnP PowerShell:</span></span>

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="d545e-365">Agora, use o cmdlet **Get-PnPTenantCdnEnabled** para recuperar as configurações de status da CDN do locatário:</span><span class="sxs-lookup"><span data-stu-id="d545e-365">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="d545e-366">O status da CDN do CdnType especificado será exibido na tela.</span><span class="sxs-lookup"><span data-stu-id="d545e-366">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="d545e-367">Use o cmdlet **Set-PnPTenantCdnEnabled** para permitir que sua organização use a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d545e-367">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="d545e-368">Você pode permitir que sua organização use origens públicas, origens privadas ou ambas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="d545e-368">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="d545e-369">Você também pode configurar a CDN para ignorar a configuração de origens padrão ao habilita-la.</span><span class="sxs-lookup"><span data-stu-id="d545e-369">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="d545e-370">Você sempre pode adicionar essas origens posteriormente, conforme descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="d545e-370">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="d545e-371">No PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d545e-371">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="d545e-372">Por exemplo, para permitir que sua organização use origens públicas e privadas, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-372">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="d545e-373">Para permitir que sua organização use origens públicas e privadas, mas ignore a configuração das origens padrão, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-373">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="d545e-374">Confira as origens de [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) padrão para obter informações sobre as origens provisionadas por padrão quando você habilita a CDN do Office 365 e o impacto potencial de ignorar a configuração de origens padrão.</span><span class="sxs-lookup"><span data-stu-id="d545e-374">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="d545e-375">Para permitir que sua organização use origens públicas, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-375">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="d545e-376">Para permitir que sua organização use origens privadas, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-376">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="d545e-377">Para obter mais informações sobre esse cmdlet, consulte [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span><span class="sxs-lookup"><span data-stu-id="d545e-377">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="d545e-378"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-378"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="d545e-379">Alterar a lista de tipos de arquivo para incluir na CDN do Office 365 (opcional)</span><span class="sxs-lookup"><span data-stu-id="d545e-379">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="d545e-380">Ao definir tipos de arquivo usando o cmdlet **Set-PnPTenantCdnPolicy,** você substitui a lista definida no momento.</span><span class="sxs-lookup"><span data-stu-id="d545e-380">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="d545e-381">Se você quiser adicionar outros tipos de arquivo à lista, use o cmdlet primeiro para descobrir quais tipos de arquivo já são permitidos e incluí-los na lista juntamente com os novos.</span><span class="sxs-lookup"><span data-stu-id="d545e-381">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="d545e-382">Use o cmdlet **Set-PnPTenantCdnPolicy** para definir tipos de arquivo estáticos que podem ser hospedados por origens públicas e privadas na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-382">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="d545e-383">Por padrão, tipos de ativos comuns são permitidos, por exemplo.css, .gif, .jpg e .js.</span><span class="sxs-lookup"><span data-stu-id="d545e-383">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="d545e-384">No PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d545e-384">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="d545e-385">Por exemplo, para habilitar a CDN para hospedar arquivos .css e .png, digite o comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-385">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="d545e-386">Para ver quais tipos de arquivo atualmente são permitidos pela CDN, use o cmdlet **Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="d545e-386">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="d545e-387">Para obter mais informações sobre esses cmdlets, consulte [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="d545e-387">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="d545e-388"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-388"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="d545e-389">Alterar a lista de classificações de site que você deseja excluir da CDN do Office 365 (opcional)</span><span class="sxs-lookup"><span data-stu-id="d545e-389">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="d545e-390">Ao excluir classificações de site usando o cmdlet **Set-PnPTenantCdnPolicy,** você substitui a lista definida no momento.</span><span class="sxs-lookup"><span data-stu-id="d545e-390">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="d545e-391">Se você quiser excluir classificações de site adicionais, use o cmdlet primeiro para descobrir quais classificações já foram excluídas e, em seguida, adicione-as com as novas.</span><span class="sxs-lookup"><span data-stu-id="d545e-391">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="d545e-392">Use o cmdlet **Set-PnPTenantCdnPolicy** para excluir as classificações de site que você não deseja disponibilizar na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-392">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="d545e-393">Por padrão, nenhuma classificação de sites é excluída.</span><span class="sxs-lookup"><span data-stu-id="d545e-393">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="d545e-394">No PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d545e-394">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="d545e-395">Para ver quais classificações de site estão restritas no momento, use o cmdlet **Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="d545e-395">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="d545e-396">As propriedades que serão retornadas _são IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ e _ExcludeIfNoScriptDisabled_.</span><span class="sxs-lookup"><span data-stu-id="d545e-396">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="d545e-397">A _propriedade IncludeFileExtensions_ contém a lista de extensões de arquivo que serão fornecidas pela CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-397">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="d545e-398">As extensões de arquivo padrão são diferentes entre públicas e privadas.</span><span class="sxs-lookup"><span data-stu-id="d545e-398">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="d545e-399">A _propriedade ExcludeRestrictedSiteClassifications_ contém as classificações de site que você deseja excluir da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-399">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="d545e-400">Por exemplo, você pode  excluir sites marcados como Confidenciais para que o conteúdo de sites com essa classificação aplicada não seja servido da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-400">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="d545e-401">A _propriedade ExcludeIfNoScriptDisabled_ exclui o conteúdo da CDN com base nas configurações do atributo _NoScript_ no nível do site.</span><span class="sxs-lookup"><span data-stu-id="d545e-401">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="d545e-402">Por padrão, o atributo _NoScript_ é definido como **Habilitado para** _sites_ modernos e **Desabilitado** para sites _clássicos._</span><span class="sxs-lookup"><span data-stu-id="d545e-402">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="d545e-403">Isso depende das configurações do locatário.</span><span class="sxs-lookup"><span data-stu-id="d545e-403">This depends on your tenant settings.</span></span>

<span data-ttu-id="d545e-404">Para obter mais informações sobre esses cmdlets, consulte [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="d545e-404">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="d545e-405"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-405"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="d545e-406">Adicionar uma origem para seus ativos</span><span class="sxs-lookup"><span data-stu-id="d545e-406">Add an origin for your assets</span></span>

<span data-ttu-id="d545e-407">Use o cmdlet **Add-PnPTenantCdnOrigin** para definir uma origem.</span><span class="sxs-lookup"><span data-stu-id="d545e-407">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="d545e-408">Você pode definir várias origens.</span><span class="sxs-lookup"><span data-stu-id="d545e-408">You can define multiple origins.</span></span> <span data-ttu-id="d545e-409">A origem é uma URL que aponta para uma biblioteca ou pasta do SharePoint contendo os ativos que você deseja hospedar na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-409">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d545e-410">Você nunca deve colocar recursos que contenham informações do usuário ou sejam considerados confidenciais para sua organização em uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="d545e-410">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="d545e-411">O valor do _caminho é_ o caminho relativo para a biblioteca ou pasta que contém os ativos.</span><span class="sxs-lookup"><span data-stu-id="d545e-411">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="d545e-412">Você pode usar caracteres curinga, além de caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="d545e-412">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="d545e-413">As origens suportam caracteres curinga anexados à URL.</span><span class="sxs-lookup"><span data-stu-id="d545e-413">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="d545e-414">Isso permite que você crie origens que abrangem vários sites.</span><span class="sxs-lookup"><span data-stu-id="d545e-414">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="d545e-415">Por exemplo, para incluir todos os ativos na pasta páginas mestras de todos os seus sites como uma origem pública dentro da CDN, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-415">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="d545e-416">O modificador curinga \* só pode ser usado no início do caminho e corresponderá a todos os segmentos de **/** URL sob a URL especificada.</span><span class="sxs-lookup"><span data-stu-id="d545e-416">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="d545e-417">O caminho pode apontar para uma biblioteca de documentos, pasta ou site.</span><span class="sxs-lookup"><span data-stu-id="d545e-417">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="d545e-418">Por exemplo, o caminho _\*/site1_ corresponderá a todas as bibliotecas de documentos no site.</span><span class="sxs-lookup"><span data-stu-id="d545e-418">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="d545e-419">Você pode adicionar uma origem com um caminho relativo específico.</span><span class="sxs-lookup"><span data-stu-id="d545e-419">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="d545e-420">Você não pode adicionar uma origem usando o caminho completo.</span><span class="sxs-lookup"><span data-stu-id="d545e-420">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="d545e-421">Este exemplo adiciona uma origem privada da biblioteca de ativos do site em um site específico:</span><span class="sxs-lookup"><span data-stu-id="d545e-421">This example adds a private origin of the site assets library on a specific site:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="d545e-422">Este exemplo adiciona uma origem privada _da pasta folder1_ à biblioteca de ativos do site do conjunto de sites:</span><span class="sxs-lookup"><span data-stu-id="d545e-422">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="d545e-423">Se houver um espaço no caminho, você pode cercar o caminho entre aspas duplas ou substituir o espaço pela CODIFICAção de URL %20.</span><span class="sxs-lookup"><span data-stu-id="d545e-423">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="d545e-424">Os exemplos a seguir adicionam uma origem privada da pasta _1_ na biblioteca de ativos do site do conjunto de sites:</span><span class="sxs-lookup"><span data-stu-id="d545e-424">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="d545e-425">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="d545e-425">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="d545e-426">Em origens privadas, os ativos compartilhados de uma origem devem ter uma versão principal publicada antes que possam ser acessados a partir da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-426">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="d545e-427">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="d545e-427">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="d545e-428">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="d545e-428">This can take up to 15 minutes.</span></span>

<span data-ttu-id="d545e-429"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-429"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="d545e-430">Exemplo: configurar uma origem pública para suas páginas mestras e para sua biblioteca de estilos para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-430">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="d545e-431">Normalmente, essas origens são configuradas para você por padrão quando você habilita a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d545e-431">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="d545e-432">No entanto, se você quiser habilita-los manualmente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d545e-432">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="d545e-433">Use o cmdlet **Add-PnPTenantCdnOrigin** para definir a biblioteca de estilos como uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="d545e-433">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="d545e-434">Use o cmdlet **Add-PnPTenantCdnOrigin** para definir as páginas mestras como uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="d545e-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="d545e-435">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="d545e-435">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="d545e-436">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="d545e-436">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="d545e-437">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="d545e-437">This can take up to 15 minutes.</span></span>

<span data-ttu-id="d545e-438"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-438"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="d545e-439">Exemplo: Configurar uma origem privada para os ativos do site, páginas do site e imagens de publicação do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-439">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="d545e-440">Use o cmdlet **Add-PnPTenantCdnOrigin** para definir a pasta de ativos do site como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="d545e-440">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="d545e-441">Use o cmdlet **Add-PnPTenantCdnOrigin** para definir a pasta de páginas do site como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="d545e-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="d545e-442">Use o cmdlet **Add-PnPTenantCdnOrigin** para definir a pasta de imagens de publicação como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="d545e-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="d545e-443">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="d545e-443">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="d545e-444">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="d545e-444">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="d545e-445">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="d545e-445">This can take up to 15 minutes.</span></span>

<span data-ttu-id="d545e-446"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-446"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="d545e-447">Exemplo: Configurar uma origem privada para um conjunto de sites para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-447">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="d545e-448">Use o cmdlet **Add-PnPTenantCdnOrigin** para definir um conjunto de sites como uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="d545e-448">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="d545e-449">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d545e-449">For example:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="d545e-450">Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="d545e-450">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="d545e-451">Depois de executar o comando, o sistema sincroniza a configuração no datacenter.</span><span class="sxs-lookup"><span data-stu-id="d545e-451">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="d545e-452">Você pode ver uma mensagem _pendente de_ Configuração que é esperada à medida que o locatário do SharePoint Online se conecta ao serviço da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-452">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="d545e-453">Isso pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="d545e-453">This can take up to 15 minutes.</span></span>

<span data-ttu-id="d545e-454"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-454"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="d545e-455">Gerenciar a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-455">Manage the Office 365 CDN</span></span>

<span data-ttu-id="d545e-456">Depois de configurar a CDN, você pode fazer alterações em sua configuração à medida que atualiza o conteúdo ou conforme suas necessidades mudam, conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="d545e-456">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="d545e-457"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-457"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="d545e-458">Adicionar, atualizar ou remover ativos da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-458">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="d545e-459">Depois de concluir as etapas de configuração, você pode adicionar novos ativos e atualizar ou remover ativos existentes sempre que quiser.</span><span class="sxs-lookup"><span data-stu-id="d545e-459">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="d545e-460">Basta fazer suas alterações nos ativos na pasta ou na biblioteca do SharePoint que você identificou como origem.</span><span class="sxs-lookup"><span data-stu-id="d545e-460">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="d545e-461">Se você adicionar um novo ativo, ele estará disponível imediatamente por meio da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-461">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="d545e-462">No entanto, se você atualizar o ativo, levará até 15 minutos para que a nova cópia se propague e se torne disponível na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-462">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="d545e-463">Se você precisar recuperar o local da origem, poderá usar o cmdlet **Get-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="d545e-463">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="d545e-464">Para obter informações sobre como usar esse cmdlet, consulte [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="d545e-464">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="d545e-465"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-465"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="d545e-466">Remover uma origem da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-466">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="d545e-467">Você pode remover o acesso a uma pasta ou biblioteca do SharePoint que você identificou como uma origem.</span><span class="sxs-lookup"><span data-stu-id="d545e-467">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="d545e-468">Para fazer isso, use o cmdlet **Remove-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="d545e-468">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="d545e-469">Para obter informações sobre como usar esse cmdlet, consulte [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="d545e-469">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="d545e-470"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-470"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="d545e-471">Modificar uma origem na CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-471">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="d545e-472">Não é possível modificar uma origem que você criou.</span><span class="sxs-lookup"><span data-stu-id="d545e-472">You cannot modify an origin you've created.</span></span> <span data-ttu-id="d545e-473">Em vez disso, remova a origem e adicione uma nova.</span><span class="sxs-lookup"><span data-stu-id="d545e-473">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="d545e-474">Para saber mais, confira Para remover uma origem da CDN do [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) e adicionar uma [origem para seus ativos.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)</span><span class="sxs-lookup"><span data-stu-id="d545e-474">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="d545e-475"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-475"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="d545e-476">Desabilitar a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-476">Disable the Office 365 CDN</span></span>

<span data-ttu-id="d545e-477">Use o cmdlet **Set-PnPTenantCdnEnabled** para desabilitar a CDN da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d545e-477">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="d545e-478">Se você tiver as origens pública e privada habilitadas para a CDN, será necessário executar o cmdlet duas vezes, conforme mostrado nos exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="d545e-478">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="d545e-479">Para desabilitar o uso de origens públicas na CDN, insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-479">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="d545e-480">Para desabilitar o uso das origens privadas na CDN, insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d545e-480">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="d545e-481">Para obter mais informações sobre esse cmdlet, consulte [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span><span class="sxs-lookup"><span data-stu-id="d545e-481">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="d545e-482"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-482"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="d545e-483">Instalação e configuração da CDN do Office 365 usando a CLI do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-483">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="d545e-484">Os procedimentos nesta seção exigem que você tenha instalado a [CLI do Office 365.](https://aka.ms/o365cli)</span><span class="sxs-lookup"><span data-stu-id="d545e-484">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="d545e-485">Em seguida, conecte-se ao seu locatário do Office 365 usando o comando [de logon.](https://pnp.github.io/office365-cli/cmd/login/)</span><span class="sxs-lookup"><span data-stu-id="d545e-485">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="d545e-486">Conclua estas etapas para configurar a CDN para hospedar seus ativos no SharePoint Online usando a CLI do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d545e-486">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="d545e-487">Clique para expandir</span><span class="sxs-lookup"><span data-stu-id="d545e-487">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="d545e-488">Habilitar a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-488">Enable the Office 365 CDN</span></span>

<span data-ttu-id="d545e-489">Você pode gerenciar o estado da CDN do Office 365 no locatário usando o comando [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/).</span><span class="sxs-lookup"><span data-stu-id="d545e-489">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="d545e-490">Para habilitar a CDN pública do Office 365 no locatário:</span><span class="sxs-lookup"><span data-stu-id="d545e-490">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```sh
spo cdn set --type Public --enabled true
```

<span data-ttu-id="d545e-491">Para habilitar a CDN do SharePoint do Office 365, execute:</span><span class="sxs-lookup"><span data-stu-id="d545e-491">To enable the Office 365 SharePoint CDN, execute:</span></span>

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="d545e-492">Exiba o status atual da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-492">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="d545e-493">Para verificar se o tipo específico de CDN do Office 365 está habilitado ou desabilitado, use o comando [spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)</span><span class="sxs-lookup"><span data-stu-id="d545e-493">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="d545e-494">Para verificar se a CDN pública do Office 365 está habilitada:</span><span class="sxs-lookup"><span data-stu-id="d545e-494">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="d545e-495">Exibir as origens da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-495">View the Office 365 CDN origins</span></span>

<span data-ttu-id="d545e-496">Para exibir as origens de CDN pública do Office 365 configuradas no momento:</span><span class="sxs-lookup"><span data-stu-id="d545e-496">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```sh
spo cdn origin list --type Public
```

<span data-ttu-id="d545e-497">Confira [as origens de CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) padrão para obter informações sobre as origens provisionadas por padrão quando você habilita a CDN do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d545e-497">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="d545e-498">Adicionar uma origem de CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-498">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d545e-499">Você nunca deve colocar recursos considerados confidenciais para sua organização em uma biblioteca de documentos do SharePoint configurada como uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="d545e-499">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="d545e-500">Use o adicionar comando [spo cdn origem ](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) para definir uma origem de CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-500">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="d545e-501">Você pode definir várias origens.</span><span class="sxs-lookup"><span data-stu-id="d545e-501">You can define multiple origins.</span></span> <span data-ttu-id="d545e-502">A origem é uma URL que aponta para uma biblioteca ou pasta do SharePoint contendo os ativos que você deseja hospedar na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-502">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="d545e-503">Onde `path` está o caminho relativo para a pasta que contém os ativos.</span><span class="sxs-lookup"><span data-stu-id="d545e-503">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="d545e-504">Você pode usar caracteres curinga, além de caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="d545e-504">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="d545e-505">Para incluir todos os ativos na **Galeria de Páginas Mestras** de todos os sites como uma origem pública, execute:</span><span class="sxs-lookup"><span data-stu-id="d545e-505">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```sh
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="d545e-506">Para configurar uma origem privada para um conjunto de sites específico:</span><span class="sxs-lookup"><span data-stu-id="d545e-506">To configure a private origin for a specific site collection, execute:</span></span>

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="d545e-507">Após adicionar uma origem de CDN, pode levar até 15 minutos para que você possa recuperar arquivos por meio do serviço de CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-507">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="d545e-508">Você pode verificar se a origem específica já foi ativada usando o comando [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/).</span><span class="sxs-lookup"><span data-stu-id="d545e-508">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="d545e-509">Remover uma origem de CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-509">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="d545e-510">Use o comando [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) para remover uma origem de CDN para o tipo de CDN especificado.</span><span class="sxs-lookup"><span data-stu-id="d545e-510">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="d545e-511">Para remover uma origem pública da configuração da CDN, execute:</span><span class="sxs-lookup"><span data-stu-id="d545e-511">To remove a public origin from the CDN configuration, execute:</span></span>

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="d545e-512">Remover uma origem de CDN não afeta os arquivos armazenados em qualquer biblioteca de documentos correspondente a essa origem.</span><span class="sxs-lookup"><span data-stu-id="d545e-512">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="d545e-513">Se esses ativos foram referenciados usando a URL do SharePoint, o SharePoint voltará automaticamente para a URL original apontando para a biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="d545e-513">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="d545e-514">No entanto, se os ativos foram referenciados usando uma URL pública da CDN, remover a origem quebrará o link e você precisará alterá-los manualmente.</span><span class="sxs-lookup"><span data-stu-id="d545e-514">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="d545e-515">Modificar uma origem de CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-515">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="d545e-516">Não é possível alterar uma origem de CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-516">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="d545e-517">Em vez disso, você deve remover a origem de CDN definida anteriormente usando o comando `spo cdn origin remove` e adicionar outro usando o comando `spo cdn origin add`.</span><span class="sxs-lookup"><span data-stu-id="d545e-517">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="d545e-518">Alterar os tipos de arquivos a incluir na CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-518">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="d545e-519">Por padrão, os seguintes tipos de arquivo estão incluídos na CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff e .woff2_.</span><span class="sxs-lookup"><span data-stu-id="d545e-519">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="d545e-520">Se precisar incluir outros tipos de arquivo na CDN, você pode alterar a configuração de CDN usando o comando [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/).</span><span class="sxs-lookup"><span data-stu-id="d545e-520">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="d545e-521">Ao alterar a lista de tipos de arquivo, você substitui a lista definida no momento.</span><span class="sxs-lookup"><span data-stu-id="d545e-521">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="d545e-522">Se quiser incluir outros tipos de arquivo, primeiro use o comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) para descobrir quais tipos de arquivo estão configurados no momento.</span><span class="sxs-lookup"><span data-stu-id="d545e-522">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="d545e-523">Para adicionar o _tipo de arquivo JSON_ à lista padrão de tipos de arquivo incluídos na CDN pública, execute:</span><span class="sxs-lookup"><span data-stu-id="d545e-523">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="d545e-524">Altere a lista de classificações de site que você deseja excluir da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-524">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="d545e-525">Use o comando [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) para excluir as classificações de site que não deseja disponibilizar na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-525">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="d545e-526">Por padrão, nenhuma classificação de sites é excluída.</span><span class="sxs-lookup"><span data-stu-id="d545e-526">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="d545e-527">Ao alterar a lista de classificações de sites excluída, você substitui a lista definida no momento.</span><span class="sxs-lookup"><span data-stu-id="d545e-527">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="d545e-528">Se desejar excluir outras classificações, primeiro use o comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) para descobrir quais classificações estão configuradas no momento.</span><span class="sxs-lookup"><span data-stu-id="d545e-528">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="d545e-529">Para excluir sites classificados como _HBI_ da CDN pública, execute</span><span class="sxs-lookup"><span data-stu-id="d545e-529">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="d545e-530">Desabilitar a CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-530">Disable the Office 365 CDN</span></span>

<span data-ttu-id="d545e-531">Para desabilitar a CDN do Office 365, use o comando `spo cdn set`, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d545e-531">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="d545e-532">Usando seus ativos da CDN</span><span class="sxs-lookup"><span data-stu-id="d545e-532">Using your CDN assets</span></span>

<span data-ttu-id="d545e-533">Agora que você habilitar a CDN e configurou origens e políticas, pode começar a usar seus ativos da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-533">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="d545e-534">Esta seção ajudará você a entender como usar URLs de CDN em suas páginas e conteúdo do SharePoint para que o SharePoint redirecione as solicitações de ativos de origens públicas e privadas para a CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-534">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="d545e-535">Atualizando links para ativos da CDN</span><span class="sxs-lookup"><span data-stu-id="d545e-535">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="d545e-536">Usando ativos em origens públicas</span><span class="sxs-lookup"><span data-stu-id="d545e-536">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="d545e-537">Usando ativos em origens privadas</span><span class="sxs-lookup"><span data-stu-id="d545e-537">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="d545e-538">Para obter informações sobre como usar a CDN para hospedar Web Parts do lado do cliente, consulte o tópico Hospedar a Web Part do lado do cliente da CDN do [Office 365 (Hello World, parte 4).](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)</span><span class="sxs-lookup"><span data-stu-id="d545e-538">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="d545e-539">Se você adicionar a _pasta ClientSideAssets_ à lista privada de origens de **CDN,** as Web Parts personalizadas hospedadas pela CDN não serão renderizações.</span><span class="sxs-lookup"><span data-stu-id="d545e-539">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="d545e-540">Os arquivos usados por Web Parts SPFX só podem utilizar a CDN pública e a pasta ClientSideAssets é uma origem padrão para a CDN pública.</span><span class="sxs-lookup"><span data-stu-id="d545e-540">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="d545e-541">Atualizando links para ativos da CDN</span><span class="sxs-lookup"><span data-stu-id="d545e-541">Updating links to CDN assets</span></span>

<span data-ttu-id="d545e-542">Para usar ativos que você adicionou a uma origem, basta atualizar os links para o arquivo original com o caminho para o arquivo na origem.</span><span class="sxs-lookup"><span data-stu-id="d545e-542">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="d545e-543">Edite a página ou o conteúdo que contém links para ativos que você adicionou a uma origem.</span><span class="sxs-lookup"><span data-stu-id="d545e-543">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="d545e-544">Você também pode usar um dos vários métodos para pesquisar globalmente e substituir links em um site ou conjunto de sites de entrada se quiser atualizar o link para um determinado ativo em todos os lugares em que ele aparecer.</span><span class="sxs-lookup"><span data-stu-id="d545e-544">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="d545e-545">Para cada link para um ativo em uma origem, substitua o caminho pelo caminho para o arquivo na origem da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-545">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="d545e-546">Você pode usar caminhos relativos.</span><span class="sxs-lookup"><span data-stu-id="d545e-546">You can use relative paths.</span></span>
+ <span data-ttu-id="d545e-547">Salve a página ou o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d545e-547">Save the page or content.</span></span>

<span data-ttu-id="d545e-548">Por exemplo, considere a imagem _/site/SiteAssets/images/image.png_, que você copiou para a pasta /site/site da biblioteca de _documentos/CDN_origins/public/_.</span><span class="sxs-lookup"><span data-stu-id="d545e-548">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="d545e-549">Para usar o ativo da CDN, substitua o caminho original para o local do arquivo de imagem pelo caminho para a origem para tornar a nova URL _/site/CDN_origins/public/image.png_.</span><span class="sxs-lookup"><span data-stu-id="d545e-549">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="d545e-550">Se você quiser usar a URL completa para o ativo em vez de um caminho relativo, construa o link da mesma forma:</span><span class="sxs-lookup"><span data-stu-id="d545e-550">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="d545e-551">Em geral, você não deve codificar URLs diretamente para ativos na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-551">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="d545e-552">No entanto, você pode construir manualmente URLs para ativos em origens públicas, se necessário.</span><span class="sxs-lookup"><span data-stu-id="d545e-552">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="d545e-553">Para obter mais informações, consulte [URLs de CDN de hardcoding para ativos públicos.](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets)</span><span class="sxs-lookup"><span data-stu-id="d545e-553">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="d545e-554">Para saber mais sobre como verificar se os ativos estão sendo atendidos na CDN, confira Como confirmar se os ativos estão sendo atendidos pela [CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) na seção Solução de problemas da CDN do [Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="d545e-554">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in the [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) section.</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="d545e-555">Usando ativos em origens públicas</span><span class="sxs-lookup"><span data-stu-id="d545e-555">Using assets in public origins</span></span>

<span data-ttu-id="d545e-556">O  recurso publicação no SharePoint Online reescreve automaticamente URLs de ativos armazenados em origens públicas para seus equivalentes de CDN para que os ativos sejam atendidos do serviço de CDN em vez do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d545e-556">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="d545e-557">Se sua origem estiver em um site com o recurso publicação habilitado e os ativos que você deseja descarregar para a CDN estão em uma das categorias a seguir, o SharePoint reescreverá automaticamente URLs para ativos na origem, desde que o ativo não tenha sido excluído por uma política de CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-557">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="d545e-558">Mostramos a seguir uma visão geral dos links reescritos automaticamente pelo recurso de Publicação do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="d545e-558">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="d545e-559">URLs IMG/LINK/CSS em respostas de HTML de página de publicação clássica</span><span class="sxs-lookup"><span data-stu-id="d545e-559">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="d545e-560">Incluem-se imagens adicionadas por autores no conteúdo HTML de uma página</span><span class="sxs-lookup"><span data-stu-id="d545e-560">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="d545e-561">URLs de imagem da web part Apresentação de Slides da Biblioteca de Imagens</span><span class="sxs-lookup"><span data-stu-id="d545e-561">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="d545e-562">Campos de imagem nos resultados da API REST SPList (RenderListDataAsStream)</span><span class="sxs-lookup"><span data-stu-id="d545e-562">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="d545e-563">Usar a nova _propriedade ImageFieldsToTryRewriteToCdnUrls_ para fornecer uma lista de campos separados por vírgulas</span><span class="sxs-lookup"><span data-stu-id="d545e-563">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="d545e-564">Oferece suporte a campos de hiperlink e campos PublishingImage</span><span class="sxs-lookup"><span data-stu-id="d545e-564">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="d545e-565">Representações de imagem do SharePoint</span><span class="sxs-lookup"><span data-stu-id="d545e-565">SharePoint image renditions</span></span>

<span data-ttu-id="d545e-566">O diagrama a seguir ilustra o fluxo de trabalho quando o SharePoint recebe uma solicitação para uma página que contém ativos de uma origem pública.</span><span class="sxs-lookup"><span data-stu-id="d545e-566">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="d545e-567">![Diagrama de fluxo de trabalho: recuperar ativos de CDN do Office 365 de uma origem pública](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Fluxo de trabalho: recuperar ativos de CDN do Office 365 de uma origem pública")</span><span class="sxs-lookup"><span data-stu-id="d545e-567">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="d545e-568">Se quiser desabilitar a reescrita automática para URLs específicas em uma página, você pode fazer check-out da página e adicionar o parâmetro de cadeia de caracteres de **consulta? NoAutoReWrites=true** no final de cada link que você deseja desabilitar.</span><span class="sxs-lookup"><span data-stu-id="d545e-568">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="hardcoding-cdn-urls-for-public-assets"></a><span data-ttu-id="d545e-569">Hardcoding CDN URLs for public assets</span><span class="sxs-lookup"><span data-stu-id="d545e-569">Hardcoding CDN URLs for public assets</span></span>

<span data-ttu-id="d545e-570">Se  o recurso de Publicação não estiver habilitado para uma origem pública ou se o ativo não for um dos tipos de link suportados pelo recurso de reescrita automática do serviço cdn, você pode construir manualmente URLs para o local da CDN dos ativos e usar essas URLs em seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d545e-570">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="d545e-571">Você não pode codificar URLs de CDN para ativos em uma origem privada porque o token de acesso necessário que forma a última seção da URL é gerado no momento em que o recurso é solicitado.</span><span class="sxs-lookup"><span data-stu-id="d545e-571">You cannot hardcode CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span>

<span data-ttu-id="d545e-572">Para ativos de CDN públicos, o formato da URL terá a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="d545e-572">For public CDN assets, the URL format will look like the following:</span></span>

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="d545e-573">Substitua **TenantHostName pelo** nome do locatário.</span><span class="sxs-lookup"><span data-stu-id="d545e-573">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="d545e-574">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="d545e-574">Example:</span></span>

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

### <a name="using-assets-in-private-origins"></a><span data-ttu-id="d545e-575">Usando ativos em origens privadas</span><span class="sxs-lookup"><span data-stu-id="d545e-575">Using assets in private origins</span></span>

<span data-ttu-id="d545e-576">Nenhuma configuração adicional é necessária para usar ativos em origens privadas.</span><span class="sxs-lookup"><span data-stu-id="d545e-576">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="d545e-577">O SharePoint Online reescreve automaticamente URLs para ativos em origens privadas, portanto, as solicitações para esses ativos sempre serão atendidas na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-577">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="d545e-578">Você não pode criar manualmente URLs para ativos de CDN em origens privadas porque essas URLs contêm tokens que devem ser gerados automaticamente pelo SharePoint Online no momento em que o ativo é solicitado.</span><span class="sxs-lookup"><span data-stu-id="d545e-578">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="d545e-579">O acesso a ativos em origens privadas é protegido por tokens gerados dinamicamente com base nas permissões do usuário para a origem, com as advertências descritas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="d545e-579">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="d545e-580">Os usuários devem ter pelo menos **acesso** de leitura às origens da CDN para renderizar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d545e-580">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="d545e-581">O diagrama a seguir ilustra o fluxo de trabalho quando o SharePoint recebe uma solicitação para uma página que contém ativos de uma origem privada.</span><span class="sxs-lookup"><span data-stu-id="d545e-581">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="d545e-582">![Diagrama de fluxo de trabalho: recuperar ativos da CDN do Office 365 de uma origem privada](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Fluxo de trabalho: recuperar ativos de CDN do Office 365 de uma origem privada")</span><span class="sxs-lookup"><span data-stu-id="d545e-582">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="d545e-583">Autorização baseada em token em origens privadas</span><span class="sxs-lookup"><span data-stu-id="d545e-583">Token-based authorization in private origins</span></span>

<span data-ttu-id="d545e-584">O acesso a ativos em origens privadas na CDN do Office 365 é concedido por tokens gerados pelo SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d545e-584">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="d545e-585">Os usuários que já têm permissão para acessar a pasta ou biblioteca designada pela origem receberão automaticamente tokens que permitem ao usuário acessar o arquivo com base em seu nível de permissão.</span><span class="sxs-lookup"><span data-stu-id="d545e-585">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="d545e-586">Esses tokens de acesso são válidos de 30 a 90 minutos depois que são gerados para ajudar a evitar ataques de repetição de token.</span><span class="sxs-lookup"><span data-stu-id="d545e-586">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="d545e-587">Depois que o token de acesso é gerado, o SharePoint Online retorna um URI personalizado para o cliente que contém dois parâmetros de autorização _eat_ (token de autorização de borda) e _oat_ (token de autorização de origem).</span><span class="sxs-lookup"><span data-stu-id="d545e-587">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="d545e-588">A estrutura de cada token é< de expiração no formato de época _>__< da assinatura segura >_.</span><span class="sxs-lookup"><span data-stu-id="d545e-588">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="d545e-589">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d545e-589">For example:</span></span>

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="d545e-590">Qualquer pessoa em posse do token pode acessar o recurso na CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-590">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="d545e-591">No entanto, as URLs que contêm esses tokens de acesso são compartilhadas apenas por HTTPS, portanto, a menos que a URL seja explicitamente compartilhada por um usuário final antes que o token expire, o ativo não será acessível a usuários não autorizados.</span><span class="sxs-lookup"><span data-stu-id="d545e-591">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="d545e-592">Permissões de nível de item não são suportadas para ativos em origens privadas</span><span class="sxs-lookup"><span data-stu-id="d545e-592">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="d545e-593">É importante observar que o SharePoint Online não dá suporte a permissões de nível de item para ativos em origens privadas.</span><span class="sxs-lookup"><span data-stu-id="d545e-593">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="d545e-594">Por exemplo, para um arquivo localizado em , os usuários têm acesso `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` efetivo ao arquivo dadas as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="d545e-594">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="d545e-595">Usuário</span><span class="sxs-lookup"><span data-stu-id="d545e-595">User</span></span>  |<span data-ttu-id="d545e-596">Permissions</span><span class="sxs-lookup"><span data-stu-id="d545e-596">Permissions</span></span>  |<span data-ttu-id="d545e-597">Acesso efetivo</span><span class="sxs-lookup"><span data-stu-id="d545e-597">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="d545e-598">Usuário 1</span><span class="sxs-lookup"><span data-stu-id="d545e-598">User 1</span></span>     |<span data-ttu-id="d545e-599">Tem acesso à pasta1</span><span class="sxs-lookup"><span data-stu-id="d545e-599">Has access to folder1</span></span>         |<span data-ttu-id="d545e-600">Pode acessar image1.jpg cdn</span><span class="sxs-lookup"><span data-stu-id="d545e-600">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="d545e-601">Usuário 2</span><span class="sxs-lookup"><span data-stu-id="d545e-601">User 2</span></span>     |<span data-ttu-id="d545e-602">Não tem acesso à pasta1</span><span class="sxs-lookup"><span data-stu-id="d545e-602">Does not have access to folder1</span></span>         |<span data-ttu-id="d545e-603">Não é possível image1.jpg a partir da CDN</span><span class="sxs-lookup"><span data-stu-id="d545e-603">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="d545e-604">Usuário 3</span><span class="sxs-lookup"><span data-stu-id="d545e-604">User 3</span></span>     |<span data-ttu-id="d545e-605">Não tem acesso à pasta1, mas tem permissão explícita para acessar image1.jpg no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-605">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="d545e-606">Pode acessar o recurso image1.jpg diretamente do SharePoint Online, mas não da CDN</span><span class="sxs-lookup"><span data-stu-id="d545e-606">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="d545e-607">Usuário 4</span><span class="sxs-lookup"><span data-stu-id="d545e-607">User 4</span></span>     |<span data-ttu-id="d545e-608">Tem acesso à pasta1, mas foi explicitamente negado acesso image1.jpg no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-608">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="d545e-609">Não é possível acessar o ativo do SharePoint Online, mas pode acessar o ativo da CDN apesar de ter sido negado acesso ao arquivo no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-609">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="d545e-610"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-610"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="d545e-611">Solução de problemas da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-611">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="d545e-612"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="d545e-612"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="d545e-613">Como confirmar se os ativos estão sendo atendidos pela CDN?</span><span class="sxs-lookup"><span data-stu-id="d545e-613">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="d545e-614">Depois de adicionar links a ativos de CDN a uma página, você poderá confirmar se o ativo está sendo servido pela CDN navegando até a página, clicando com o botão direito do mouse na imagem depois de renderizado e revendo a URL da imagem.</span><span class="sxs-lookup"><span data-stu-id="d545e-614">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="d545e-615">Você também pode usar as ferramentas de desenvolvedor do navegador para exibir a URL de cada ativo em uma página ou usar uma ferramenta de rastreamento de rede de terceiros.</span><span class="sxs-lookup"><span data-stu-id="d545e-615">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="d545e-616">Se você usar uma ferramenta de rede como o Fiddler para testar seus ativos fora da renderização do ativo de uma página do SharePoint, deverá adicionar manualmente o título de referência "Referer: " à solicitação GET em que a URL é a URL raiz do seu locatário do `https://yourdomain.sharepoint.com` SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d545e-616">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="d545e-617">Você não pode testar URLs de CDN diretamente em um navegador da Web porque você deve ter um referenciador vindo do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="d545e-617">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="d545e-618">No entanto, se você adicionar a URL do ativo da CDN a uma página do SharePoint e abrir a página em um navegador, verá o ativo da CDN renderizado na página.</span><span class="sxs-lookup"><span data-stu-id="d545e-618">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="d545e-619">Para obter mais informações sobre como usar as ferramentas de desenvolvedor no navegador Microsoft Edge, consulte [Ferramentas de Desenvolvedor do Microsoft Edge.](https://docs.microsoft.com/microsoft-edge/devtools-guide)</span><span class="sxs-lookup"><span data-stu-id="d545e-619">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="d545e-620">Para assistir a um vídeo curto hospedado no canal do YouTube de Padrões e Práticas do Desenvolvedor do [SharePoint](https://aka.ms/sppnp-videos) demonstrando como verificar se sua CDN está funcionando, consulte Verificando o uso da [CDN](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)e garantindo a conectividade de rede ideal.</span><span class="sxs-lookup"><span data-stu-id="d545e-620">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="d545e-621">Por que os ativos de uma nova origem estão indisponíveis?</span><span class="sxs-lookup"><span data-stu-id="d545e-621">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="d545e-622">Os ativos em novas origens não estarão disponíveis imediatamente para uso, pois leva tempo para que o registro se propague pela CDN e para que os ativos sejam carregados a partir da origem para o armazenamento da CDN.</span><span class="sxs-lookup"><span data-stu-id="d545e-622">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="d545e-623">O tempo necessário para que os ativos sejam disponibilizados na CDN depende de quantos ativos e tamanhos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d545e-623">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="d545e-624">Minha web part do lado do cliente ou a solução da Estrutura do SharePoint não está funcionando</span><span class="sxs-lookup"><span data-stu-id="d545e-624">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="d545e-625">Quando você habilita a CDN do Office 365 para origens públicas, o serviço CDN cria automaticamente estas origens padrão:</span><span class="sxs-lookup"><span data-stu-id="d545e-625">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="d545e-626">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="d545e-626">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="d545e-627">\*/STYLE LIBRARY</span><span class="sxs-lookup"><span data-stu-id="d545e-627">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="d545e-628">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="d545e-628">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="d545e-629">Se a origem \*/clientsideassets estiver ausente, as soluções da Estrutura do SharePoint falharão e nenhuma mensagem de aviso ou erro será gerada.</span><span class="sxs-lookup"><span data-stu-id="d545e-629">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="d545e-630">Essa origem pode estar ausente porque a CDN foi habilitada com o parâmetro _-NoDefaultOrigins_ definido como **$true** ou porque a origem foi excluída manualmente.</span><span class="sxs-lookup"><span data-stu-id="d545e-630">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="d545e-631">Você pode verificar quais origens estão presentes com o seguinte comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d545e-631">You can check to see which origins are present with the following PowerShell command:</span></span>

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="d545e-632">Ou você pode verificar com a CLI do Office 365:</span><span class="sxs-lookup"><span data-stu-id="d545e-632">Or you can check with the Office 365 CLI:</span></span>

``` powershell
spo cdn origin list
```

<span data-ttu-id="d545e-633">Para adicionar a origem no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d545e-633">To add the origin in PowerShell:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="d545e-634">Para adicionar a origem na CLI do Office 365:</span><span class="sxs-lookup"><span data-stu-id="d545e-634">To add the origin in the Office 365 CLI:</span></span>

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="d545e-635">Quais módulos do PowerShell e shells de CLI preciso para trabalhar com a CDN do Office 365?</span><span class="sxs-lookup"><span data-stu-id="d545e-635">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="d545e-636">Você pode optar por trabalhar com a CDN do Office 365 usando o módulo do PowerShell do Shell de Gerenciamento do **SharePoint Online** ou a **CLI do Office 365.**</span><span class="sxs-lookup"><span data-stu-id="d545e-636">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="d545e-637">Introdução ao Shell de Gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d545e-637">Getting started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="d545e-638">Instalar a CLI do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-638">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="d545e-639">Confira também</span><span class="sxs-lookup"><span data-stu-id="d545e-639">See also</span></span>

[<span data-ttu-id="d545e-640">Redes de Distribuição de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="d545e-640">Content Delivery Networks</span></span>](https://aka.ms/o365cdns)

[<span data-ttu-id="d545e-641">Planejamento de rede e ajuste de desempenho para o Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-641">Network planning and performance tuning for Office 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="d545e-642">Série de desempenho do SharePoint - série de vídeos da CDN do Office 365</span><span class="sxs-lookup"><span data-stu-id="d545e-642">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
