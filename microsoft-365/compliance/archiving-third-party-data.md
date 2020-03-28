---
title: Arquivar dados de terceiros
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: Os administradores podem importar dados de terceiros de plataformas de mídia social, plataformas de mensagens instantâneas e plataformas de colaboração de documentos para caixas de correio em sua organização do Microsoft 365. Isso permite que você arquive dados do Facebook, do Twitter e de outras fontes de dados de terceiros no Microsoft 365. Em seguida, você pode usar e aplicar recursos de conformidade do Microsoft 365 (como retenção legal, eDiscovery, arquivamento in-loco e políticas de retenção) para dados de terceiros.
ms.openlocfilehash: 72afb48f74a30bac2904e857a33487a83eba48cd
ms.sourcegitcommit: f9b5eca20e025acc36635cbd1786ff3407295857
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2020
ms.locfileid: "43027651"
---
# <a name="archive-third-party-data"></a><span data-ttu-id="4edc4-105">Arquivar dados de terceiros</span><span class="sxs-lookup"><span data-stu-id="4edc4-105">Archive third-party data</span></span>

<span data-ttu-id="4edc4-106">A Microsoft 365 permite que os administradores importem e arquivem dados de terceiros de plataformas de mídia social, plataformas de mensagens instantâneas e plataformas de colaboração de documentos, para caixas de correio em sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4edc4-106">Microsoft 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="4edc4-107">Exemplos de fontes de dados de terceiros que podem ser importadas para o Microsoft 365 incluem os seguintes serviços:</span><span class="sxs-lookup"><span data-stu-id="4edc4-107">Examples of third-party data sources that you can import to Microsoft 365 include the following services:</span></span> 
  
- <span data-ttu-id="4edc4-108">**Social:** Facebook, LinkedIn, Twitter e Yammer</span><span class="sxs-lookup"><span data-stu-id="4edc4-108">**Social:** Facebook, LinkedIn, Twitter, and Yammer</span></span>

- <span data-ttu-id="4edc4-109">**Mensagens instantâneas:** Yahoo Messenger e GoogleTalk</span><span class="sxs-lookup"><span data-stu-id="4edc4-109">**Instant messaging:** Yahoo Messenger and GoogleTalk</span></span>

- <span data-ttu-id="4edc4-110">**Colaboração de documentos:** Caixa e DropBox</span><span class="sxs-lookup"><span data-stu-id="4edc4-110">**Document collaboration:** Box and DropBox</span></span>

