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
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a>Usar a Pesquisa de Conteúdo para pesquisar dados de terceiros importados por um conector de parceiro personalizado

Você pode usar a ferramenta Descoberta [eDiscover & y](content-search.md) de Pesquisa de Conteúdo no Centro de Conformidade e Segurança para pesquisar itens importados para caixas de correio em Microsoft 365 de uma fonte de dados de terceiros. Você pode criar uma consulta para pesquisar todos os itens de dados de terceiros importados ou criar uma consulta para pesquisar itens de dados de terceiros específicos. Além disso, você também pode criar uma política de retenção baseada em consulta ou uma retenção de Descoberta eDiscovery baseada em consulta para preservar dados de terceiros.
  
Para obter mais informações sobre como trabalhar com um parceiro para importar dados de terceiros e uma lista dos tipos de dados de terceiros que você pode importar para o Microsoft 365, consulte Trabalhar com um parceiro para arquivar dados de terceiros em [Office 365](work-with-partner-to-archive-third-party-data.md).

> [!IMPORTANT]
> As diretrizes neste artigo se aplica apenas a dados de terceiros que foram importados por um conector de parceiro personalizado. Este artigo não se aplica a dados de terceiros que são [importados](archiving-third-party-data.md#third-party-data-connectors) usando os conectores de dados de terceiros no centro de conformidade da Microsoft.
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>Criando uma consulta para pesquisar todos os dados de terceiros

Para pesquisar (ou colocar em espera) qualquer tipo de dados de terceiros que você importou para o Office 365, você pode usar o par de valores de propriedade da mensagem na caixa de palavra-chave para uma Pesquisa de Conteúdo ou ao criar uma espera baseada em `kind:externaldata` consulta. Por exemplo, para pesquisar itens importados de qualquer fonte de dados de terceiros e conter a palavra "contoso" na propriedade Subject do item importado, você usaria a seguinte consulta: 
  
```powershell
kind:externaldata AND subject:contoso
```

O exemplo de consulta de palavra-chave anterior inclui a propriedade subject. Para obter uma lista de outras propriedades para itens de dados de terceiros que podem incluir em uma consulta de [palavra-chave,](work-with-partner-to-archive-third-party-data.md#more-information)consulte a seção "Mais informações" em Trabalhar com um parceiro para arquivar dados de terceiros em Office 365 .
  
Ao criar consultas para pesquisar e manter dados de terceiros, você também pode usar condições para restringir os resultados da pesquisa. Para obter mais informações sobre como criar consultas de Pesquisa de Conteúdo, consulte Consultas de palavra-chave [e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md).
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>Criando uma consulta para pesquisar tipos específicos de dados de terceiros

Em vez de pesquisar todos os tipos de dados de terceiros, você pode criar consultas que pesquisem apenas um tipo de especificação de dados de terceiros usando a seguinte propriedade de *mensagem:* par de valores na caixa de palavra-chave para uma Pesquisa de Conteúdo:
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

Por exemplo, para pesquisar dados do Facebook que contenham a palavra "contoso" na propriedade Subject, você usaria a seguinte consulta:
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

A tabela a seguir lista os tipos de dados de terceiros que você pode pesquisar e o valor a ser usado para a propriedade de mensagem para pesquisar especificamente esse tipo de dados  `itemclass:` de terceiros. A sintaxe de consulta não é sensível a casos. 
  
|**Tipo de dados de terceiros**|**Valor da  `itemclass:` propriedade**|
|:-----|:-----|
|AIM  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Idol  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL with Pivot Client  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Espaço reservado Axs  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs Signed  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Bazaarvoice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|BitTorrent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|Blackberry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|Logs de chamadas blackberry  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry PIN  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Mensagem da Bloomberg  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|Mensagens da Bloomberg  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Box  <br/> | `ipm.externaldata.Box*` <br/> |
|Cisco IM &amp; Presence Server  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud for Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Conexão Direta  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Gnutella  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google+  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hopster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|Conexões IBM  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|Bate-papo ICE  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|Indii Messenger  <br/> | `ipm.externaldata.Indii*` <br/> |
|Instagram  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|Alinhar a mente  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|MSN  <br/> | `ipm.externaldata.MSN*` <br/> |
|MySpace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|Pivot  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|Skype for Business  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack Enterprise Grid  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|Adúlker  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS Chat  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|YellowJacket  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
