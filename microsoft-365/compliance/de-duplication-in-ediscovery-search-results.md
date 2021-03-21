---
title: Deduplicação nos resultados de pesquisa de Descoberta Eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
ms.custom:
- seo-marvel-apr2020
description: Saiba como eliminar resultados de pesquisa de Descoberta Eletrônico duplicados para que apenas uma cópia de uma mensagem de email seja exportada.
ms.openlocfilehash: 859c1c41a9f6a530cdefce5220039fbc6ba1a14e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925667"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>Deduplicação nos resultados de pesquisa de Descoberta Eletrônica

Este artigo descreve como funciona a des duplicação dos resultados da pesquisa de Descoberta EDiscovery e explica as limitações do algoritmo de des duplicação.
  
Ao usar ferramentas de Descoberta Online para exportar os resultados de uma pesquisa de Descoberta Online, você tem a opção de des duplicar os resultados exportados. Cenário Quando você habilita a des duplicação (por padrão, a de duplicação não está habilitada), apenas uma cópia de uma mensagem de email é exportada, mesmo que várias instâncias da mesma mensagem possam ter sido encontradas nas caixas de correio que foram pesquisadas. A des duplicação ajuda você a economizar tempo reduzindo o número de itens que você precisa revisar e analisar depois que os resultados da pesquisa são exportados. Mas é importante entender como a duplicação funciona e estar ciente de que há limitações para o algoritmo que podem fazer com que um item exclusivo seja marcado como uma duplicata durante o processo de exportação.
  
## <a name="how-duplicate-messages-are-identified"></a>Como as mensagens duplicadas são identificadas

As ferramentas de Descoberta Eletrônico usam uma combinação das seguintes propriedades de email para determinar se uma mensagem é uma duplicata:
  
- **InternetMessageId** - Essa propriedade especifica o identificador de mensagem de Internet de uma mensagem de email, que é um identificador global exclusivo que se refere a uma versão específica de uma mensagem específica. Essa ID é gerada pelo programa de cliente de email do remetente ou pelo sistema de email host que envia a mensagem. Se uma pessoa enviar uma mensagem para mais de um destinatário, a ID da mensagem da Internet será a mesma para cada instância da mensagem. As revisões subsequentes à mensagem original receberão um identificador de mensagem diferente. 

- **ConversationTopic** - Essa propriedade especifica o assunto do thread de conversa de uma mensagem. O valor da **propriedade ConversationTopic** é a cadeia de caracteres que descreve o tópico geral da conversa. Uma conservação consiste em uma mensagem inicial e todas as mensagens enviadas em resposta à mensagem inicial. As mensagens na mesma conversa têm o mesmo valor para a **propriedade ConversationTopic.** O valor dessa propriedade normalmente é a linha Subject da mensagem inicial que gerou a conversa. 

- **BodyTagInfo** - Essa é uma propriedade interna do Exchange Store. O valor dessa propriedade é calculado verificando vários atributos no corpo da mensagem. Essa propriedade é usada para identificar diferenças no corpo das mensagens. 

Durante o processo de exportação da Descoberta EDiscovery, essas três propriedades são comparadas para cada mensagem que corresponde aos critérios de pesquisa. Se essas propriedades são idênticas para duas (ou mais) mensagens, essas mensagens são determinadas como duplicatas e o resultado é que apenas uma cópia da mensagem será exportada se a des duplicação estiver habilitada. A mensagem exportada é conhecida como "item de origem". As informações sobre mensagens duplicadas são incluídas nos relatórios **Results.csv** e **Manifest.xml** que estão incluídos nos resultados da pesquisa exportada. No arquivo **Results.csv,** uma mensagem duplicada é identificada por ter um valor na coluna **Duplicar para Item.** O valor nesta coluna corresponde ao valor na coluna **Identidade do Item** da mensagem que foi exportada. 
  
Os gráficos a seguir mostram como  as mensagens duplicadas são exibidas nos relatóriosResults.csve **Manifest.xml** que são exportadas com os resultados da pesquisa. Esses relatórios não incluem as propriedades de email descritas anteriormente, que são usadas no algoritmo de des duplicação. Em vez disso, os relatórios **incluem** a propriedade Identidade do Item atribuída a itens pelo armazenamento do Exchange. 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>Results.csv relatório (exibido no Excel)
  
