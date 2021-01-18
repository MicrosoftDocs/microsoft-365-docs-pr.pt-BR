---
title: Alinhamento de Descobertas Eletrônicos Avançadas com o EDRM
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: O fluxo de trabalho integrado da Descoberta Eletrônica Avançada no Microsoft 365 se alinha ao processo de Descoberta Eletrônica descrito pelo EDRM (Electronic Discovery Reference Model).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ca94baf1fc57ac014a32a80ddc5705feeb2c842
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841591"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a><span data-ttu-id="99a43-103">Alinhamento da Descoberta Eletrônica Avançada com o Modelo de Referência de Descoberta Eletrônica</span><span class="sxs-lookup"><span data-stu-id="99a43-103">Advanced eDiscovery alignment with the Electronic Discovery Reference Model</span></span>

<span data-ttu-id="99a43-104">O fluxo de trabalho integrado da Descoberta Eletrônica Avançada no Microsoft 365 se alinha ao processo de Descoberta Eletrônica descrito pelo EDRM (Electronic Discovery Reference Model).</span><span class="sxs-lookup"><span data-stu-id="99a43-104">The built-in workflow of Advanced eDiscovery in Microsoft 365 aligns with the eDiscovery process outlined by the Electronic Discovery Reference Model (EDRM).</span></span>

![O EDRM (Electronic Discovery Reference Model)](../media/EDRMv1.png)

<span data-ttu-id="99a43-106">(Cortesia de origem da imagem edrm.net.</span><span class="sxs-lookup"><span data-stu-id="99a43-106">(Image source courtesy of edrm.net.</span></span> <span data-ttu-id="99a43-107">A imagem de origem foi disponibilizada em Creative Commons Attribution 3.0 Unported License.)</span><span class="sxs-lookup"><span data-stu-id="99a43-107">The source image was made available under Creative Commons Attribution 3.0 Unported License.)</span></span>

<span data-ttu-id="99a43-108">Em um nível alto, veja como a Descoberta Avançada dá suporte ao fluxo de trabalho EDRM:</span><span class="sxs-lookup"><span data-stu-id="99a43-108">At a high level, here's how Advanced eDiscovery supports the EDRM workflow:</span></span>

