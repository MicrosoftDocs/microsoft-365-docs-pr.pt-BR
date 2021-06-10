---
title: Ajuste o desempenho do Exchange Online
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: Este artigo contém dicas gerais e links para outros recursos que lhe dizem como melhorar o desempenho de Exchange Online.
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909437"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="40233-103">Ajuste o desempenho do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="40233-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="40233-104">Este artigo contém dicas gerais e links para outros recursos que lhe dizem como melhorar o desempenho Exchange Online, especialmente na frente de uma migração.</span><span class="sxs-lookup"><span data-stu-id="40233-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="40233-105">Este artigo faz parte do planejamento de rede e [ajuste de desempenho para Office 365](./network-planning-and-performance.md) projeto.</span><span class="sxs-lookup"><span data-stu-id="40233-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="40233-106">Coisas a considerar para melhorar o Exchange Online desempenho</span><span class="sxs-lookup"><span data-stu-id="40233-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="40233-107">Para melhorar a velocidade da migração e reduzir as restrições de largura de banda da sua organização para Exchange Online, considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="40233-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="40233-108">**Reduzir tamanhos de caixa de correio.**</span><span class="sxs-lookup"><span data-stu-id="40233-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="40233-109">O tamanho menor da caixa de correio melhora a velocidade de migração.</span><span class="sxs-lookup"><span data-stu-id="40233-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="40233-110">**Use os recursos de movimentação de caixa de correio com uma implantação Exchange híbrida.**</span><span class="sxs-lookup"><span data-stu-id="40233-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="40233-111">Com uma Exchange híbrida, o email offline (na forma de . Arquivos OST) não exigem re download ao migrar para Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="40233-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="40233-112">Isso reduz significativamente seus requisitos de largura de banda de download.</span><span class="sxs-lookup"><span data-stu-id="40233-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="40233-113">**Agende movimentações de caixa de correio para ocorrer durante períodos de baixo tráfego da Internet e baixo uso Exchange local.**</span><span class="sxs-lookup"><span data-stu-id="40233-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="40233-114">Quando o agendamento é movimentado, as solicitações de migração são enviadas ao proxy de replicação de caixa de correio e podem não ocorrer imediatamente.</span><span class="sxs-lookup"><span data-stu-id="40233-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="40233-115">**Use popouts enxutos Outlook na Web.**</span><span class="sxs-lookup"><span data-stu-id="40233-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="40233-116">Os pop-outs enxutos fornecem versões menores e menos intensas de memória de determinadas mensagens de email no Microsoft Edge ou no Internet Explorer renderizar alguns componentes no servidor.</span><span class="sxs-lookup"><span data-stu-id="40233-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="40233-117">Para obter mais informações, [consulte Use popouts enxutos para reduzir](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)a memória usada ao ler mensagens de email .</span><span class="sxs-lookup"><span data-stu-id="40233-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="40233-118">Consultoria geral</span><span class="sxs-lookup"><span data-stu-id="40233-118">General advice</span></span>

- <span data-ttu-id="40233-119">Certifique-se de que a pesquisa DNS outlook.office.com o datacenter MS em um local de entrada lógico para sua localização.</span><span class="sxs-lookup"><span data-stu-id="40233-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="40233-120">Pesquise o cache da caixa de correio e escolha as opções apropriadas (re.</span><span class="sxs-lookup"><span data-stu-id="40233-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="40233-121">período de cache, cache de caixa de correio compartilhada, et cetera).</span><span class="sxs-lookup"><span data-stu-id="40233-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="40233-122">Mantenha seus Outlook dados de passagem de conexões VPN (para um escritório central) antes de passar pela Internet.</span><span class="sxs-lookup"><span data-stu-id="40233-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="40233-123">Certifique-se de que seus dados de caixa de correio aderem às limitações de valores de pasta e item.</span><span class="sxs-lookup"><span data-stu-id="40233-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="40233-124">Para obter mais informações sobre Exchange de migração, [consulte Office 365 de migração e práticas recomendadas.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)</span><span class="sxs-lookup"><span data-stu-id="40233-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