- <span data-ttu-id="4edc4-111">**Setores verticais:** Gerenciamento de relacionamento com o cliente (como o Salesforce e os serviços financeiros (como Bloomberg e Thomson Reuters)</span><span class="sxs-lookup"><span data-stu-id="4edc4-111">**Vertical industries:** Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span>

- <span data-ttu-id="4edc4-112">**SMS/mensagens de texto:** Rim</span><span class="sxs-lookup"><span data-stu-id="4edc4-112">**SMS/text messaging:** BlackBerry</span></span>

<span data-ttu-id="4edc4-113">Após a importação dos dados de terceiros, é possível aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, eDiscovery, arquivamento in-loco, auditoria, conformidade de comunicação e políticas de retenção a esses dados.</span><span class="sxs-lookup"><span data-stu-id="4edc4-113">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Communication compliance, and retention policies to this data.</span></span> <span data-ttu-id="4edc4-114">Por exemplo, quando uma caixa de correio é colocada em retenção de litígio, os dados de terceiros são preservados.</span><span class="sxs-lookup"><span data-stu-id="4edc4-114">For example, when a mailbox is placed on Litigation Hold, third-party data is preserved.</span></span> <span data-ttu-id="4edc4-115">Você pode pesquisar dados de terceiros usando as ferramentas de descoberta eletrônica da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4edc4-115">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="4edc4-116">Ou você pode aplicar políticas de arquivamento e retenção a dados de terceiros, da mesma forma que você pode para os dados da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4edc4-116">Or you can apply archiving and retention policies to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="4edc4-117">Em suma, o arquivamento de dados de terceiros no Microsoft 365 pode ajudar sua organização a se manter em conformidade com as políticas governamentais e regulamentares.</span><span class="sxs-lookup"><span data-stu-id="4edc4-117">In short, archiving third-party data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="4edc4-118">Há duas maneiras de importar e arquivar dados de terceiros no Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="4edc4-118">There are two ways to import and archive third-party data in Microsoft 365:</span></span>

- <span data-ttu-id="4edc4-119">**Use um conector de dados de terceiros no centro de conformidade de & de segurança:** Use um conector de dados personalizado que está disponível no centro de conformidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4edc4-119">**Use a third-party data connector in the Security & Compliance Center:** Use a custom data connector that's available in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4edc4-120">Após configurar e configurar o conector, ele se conecta à fonte de dados de terceiros, converte o conteúdo de um item em um formato de mensagem de email e, em seguida, importa o item para uma caixa de correio no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4edc4-120">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="4edc4-121">No momento, você pode implementar conectores para importar e arquivar dados de páginas de negócios do Facebook, contas do Twitter corporativos, LinkedIn, Bloomberg do Instant e dados de recursos humanos da sua organização (RH).</span><span class="sxs-lookup"><span data-stu-id="4edc4-121">Currently, you can implement connectors to import and archive data from Facebook Business pages, corporate Twitter accounts, LinkedIn, Instant Bloomberg, and your organization's human resources (HR) data.</span></span> <span data-ttu-id="4edc4-122">Para obter instruções passo a passo para configurar um desses conectores, consulte:</span><span class="sxs-lookup"><span data-stu-id="4edc4-122">For the step-by-step instructions to set up one of these connectors, see:</span></span>

   - <span data-ttu-id="4edc4-123">**Facebook:** [usar um conector para arquivar dados do Facebook](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="4edc4-123">**Facebook:** [Use a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="4edc4-124">**Twitter:** [usar um conector para arquivar dados do Twitter](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="4edc4-124">**Twitter:** [Use a connector to archive Twitter data](archive-twitter-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="4edc4-125">**LinkedIn:** [configurar um conector para arquivar dados do LinkedIn](archive-linkedin-data.md)</span><span class="sxs-lookup"><span data-stu-id="4edc4-125">**LinkedIn:** [Set up a connector to archive LinkedIn data](archive-linkedin-data.md)</span></span>

   - <span data-ttu-id="4edc4-126">**Bloomberg instantâneo:** [configurar um conector para arquivar dados instantâneos do Bloomberg](archive-instant-bloomberg-data.md)</span><span class="sxs-lookup"><span data-stu-id="4edc4-126">**Instant Bloomberg:** [Set up a connector to archive Instant Bloomberg data](archive-instant-bloomberg-data.md)</span></span>

   - <span data-ttu-id="4edc4-127">**Dados de RH:** [configurar um conector para importar dados de RH](import-hr-data.md)</span><span class="sxs-lookup"><span data-stu-id="4edc4-127">**HR data:** [Set up a connector to import HR data](import-hr-data.md)</span></span>

- <span data-ttu-id="4edc4-128">**Trabalhar com um parceiro da Microsoft:** Sua organização trabalha com um parceiro da Microsoft que fornecerá um conector personalizado que será configurado para extrair itens da fonte de dados de terceiros regularmente e, em seguida, se conectar à nuvem da Microsoft por uma API de terceiros e importá-los para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4edc4-128">**Work with a Microsoft partner:** Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source on a regular basis and then connect to the Microsoft cloud by a third-party API and import those items to Microsoft 365.</span></span> <span data-ttu-id="4edc4-129">O conector de parceiro também converte o conteúdo de um item da fonte de dados de terceiros em uma mensagem de email e, em seguida, importa-o para uma caixa de correio no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4edc4-129">The partner connector also converts the content of an item from the third-party data source to an email message and then imports it to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="4edc4-130">Para obter uma lista de parceiros com os quais você pode trabalhar e o processo passo a passo desse método, confira [trabalhar com um parceiro para arquivar dados de terceiros no Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="4edc4-130">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span></span>
