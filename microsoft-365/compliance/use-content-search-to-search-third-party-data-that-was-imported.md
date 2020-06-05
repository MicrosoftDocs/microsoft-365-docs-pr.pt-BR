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
description: Use a ferramenta de descoberta eletrônica de pesquisa de conteúdo para pesquisar itens importados para caixas de correio no Microsoft 365 de uma fonte de dados de terceiros. Você pode criar uma consulta para pesquisar todos os itens importados ou criar uma consulta para Pesquisar tipos de dados específicos de terceiros. Este artigo lista os valores que podem ser usados em uma consulta de palavra-chave para pesquisar os tipos de dados de terceiros que podem ser importados para o Microsoft 365.
ms.openlocfilehash: c494f4bbb13919f9a980f227093d291c148e9afe
ms.sourcegitcommit: 86705d15231c987be2fcf5a295b9b6239fc46077
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "44566665"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="a9f3c-105">Usar a pesquisa de conteúdo para pesquisar dados de terceiros importados por um conector de parceiro personalizado</span><span class="sxs-lookup"><span data-stu-id="a9f3c-105">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="a9f3c-106">Você pode usar a [ferramenta de descoberta eletrônica de pesquisa de conteúdo](content-search.md) no centro de conformidade de & de segurança para pesquisar itens importados para caixas de correio no Microsoft 365 de uma fonte de dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-106">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="a9f3c-107">Você pode criar uma consulta para pesquisar todos os itens importados de dados de terceiros ou pode criar uma consulta para pesquisar itens de dados de terceiros específicos.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-107">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="a9f3c-108">Além disso, você também pode criar uma política de retenção baseada em consulta ou um controle de descoberta eletrônica baseado em consulta para preservar dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-108">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="a9f3c-109">Para obter mais informações sobre como trabalhar com um parceiro para importar dados de terceiros e uma lista dos tipos de dados de terceiros que podem ser importados para o Microsoft 365, consulte [trabalhar com um parceiro para arquivar dados de terceiros no Office 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="a9f3c-109">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9f3c-110">As orientações deste artigo se aplicam apenas a dados de terceiros que foram importados por um conector de parceiro personalizado.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-110">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="a9f3c-111">Este artigo não se aplica a dados de terceiros que são importados usando os [conectores de dados de terceiros](archiving-third-party-data.md#third-party-data-connectors) no centro de conformidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-111">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="a9f3c-112">Criar uma consulta para pesquisar todos os dados de terceiros</span><span class="sxs-lookup"><span data-stu-id="a9f3c-112">Creating a query to search all third-party data</span></span>

