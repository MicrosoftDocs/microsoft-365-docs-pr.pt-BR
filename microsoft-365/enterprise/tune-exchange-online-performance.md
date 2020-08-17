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
description: Este artigo contém dicas gerais e links para outros recursos que explicam como melhorar o desempenho do Exchange Online.
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687359"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="99b6d-103">Ajuste o desempenho do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="99b6d-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="99b6d-104">Este artigo contém dicas gerais e links para outros recursos que explicam como melhorar o desempenho do Exchange Online, particularmente na frente de uma migração.</span><span class="sxs-lookup"><span data-stu-id="99b6d-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="99b6d-105">Este artigo faz parte do [planejamento de rede e ajuste de desempenho para o projeto do Office 365](https://aka.ms/tune) .</span><span class="sxs-lookup"><span data-stu-id="99b6d-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="99b6d-106">Considerações a serem consideradas para melhorar o desempenho do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="99b6d-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="99b6d-107">Para melhorar a velocidade da migração e reduzir as restrições de largura de banda da sua organização para o Exchange Online, considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="99b6d-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="99b6d-108">**Reduzir tamanhos de caixa de correio.**</span><span class="sxs-lookup"><span data-stu-id="99b6d-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="99b6d-109">O tamanho de caixa de correio menor melhora a velocidade de migração.</span><span class="sxs-lookup"><span data-stu-id="99b6d-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="99b6d-110">**Use os recursos de movimentação de caixa de correio com uma implantação híbrida do Exchange.**</span><span class="sxs-lookup"><span data-stu-id="99b6d-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="99b6d-111">Com uma implantação híbrida do Exchange, email offline (na forma de. OST) não requer o novo download ao migrar para o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="99b6d-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="99b6d-112">Isso reduz significativamente os requisitos de largura de banda de download.</span><span class="sxs-lookup"><span data-stu-id="99b6d-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="99b6d-113">**Agendar movimentações de caixa de correio para ocorrer durante períodos de baixo tráfego da Internet e baixo uso do Exchange no local.**</span><span class="sxs-lookup"><span data-stu-id="99b6d-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="99b6d-114">Ao agendar movimentações, as solicitações de migração são enviadas para o proxy de replicação de caixa de correio e podem não acontecer imediatamente.</span><span class="sxs-lookup"><span data-stu-id="99b6d-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="99b6d-115">**Use o Lean pop-ups para Outlook na Web.**</span><span class="sxs-lookup"><span data-stu-id="99b6d-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="99b6d-116">O Lean pop-ups oferece versões menores e menos intensas de memória de determinadas mensagens de email no Microsoft Edge ou no Internet Explorer ao renderizar alguns componentes no servidor.</span><span class="sxs-lookup"><span data-stu-id="99b6d-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="99b6d-117">Para obter mais informações, consulte [use Lean pop-ups para reduzir a memória usada ao ler mensagens de email](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span><span class="sxs-lookup"><span data-stu-id="99b6d-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="99b6d-118">Conselhos gerais</span><span class="sxs-lookup"><span data-stu-id="99b6d-118">General advice</span></span>

- <span data-ttu-id="99b6d-119">Certifique-se de que a pesquisa de DNS para outlook.office.com Insira o MS-datacenter em um local de entrada lógica para seu local.</span><span class="sxs-lookup"><span data-stu-id="99b6d-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="99b6d-120">Pesquisar cache de caixa de correio e escolha as opções apropriadas (re.</span><span class="sxs-lookup"><span data-stu-id="99b6d-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="99b6d-121">período de cache, cache de caixa de correio compartilhada, et cetera).</span><span class="sxs-lookup"><span data-stu-id="99b6d-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="99b6d-122">Mantenha seus dados do Outlook passando por conexões VPN (para um escritório central) antes de passar pela Internet.</span><span class="sxs-lookup"><span data-stu-id="99b6d-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="99b6d-123">Certifique-se de que os dados da caixa de correio estão de acordo com as limitações da pasta e dos valores de item.</span><span class="sxs-lookup"><span data-stu-id="99b6d-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="99b6d-124">Para obter mais informações sobre o desempenho de migração do Exchange, confira [desempenho de migração e práticas recomendadas do Office 365](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span><span class="sxs-lookup"><span data-stu-id="99b6d-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
  
