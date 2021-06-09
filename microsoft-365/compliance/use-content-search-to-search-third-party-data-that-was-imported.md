---
title: Usar a Pesquisa de Conteúdo para pesquisar dados importados de terceiros
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
description: Use a ferramenta Descoberta Eletrônico de Pesquisa de Conteúdo para pesquisar itens importados para caixas de correio em Microsoft 365 de uma fonte de dados de terceiros criando consultas.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324567"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="21f68-103">Usar a Pesquisa de Conteúdo para pesquisar dados de terceiros importados por um conector de parceiro personalizado</span><span class="sxs-lookup"><span data-stu-id="21f68-103">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="21f68-104">Você pode usar a ferramenta Descoberta [eDiscover & y](content-search.md) de Pesquisa de Conteúdo no Centro de Conformidade e Segurança para pesquisar itens importados para caixas de correio em Microsoft 365 de uma fonte de dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="21f68-104">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="21f68-105">Você pode criar uma consulta para pesquisar todos os itens de dados de terceiros importados ou criar uma consulta para pesquisar itens de dados de terceiros específicos.</span><span class="sxs-lookup"><span data-stu-id="21f68-105">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="21f68-106">Além disso, você também pode criar uma política de retenção baseada em consulta ou uma retenção de Descoberta eDiscovery baseada em consulta para preservar dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="21f68-106">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="21f68-107">Para obter mais informações sobre como trabalhar com um parceiro para importar dados de terceiros e uma lista dos tipos de dados de terceiros que você pode importar para o Microsoft 365, consulte Trabalhar com um parceiro para arquivar dados de terceiros em [Office 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="21f68-107">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21f68-108">As diretrizes neste artigo se aplica apenas a dados de terceiros que foram importados por um conector de parceiro personalizado.</span><span class="sxs-lookup"><span data-stu-id="21f68-108">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="21f68-109">Este artigo não se aplica a dados de terceiros que são [importados](archiving-third-party-data.md#third-party-data-connectors) usando os conectores de dados de terceiros no centro de conformidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="21f68-109">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="21f68-110">Criando uma consulta para pesquisar todos os dados de terceiros</span><span class="sxs-lookup"><span data-stu-id="21f68-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="21f68-111">Para pesquisar (ou colocar em espera) qualquer tipo de dados de terceiros que você importou para o Office 365, você pode usar o par de valores de propriedade da mensagem na caixa de palavra-chave para uma Pesquisa de Conteúdo ou ao criar uma espera baseada em `kind:externaldata` consulta.</span><span class="sxs-lookup"><span data-stu-id="21f68-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="21f68-112">Por exemplo, para pesquisar itens importados de qualquer fonte de dados de terceiros e conter a palavra "contoso" na propriedade Subject do item importado, você usaria a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="21f68-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="21f68-113">O exemplo de consulta de palavra-chave anterior inclui a propriedade subject.</span><span class="sxs-lookup"><span data-stu-id="21f68-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="21f68-114">Para obter uma lista de outras propriedades para itens de dados de terceiros que podem incluir em uma consulta de [palavra-chave,](work-with-partner-to-archive-third-party-data.md#more-information)consulte a seção "Mais informações" em Trabalhar com um parceiro para arquivar dados de terceiros em Office 365 .</span><span class="sxs-lookup"><span data-stu-id="21f68-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="21f68-115">Ao criar consultas para pesquisar e manter dados de terceiros, você também pode usar condições para restringir os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="21f68-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="21f68-116">Para obter mais informações sobre como criar consultas de Pesquisa de Conteúdo, consulte Consultas de palavra-chave [e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="21f68-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="21f68-117">Criando uma consulta para pesquisar tipos específicos de dados de terceiros</span><span class="sxs-lookup"><span data-stu-id="21f68-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="21f68-118">Em vez de pesquisar todos os tipos de dados de terceiros, você pode criar consultas que pesquisem apenas um tipo de especificação de dados de terceiros usando a seguinte propriedade de *mensagem:* par de valores na caixa de palavra-chave para uma Pesquisa de Conteúdo:</span><span class="sxs-lookup"><span data-stu-id="21f68-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property: value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="21f68-119">Por exemplo, para pesquisar dados do Facebook que contenham a palavra "contoso" na propriedade Subject, você usaria a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="21f68-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="21f68-120">A tabela a seguir lista os tipos de dados de terceiros que você pode pesquisar e o valor a ser usado para a propriedade de mensagem para pesquisar especificamente esse tipo de dados  `itemclass:` de terceiros.</span><span class="sxs-lookup"><span data-stu-id="21f68-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="21f68-121">A sintaxe de consulta não é sensível a casos.</span><span class="sxs-lookup"><span data-stu-id="21f68-121">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="21f68-122">**Tipo de dados de terceiros**</span><span class="sxs-lookup"><span data-stu-id="21f68-122">**Third-party data type**</span></span>|<span data-ttu-id="21f68-123">**Valor da  `itemclass:` propriedade**</span><span class="sxs-lookup"><span data-stu-id="21f68-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="21f68-124">AIM</span><span class="sxs-lookup"><span data-stu-id="21f68-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="21f68-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="21f68-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="21f68-126">AOL with Pivot Client</span><span class="sxs-lookup"><span data-stu-id="21f68-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="21f68-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="21f68-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="21f68-128">Ares</span><span class="sxs-lookup"><span data-stu-id="21f68-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="21f68-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="21f68-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="21f68-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="21f68-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="21f68-131">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="21f68-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="21f68-132">Espaço reservado Axs</span><span class="sxs-lookup"><span data-stu-id="21f68-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="21f68-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="21f68-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="21f68-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="21f68-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="21f68-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="21f68-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="21f68-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="21f68-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="21f68-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="21f68-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="21f68-138">Logs de chamadas blackberry</span><span class="sxs-lookup"><span data-stu-id="21f68-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="21f68-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="21f68-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="21f68-140">BlackBerry PIN</span><span class="sxs-lookup"><span data-stu-id="21f68-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="21f68-141">BlackBerry SMS</span><span class="sxs-lookup"><span data-stu-id="21f68-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="21f68-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="21f68-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="21f68-143">Mensagem da Bloomberg</span><span class="sxs-lookup"><span data-stu-id="21f68-143">Bloomberg Message</span></span>  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|<span data-ttu-id="21f68-144">Mensagens da Bloomberg</span><span class="sxs-lookup"><span data-stu-id="21f68-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="21f68-145">Box</span><span class="sxs-lookup"><span data-stu-id="21f68-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="21f68-146">Cisco IM &amp; Presence Server</span><span class="sxs-lookup"><span data-stu-id="21f68-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="21f68-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="21f68-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="21f68-148">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="21f68-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="21f68-149">Conexão Direta</span><span class="sxs-lookup"><span data-stu-id="21f68-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="21f68-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="21f68-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="21f68-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="21f68-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="21f68-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="21f68-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="21f68-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="21f68-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="21f68-154">Gnutella</span><span class="sxs-lookup"><span data-stu-id="21f68-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="21f68-155">Google+</span><span class="sxs-lookup"><span data-stu-id="21f68-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="21f68-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="21f68-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="21f68-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="21f68-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="21f68-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="21f68-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="21f68-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="21f68-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="21f68-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="21f68-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="21f68-161">Conexões IBM</span><span class="sxs-lookup"><span data-stu-id="21f68-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="21f68-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="21f68-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="21f68-163">Bate-papo ICE</span><span class="sxs-lookup"><span data-stu-id="21f68-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|<span data-ttu-id="21f68-164">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="21f68-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="21f68-165">Instagram</span><span class="sxs-lookup"><span data-stu-id="21f68-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="21f68-166">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="21f68-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="21f68-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="21f68-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="21f68-168">IRC</span><span class="sxs-lookup"><span data-stu-id="21f68-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="21f68-169">Jive</span><span class="sxs-lookup"><span data-stu-id="21f68-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="21f68-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="21f68-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="21f68-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="21f68-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="21f68-172">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="21f68-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="21f68-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="21f68-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="21f68-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="21f68-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="21f68-175">Alinhar a mente</span><span class="sxs-lookup"><span data-stu-id="21f68-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="21f68-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="21f68-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="21f68-177">MSN</span><span class="sxs-lookup"><span data-stu-id="21f68-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="21f68-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="21f68-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="21f68-179">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="21f68-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="21f68-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="21f68-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="21f68-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="21f68-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="21f68-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="21f68-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="21f68-183">QQ</span><span class="sxs-lookup"><span data-stu-id="21f68-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="21f68-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="21f68-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="21f68-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="21f68-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="21f68-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="21f68-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="21f68-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="21f68-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="21f68-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="21f68-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="21f68-189">Adúlker</span><span class="sxs-lookup"><span data-stu-id="21f68-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="21f68-190">Symphony</span><span class="sxs-lookup"><span data-stu-id="21f68-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="21f68-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="21f68-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="21f68-192">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="21f68-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="21f68-193">Tor</span><span class="sxs-lookup"><span data-stu-id="21f68-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="21f68-194">TTT</span><span class="sxs-lookup"><span data-stu-id="21f68-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="21f68-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="21f68-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="21f68-196">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="21f68-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="21f68-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="21f68-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="21f68-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="21f68-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="21f68-199">Winny</span><span class="sxs-lookup"><span data-stu-id="21f68-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="21f68-200">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="21f68-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="21f68-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="21f68-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="21f68-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="21f68-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="21f68-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="21f68-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