![Exibindo informações sobre itens duplicados no Results.csv relatório](../media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Manifest.xml relatório (exibido no Excel)
  
![Exibindo informações sobre itens duplicados no Manifest.xml relatório](../media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
Além disso, outras propriedades de mensagens duplicadas são incluídas nos relatórios de exportação. Isso inclui a caixa de correio em que a mensagem duplicada está localizada, se a mensagem foi enviada a um grupo de distribuição e se a mensagem foi Cc'd ou Bcc'd para outro usuário.
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>Limitações do algoritmo de des duplicação

Existem algumas limitações conhecidas do algoritmo de des duplicação que podem fazer com que itens exclusivos sejam marcados como duplicatas. É importante entender essas limitações para que você possa decidir se deve ou não usar o recurso opcional de des duplicação.
  
Há uma situação em que o recurso de des duplicação pode identificar erroneamente uma mensagem como uma duplicata e não exportá-la (mas ainda cite-a como uma duplicata nos relatórios de exportação). São mensagens que um usuário edita, mas não envia. Por exemplo, digamos que um usuário selecione uma mensagem no Outlook, copie o conteúdo da mensagem e, em seguida, a colará em uma nova mensagem. Em seguida, o usuário altera uma das cópias removendo ou adicionando um anexo ou alterando a linha de assunto ou o próprio corpo. Se essas duas mensagens corresponderem à consulta de uma pesquisa de Descoberta eDiscovery, apenas uma das mensagens será exportada se a des duplicação estiver habilitada quando os resultados da pesquisa são exportados. Portanto, mesmo que a mensagem original ou a mensagem copiada tenha sido alterada, nenhuma das mensagens revisadas foi enviada e, portanto, os valores das propriedades **InternetMessageId,** **ConversationTopic** e **BodyTagInfo** não foram atualizados. Mas, conforme explicado anteriormente, ambas as mensagens serão listadas nos relatórios de exportação 
  
As mensagens exclusivas também podem ser marcadas como duplicatas quando o recurso de proteção de página Copiar na Gravação estiver habilitado, como no caso de uma caixa de correio estar em Contencioso ou In-Place Desativer. O recurso Copy-on-Write copia a mensagem original (e salva-a na pasta Versões da pasta Itens Recuperáveis do usuário) antes que a revisão para o item original seja salva. Nesse caso, a cópia revisada e a mensagem original (na pasta Itens Recuperáveis) podem ser consideradas como mensagens duplicadas e, portanto, apenas uma delas seria exportada.
  
> [!IMPORTANT]
> Se as limitações do algoritmo de des duplicação podem afetar a qualidade dos resultados da pesquisa, você não deve habilitar a de duplicação ao exportar itens. Se as situações descritas nesta seção não são prováveis de serem um fator nos resultados da pesquisa e você quiser reduzir o número de itens mais prováveis de serem duplicados, considere a habilitação da des duplicação. 
  
## <a name="more-information"></a>Mais informações

- As informações neste artigo são aplicáveis ao exportar resultados de pesquisa usando uma das seguintes ferramentas de Descoberta e:

  - Pesquisa de conteúdo no centro de conformidade no Office 365

  - Descoberta Eletrônica In-loco no Exchange Online

  - A Central de Descoberta Eletrônica no SharePoint Online

- Para obter mais informações sobre como exportar resultados de pesquisa, consulte:

  - [Exportar Pesquisa de Conteúdo](export-search-results.md)

  - [Exportar um relatório da Pesquisa de Conteúdo](export-a-content-search-report.md)

  - [Exportar In-Place resultados da pesquisa de Descoberta EDiscovery para um arquivo PST](/exchange/security-and-compliance/in-place-ediscovery/export-search-results)

  - [Exportar conteúdo e criar relatórios no Centro de Descoberta eletrônica](/SharePoint/governance/export-content-and-create-reports-in-the-ediscovery-center)