- <span data-ttu-id="99a43-109">**Identificação.**</span><span class="sxs-lookup"><span data-stu-id="99a43-109">**Identification.**</span></span> <span data-ttu-id="99a43-110">Depois de identificar possíveis pessoas de interesse em uma investigação, você pode adicioná-las como custodiantes (também chamadas de responsáveis de *dados,* porque elas podem ter informações relevantes para a investigação) para um caso de Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="99a43-110">After you identify potential persons of interest in an investigation, you can add them as custodians (also called *data custodians*, because they may possess information that's relevant to the investigation) to an Advanced eDiscovery case.</span></span> <span data-ttu-id="99a43-111">Depois que os usuários são adicionados como custodiantes, é fácil preservar, coletar e revisar documentos custodiantes.</span><span class="sxs-lookup"><span data-stu-id="99a43-111">After users are added as custodians, it's easy to preserve, collect, and review custodian documents.</span></span>

- <span data-ttu-id="99a43-112">**Preservação.**</span><span class="sxs-lookup"><span data-stu-id="99a43-112">**Preservation.**</span></span> <span data-ttu-id="99a43-113">Para preservar e proteger dados que são relevantes para uma investigação, a Descoberta Avançada permite que você coloque uma responsabilidade legal sobre as fontes de dados associadas aos responsáveis em um caso.</span><span class="sxs-lookup"><span data-stu-id="99a43-113">To preserve and protect data that's relevant to an investigation, Advanced eDiscovery lets you place a legal hold on the data sources associated with the custodians in a case.</span></span> <span data-ttu-id="99a43-114">Você também pode colocar dados não custodial em espera.</span><span class="sxs-lookup"><span data-stu-id="99a43-114">You can also place non-custodial data on hold.</span></span> <span data-ttu-id="99a43-115">A Descoberta Eletrônica Avançada também tem um fluxo de trabalho de comunicação integrado para que você possa enviar notificações de responsabilidade legal aos responsáveis e acompanhar suas confirmações.</span><span class="sxs-lookup"><span data-stu-id="99a43-115">Advanced eDiscovery also has a built-in communications workflow so you can send legal hold notifications to custodians and track their acknowledgments.</span></span>

- <span data-ttu-id="99a43-116">**Coleção.**</span><span class="sxs-lookup"><span data-stu-id="99a43-116">**Collection.**</span></span> <span data-ttu-id="99a43-117">Depois de identificar (e preservar) as fontes de dados relevantes para a investigação, você pode usar a ferramenta de pesquisa interna na Pesquisa de Descoberta Avançada e coletar dados a vivos das fontes de dados custodial (e fontes de dados não custodial, se aplicável) que podem ser relevantes para o caso.</span><span class="sxs-lookup"><span data-stu-id="99a43-117">After you identified (and preserved) the data sources relevant to the investigation, you can use the built-in search tool in Advanced eDiscovery search for and collect live data from the custodial data sources (and non-custodial data sources, if applicable) that may be relevant to the case.</span></span>

- <span data-ttu-id="99a43-118">**Processamento.**</span><span class="sxs-lookup"><span data-stu-id="99a43-118">**Processing.**</span></span> <span data-ttu-id="99a43-119">Depois de coletar todos os dados relevantes para o caso, a próxima etapa é processá-los para análise e revisão posteriores.</span><span class="sxs-lookup"><span data-stu-id="99a43-119">After you've collected all data relevant to the case, the next step is process it for further review and analysis.</span></span> <span data-ttu-id="99a43-120">Na Descoberta Avançada, os dados in-loco que você identificou na fase de coleta são copiados para um local de Armazenamento do Azure (chamado de conjunto de *revisão),* que fornece uma exibição estática dos dados da ocorrência.</span><span class="sxs-lookup"><span data-stu-id="99a43-120">In Advanced eDiscovery, the in-place data that you identified in the collection phase is copied to an Azure Storage location (called a *review set*), which provides you with a static view of the case data.</span></span> 

- <span data-ttu-id="99a43-121">**Revisão.**</span><span class="sxs-lookup"><span data-stu-id="99a43-121">**Review.**</span></span> <span data-ttu-id="99a43-122">Depois que os dados são adicionados a um conjunto de revisão, você pode exibir documentos específicos e executar consultas adicionais para reduzir os dados ao que é mais relevante para o caso.</span><span class="sxs-lookup"><span data-stu-id="99a43-122">After data has been added to a review set, you can view specific documents and run additional queries to reduce the data to what is most relevant to the case.</span></span> <span data-ttu-id="99a43-123">Além disso, pode anotar e marcar documentos específicos.</span><span class="sxs-lookup"><span data-stu-id="99a43-123">Also, can annotate and tag specific documents.</span></span>

- <span data-ttu-id="99a43-124">**Análise.**</span><span class="sxs-lookup"><span data-stu-id="99a43-124">**Analysis.**</span></span> <span data-ttu-id="99a43-125">A Descoberta Avançada fornece uma ferramenta de análise integrada que ajuda você a excluir ainda mais os dados do conjunto de revisão que você determina que não são relevantes para a investigação.</span><span class="sxs-lookup"><span data-stu-id="99a43-125">Advanced eDiscovery provides integrated analytics tool that helps you further cull data from the review set that you determine isn't relevant to the investigation.</span></span> <span data-ttu-id="99a43-126">Além de reduzir o volume de dados relevantes, a Descoberta Antecipada também ajuda a economizar custos de revisão jurídica, o que permite organizar o conteúdo para tornar o processo de revisão mais fácil e eficiente.</span><span class="sxs-lookup"><span data-stu-id="99a43-126">In addition to reducing the volume of relevant data, Advance eDiscovery also helps you save legal review costs by letting you organize content to make the review process easier and more efficient.</span></span>

- <span data-ttu-id="99a43-127">**Produção** e **apresentação.**</span><span class="sxs-lookup"><span data-stu-id="99a43-127">**Production** and **Presentation.**</span></span> <span data-ttu-id="99a43-128">Quando estiver pronto, você poderá exportar documentos de um conjunto de revisão para revisão jurídica.</span><span class="sxs-lookup"><span data-stu-id="99a43-128">When you're ready, you can export documents from a review set for legal review.</span></span> <span data-ttu-id="99a43-129">Você pode exportar documentos em seu formato nativo ou em um formato especificado por EDRM para que eles possam ser importados para aplicativos de revisão de terceiros.</span><span class="sxs-lookup"><span data-stu-id="99a43-129">You can export documents in their native format or in an EDRM-specified format so they can be imported into third-party review applications.</span></span>

## <a name="more-information"></a><span data-ttu-id="99a43-130">Mais informações</span><span class="sxs-lookup"><span data-stu-id="99a43-130">More information</span></span>

<span data-ttu-id="99a43-131">Para começar a usar a Descoberta Avançada, confira:</span><span class="sxs-lookup"><span data-stu-id="99a43-131">To get started using Advanced eDiscovery, see:</span></span>

- [<span data-ttu-id="99a43-132">Configurar a Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="99a43-132">Set up Advanced eDiscovery</span></span>](get-started-with-advanced-ediscovery.md)

- [<span data-ttu-id="99a43-133">Criar e gerenciar um caso de Descoberta Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="99a43-133">Create and manage an Advanced eDiscovery case</span></span>](create-and-manage-advanced-ediscoveryv2-case.md)