<span data-ttu-id="a9f3c-113">Para pesquisar (ou colocar em espera) qualquer tipo de dados de terceiros que você importou para o Office 365, você pode usar o `kind:externaldata` par propriedade-valor de mensagem na caixa palavra-chave para uma pesquisa de conteúdo ou ao criar uma retenção baseada em consulta.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-113">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="a9f3c-114">Por exemplo, para pesquisar itens importados de qualquer fonte de dados de terceiros e contenham a palavra "contoso" na propriedade Subject do item importado, você usaria a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="a9f3c-114">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="a9f3c-115">O exemplo de consulta de palavra-chave anterior inclui a propriedade Subject.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-115">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="a9f3c-116">Para obter uma lista de outras propriedades de itens de dados de terceiros que podem incluir em uma consulta de palavra-chave, consulte a seção "mais informações" em [trabalhar com um parceiro para arquivar dados de terceiros no Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span><span class="sxs-lookup"><span data-stu-id="a9f3c-116">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="a9f3c-117">Ao criar consultas para pesquisar e manter dados de terceiros, você também pode usar condições para restringir os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-117">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="a9f3c-118">Para obter mais informações sobre a criação de consultas de pesquisa de conteúdo, consulte [keyword queries and Search Conditions for Content Search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="a9f3c-118">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="a9f3c-119">Criar uma consulta para Pesquisar tipos específicos de dados de terceiros</span><span class="sxs-lookup"><span data-stu-id="a9f3c-119">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="a9f3c-120">Em vez de Pesquisar todos os tipos de dados de terceiros, você pode criar consultas que só pesquisem um tipo especificado de dados de terceiros usando o par seguinte propriedade de mensagem *: valor* na caixa de palavra-chave de uma pesquisa de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="a9f3c-120">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property:value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="a9f3c-121">Por exemplo, para pesquisar dados do Facebook que contenham a palavra "contoso" na propriedade Subject, você deve usar a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="a9f3c-121">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="a9f3c-122">A tabela a seguir lista os tipos de dados de terceiros que podem ser pesquisados e o valor a ser usado para a `itemclass:` Propriedade Message para pesquisar especificamente o tipo de dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-122">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="a9f3c-123">A sintaxe da consulta não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a9f3c-123">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="a9f3c-124">**Tipo de dados de terceiros**</span><span class="sxs-lookup"><span data-stu-id="a9f3c-124">**Third-party data type**</span></span>|<span data-ttu-id="a9f3c-125">**Valor da `itemclass:` Propriedade**</span><span class="sxs-lookup"><span data-stu-id="a9f3c-125">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a9f3c-126">META</span><span class="sxs-lookup"><span data-stu-id="a9f3c-126">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="a9f3c-127">American Idol</span><span class="sxs-lookup"><span data-stu-id="a9f3c-127">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="a9f3c-128">AOL with Pivot Client</span><span class="sxs-lookup"><span data-stu-id="a9f3c-128">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="a9f3c-129">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="a9f3c-129">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="a9f3c-130">Ares</span><span class="sxs-lookup"><span data-stu-id="a9f3c-130">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="a9f3c-131">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="a9f3c-131">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="a9f3c-132">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="a9f3c-132">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="a9f3c-133">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="a9f3c-133">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="a9f3c-134">Espaço reservado do AXS</span><span class="sxs-lookup"><span data-stu-id="a9f3c-134">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="a9f3c-135">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="a9f3c-135">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="a9f3c-136">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="a9f3c-136">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="a9f3c-137">Bearshare</span><span class="sxs-lookup"><span data-stu-id="a9f3c-137">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="a9f3c-138">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="a9f3c-138">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="a9f3c-139">Rim</span><span class="sxs-lookup"><span data-stu-id="a9f3c-139">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="a9f3c-140">Logs de chamadas do BlackBerry</span><span class="sxs-lookup"><span data-stu-id="a9f3c-140">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="a9f3c-141">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="a9f3c-141">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="a9f3c-142">PIN do BlackBerry</span><span class="sxs-lookup"><span data-stu-id="a9f3c-142">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="a9f3c-143">SMS BlackBerry</span><span class="sxs-lookup"><span data-stu-id="a9f3c-143">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="a9f3c-144">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a9f3c-144">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="a9f3c-145">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="a9f3c-145">Bloomberg Mail</span></span>  <br/> | `ipm.externaldata.BloombergMail*` <br/> |
|<span data-ttu-id="a9f3c-146">Mensagens do Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a9f3c-146">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="a9f3c-147">Caixa</span><span class="sxs-lookup"><span data-stu-id="a9f3c-147">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="a9f3c-148">Servidor de presença de IM da Cisco &amp;</span><span class="sxs-lookup"><span data-stu-id="a9f3c-148">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="a9f3c-149">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="a9f3c-149">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="a9f3c-150">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="a9f3c-150">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="a9f3c-151">Conexão Direta</span><span class="sxs-lookup"><span data-stu-id="a9f3c-151">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="a9f3c-152">Facebook</span><span class="sxs-lookup"><span data-stu-id="a9f3c-152">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="a9f3c-153">FastTrack</span><span class="sxs-lookup"><span data-stu-id="a9f3c-153">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="a9f3c-154">FXConnect</span><span class="sxs-lookup"><span data-stu-id="a9f3c-154">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="a9f3c-155">Flickr</span><span class="sxs-lookup"><span data-stu-id="a9f3c-155">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="a9f3c-156">Gnutella</span><span class="sxs-lookup"><span data-stu-id="a9f3c-156">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="a9f3c-157">Google +</span><span class="sxs-lookup"><span data-stu-id="a9f3c-157">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="a9f3c-158">Google Talk</span><span class="sxs-lookup"><span data-stu-id="a9f3c-158">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="a9f3c-159">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="a9f3c-159">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="a9f3c-160">HipChat</span><span class="sxs-lookup"><span data-stu-id="a9f3c-160">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="a9f3c-161">Hopster</span><span class="sxs-lookup"><span data-stu-id="a9f3c-161">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="a9f3c-162">HubConnex</span><span class="sxs-lookup"><span data-stu-id="a9f3c-162">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="a9f3c-163">Conexões IBM</span><span class="sxs-lookup"><span data-stu-id="a9f3c-163">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="a9f3c-164">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="a9f3c-164">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="a9f3c-165">Chat de gelo</span><span class="sxs-lookup"><span data-stu-id="a9f3c-165">ICE Chat</span></span>  <br/> | `ipm.externaldata.ICEChat.Chat` <br/> |
|<span data-ttu-id="a9f3c-166">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="a9f3c-166">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="a9f3c-167">Instagram</span><span class="sxs-lookup"><span data-stu-id="a9f3c-167">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="a9f3c-168">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="a9f3c-168">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="a9f3c-169">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="a9f3c-169">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="a9f3c-170">IRC</span><span class="sxs-lookup"><span data-stu-id="a9f3c-170">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="a9f3c-171">Jive</span><span class="sxs-lookup"><span data-stu-id="a9f3c-171">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="a9f3c-172">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="a9f3c-172">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="a9f3c-173">JXTA</span><span class="sxs-lookup"><span data-stu-id="a9f3c-173">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="a9f3c-174">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="a9f3c-174">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="a9f3c-175">MFTP</span><span class="sxs-lookup"><span data-stu-id="a9f3c-175">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="a9f3c-176">UC da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a9f3c-176">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="a9f3c-177">Alinhamento de mentalidade</span><span class="sxs-lookup"><span data-stu-id="a9f3c-177">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="a9f3c-178">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="a9f3c-178">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="a9f3c-179">MSN</span><span class="sxs-lookup"><span data-stu-id="a9f3c-179">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="a9f3c-180">MySpace</span><span class="sxs-lookup"><span data-stu-id="a9f3c-180">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="a9f3c-181">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="a9f3c-181">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="a9f3c-182">OpenNap</span><span class="sxs-lookup"><span data-stu-id="a9f3c-182">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="a9f3c-183">Pinterest</span><span class="sxs-lookup"><span data-stu-id="a9f3c-183">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="a9f3c-184">Navegação dinâmica</span><span class="sxs-lookup"><span data-stu-id="a9f3c-184">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="a9f3c-185">QQ</span><span class="sxs-lookup"><span data-stu-id="a9f3c-185">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="a9f3c-186">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="a9f3c-186">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="a9f3c-187">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="a9f3c-187">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="a9f3c-188">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a9f3c-188">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="a9f3c-189">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="a9f3c-189">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="a9f3c-190">SoftEther</span><span class="sxs-lookup"><span data-stu-id="a9f3c-190">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="a9f3c-191">Squawker</span><span class="sxs-lookup"><span data-stu-id="a9f3c-191">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="a9f3c-192">Symphony</span><span class="sxs-lookup"><span data-stu-id="a9f3c-192">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="a9f3c-193">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="a9f3c-193">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="a9f3c-194">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="a9f3c-194">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="a9f3c-195">Tor</span><span class="sxs-lookup"><span data-stu-id="a9f3c-195">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="a9f3c-196">TTT</span><span class="sxs-lookup"><span data-stu-id="a9f3c-196">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="a9f3c-197">Twitter</span><span class="sxs-lookup"><span data-stu-id="a9f3c-197">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="a9f3c-198">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="a9f3c-198">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="a9f3c-199">Vimeo</span><span class="sxs-lookup"><span data-stu-id="a9f3c-199">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="a9f3c-200">WinMX</span><span class="sxs-lookup"><span data-stu-id="a9f3c-200">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="a9f3c-201">Winny</span><span class="sxs-lookup"><span data-stu-id="a9f3c-201">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="a9f3c-202">Toolbar</span><span class="sxs-lookup"><span data-stu-id="a9f3c-202">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="a9f3c-203">Yammer</span><span class="sxs-lookup"><span data-stu-id="a9f3c-203">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="a9f3c-204">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="a9f3c-204">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="a9f3c-205">YouTube</span><span class="sxs-lookup"><span data-stu-id="a9f3c-205">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
