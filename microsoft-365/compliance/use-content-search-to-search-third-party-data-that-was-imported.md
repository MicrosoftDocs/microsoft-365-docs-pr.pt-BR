---
title: Usar a pesquisa de conteúdo para pesquisar dados importados de terceiros
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Use a ferramenta de descoberta eletrônica de pesquisa de conteúdo para pesquisar itens importados para caixas de correio no Microsoft 365 de uma fonte de dados de terceiros criando consultas.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 916a780bccc3f24d509991e8ac72f31b374757d4
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819091"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="5f1e1-103">Usar a pesquisa de conteúdo para pesquisar dados de terceiros importados por um conector de parceiro personalizado</span><span class="sxs-lookup"><span data-stu-id="5f1e1-103">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="5f1e1-104">Você pode usar a [ferramenta de descoberta eletrônica de pesquisa de conteúdo](content-search.md) no centro de conformidade de & de segurança para pesquisar itens importados para caixas de correio no Microsoft 365 de uma fonte de dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="5f1e1-104">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="5f1e1-105">Você pode criar uma consulta para pesquisar todos os itens importados de dados de terceiros ou pode criar uma consulta para pesquisar itens de dados de terceiros específicos.</span><span class="sxs-lookup"><span data-stu-id="5f1e1-105">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="5f1e1-106">Além disso, você também pode criar uma política de retenção baseada em consulta ou um controle de descoberta eletrônica baseado em consulta para preservar dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="5f1e1-106">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="5f1e1-107">Para obter mais informações sobre como trabalhar com um parceiro para importar dados de terceiros e uma lista dos tipos de dados de terceiros que podem ser importados para o Microsoft 365, consulte [trabalhar com um parceiro para arquivar dados de terceiros no Office 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="5f1e1-107">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f1e1-108">As orientações deste artigo se aplicam apenas a dados de terceiros que foram importados por um conector de parceiro personalizado.</span><span class="sxs-lookup"><span data-stu-id="5f1e1-108">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="5f1e1-109">Este artigo não se aplica a dados de terceiros que são importados usando os [conectores de dados de terceiros](archiving-third-party-data.md#third-party-data-connectors) no centro de conformidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5f1e1-109">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="5f1e1-110">Criar uma consulta para pesquisar todos os dados de terceiros</span><span class="sxs-lookup"><span data-stu-id="5f1e1-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="5f1e1-111">Para pesquisar (ou colocar em espera) qualquer tipo de dados de terceiros que você importou para o Office 365, você pode usar o `kind:externaldata` par propriedade-valor de mensagem na caixa palavra-chave para uma pesquisa de conteúdo ou ao criar uma retenção baseada em consulta.</span><span class="sxs-lookup"><span data-stu-id="5f1e1-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="5f1e1-112">Por exemplo, para pesquisar itens importados de qualquer fonte de dados de terceiros e contenham a palavra "contoso" na propriedade Subject do item importado, você usaria a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="5f1e1-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="5f1e1-113">O exemplo de consulta de palavra-chave anterior inclui a propriedade Subject.</span><span class="sxs-lookup"><span data-stu-id="5f1e1-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="5f1e1-114">Para obter uma lista de outras propriedades de itens de dados de terceiros que podem incluir em uma consulta de palavra-chave, consulte a seção "mais informações" em [trabalhar com um parceiro para arquivar dados de terceiros no Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span><span class="sxs-lookup"><span data-stu-id="5f1e1-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="5f1e1-115">Ao criar consultas para pesquisar e manter dados de terceiros, você também pode usar condições para restringir os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5f1e1-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="5f1e1-116">Para obter mais informações sobre a criação de consultas de pesquisa de conteúdo, consulte [keyword queries and Search Conditions for Content Search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="5f1e1-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="5f1e1-117">Criar uma consulta para Pesquisar tipos específicos de dados de terceiros</span><span class="sxs-lookup"><span data-stu-id="5f1e1-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="5f1e1-118">Em vez de Pesquisar todos os tipos de dados de terceiros, você pode criar consultas que só pesquisem um tipo especificado de dados de terceiros usando o par seguinte propriedade de mensagem *: valor* na caixa de palavra-chave de uma pesquisa de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="5f1e1-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property:value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="5f1e1-119">Por exemplo, para pesquisar dados do Facebook que contenham a palavra "contoso" na propriedade Subject, você deve usar a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="5f1e1-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="5f1e1-120">A tabela a seguir lista os tipos de dados de terceiros que podem ser pesquisados e o valor a ser usado para a `itemclass:` Propriedade Message para pesquisar especificamente o tipo de dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="5f1e1-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="5f1e1-121">A sintaxe da consulta não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="5f1e1-121">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="5f1e1-122">**Tipo de dados de terceiros**</span><span class="sxs-lookup"><span data-stu-id="5f1e1-122">**Third-party data type**</span></span>|<span data-ttu-id="5f1e1-123">**Valor da `itemclass:` Propriedade**</span><span class="sxs-lookup"><span data-stu-id="5f1e1-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5f1e1-124">META</span><span class="sxs-lookup"><span data-stu-id="5f1e1-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="5f1e1-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="5f1e1-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="5f1e1-126">AOL with Pivot Client</span><span class="sxs-lookup"><span data-stu-id="5f1e1-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="5f1e1-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="5f1e1-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="5f1e1-128">Ares</span><span class="sxs-lookup"><span data-stu-id="5f1e1-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="5f1e1-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="5f1e1-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="5f1e1-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="5f1e1-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="5f1e1-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="5f1e1-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="5f1e1-132">Espaço reservado do AXS</span><span class="sxs-lookup"><span data-stu-id="5f1e1-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="5f1e1-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="5f1e1-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="5f1e1-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="5f1e1-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="5f1e1-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="5f1e1-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="5f1e1-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="5f1e1-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="5f1e1-137">Rim</span><span class="sxs-lookup"><span data-stu-id="5f1e1-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="5f1e1-138">Logs de chamadas do BlackBerry</span><span class="sxs-lookup"><span data-stu-id="5f1e1-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="5f1e1-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="5f1e1-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="5f1e1-140">PIN do BlackBerry</span><span class="sxs-lookup"><span data-stu-id="5f1e1-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="5f1e1-141">SMS BlackBerry</span><span class="sxs-lookup"><span data-stu-id="5f1e1-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="5f1e1-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="5f1e1-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="5f1e1-143">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="5f1e1-143">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="5f1e1-144">Mensagens do Bloomberg</span><span class="sxs-lookup"><span data-stu-id="5f1e1-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="5f1e1-145">Caixa</span><span class="sxs-lookup"><span data-stu-id="5f1e1-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="5f1e1-146">Servidor de presença de IM da Cisco &amp;</span><span class="sxs-lookup"><span data-stu-id="5f1e1-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="5f1e1-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="5f1e1-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="5f1e1-148">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="5f1e1-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="5f1e1-149">Conexão Direta</span><span class="sxs-lookup"><span data-stu-id="5f1e1-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="5f1e1-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="5f1e1-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="5f1e1-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="5f1e1-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="5f1e1-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="5f1e1-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="5f1e1-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="5f1e1-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="5f1e1-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="5f1e1-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="5f1e1-155">Google +</span><span class="sxs-lookup"><span data-stu-id="5f1e1-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="5f1e1-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="5f1e1-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="5f1e1-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="5f1e1-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="5f1e1-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="5f1e1-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="5f1e1-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="5f1e1-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="5f1e1-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="5f1e1-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="5f1e1-161">Conexões IBM</span><span class="sxs-lookup"><span data-stu-id="5f1e1-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="5f1e1-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="5f1e1-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="5f1e1-163">Chat de gelo</span><span class="sxs-lookup"><span data-stu-id="5f1e1-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="5f1e1-164">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="5f1e1-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="5f1e1-165">Instagram</span><span class="sxs-lookup"><span data-stu-id="5f1e1-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="5f1e1-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="5f1e1-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="5f1e1-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="5f1e1-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="5f1e1-168">IRC</span><span class="sxs-lookup"><span data-stu-id="5f1e1-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="5f1e1-169">Jive</span><span class="sxs-lookup"><span data-stu-id="5f1e1-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="5f1e1-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="5f1e1-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="5f1e1-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="5f1e1-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="5f1e1-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="5f1e1-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="5f1e1-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="5f1e1-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="5f1e1-174">UC da Microsoft</span><span class="sxs-lookup"><span data-stu-id="5f1e1-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="5f1e1-175">Alinhamento de mentalidade</span><span class="sxs-lookup"><span data-stu-id="5f1e1-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="5f1e1-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="5f1e1-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="5f1e1-177">MSN</span><span class="sxs-lookup"><span data-stu-id="5f1e1-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="5f1e1-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="5f1e1-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="5f1e1-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="5f1e1-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="5f1e1-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="5f1e1-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="5f1e1-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="5f1e1-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="5f1e1-182">Navegação dinâmica</span><span class="sxs-lookup"><span data-stu-id="5f1e1-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="5f1e1-183">QQ</span><span class="sxs-lookup"><span data-stu-id="5f1e1-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="5f1e1-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="5f1e1-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="5f1e1-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="5f1e1-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="5f1e1-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5f1e1-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="5f1e1-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="5f1e1-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="5f1e1-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="5f1e1-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="5f1e1-189">Squawker</span><span class="sxs-lookup"><span data-stu-id="5f1e1-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="5f1e1-190">Symphony</span><span class="sxs-lookup"><span data-stu-id="5f1e1-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="5f1e1-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="5f1e1-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="5f1e1-192">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="5f1e1-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="5f1e1-193">Tor</span><span class="sxs-lookup"><span data-stu-id="5f1e1-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="5f1e1-194">TTT</span><span class="sxs-lookup"><span data-stu-id="5f1e1-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="5f1e1-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="5f1e1-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="5f1e1-196">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="5f1e1-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="5f1e1-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="5f1e1-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="5f1e1-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="5f1e1-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="5f1e1-199">Winny</span><span class="sxs-lookup"><span data-stu-id="5f1e1-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="5f1e1-200">Toolbar</span><span class="sxs-lookup"><span data-stu-id="5f1e1-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="5f1e1-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="5f1e1-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="5f1e1-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="5f1e1-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="5f1e1-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="5f1e1-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
