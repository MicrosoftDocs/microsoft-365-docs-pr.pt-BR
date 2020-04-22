---
title: Deduplicação nos resultados de pesquisa de Descoberta Eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
description: Você tem a opção de cancelar a duplicação de resultados de pesquisa de descoberta eletrônica que são exportados para que apenas uma cópia de uma mensagem de email seja exportada, embora várias instâncias da mesma mensagem possam ter sido encontradas em caixas de correio diferentes.
ms.openlocfilehash: d61edf03ed64402f6540b4c822060f283825cd6e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630578"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>Deduplicação nos resultados de pesquisa de Descoberta Eletrônica

Este artigo descreve como a duplicação de resultados de pesquisa de descoberta eletrônica funciona e explica as limitações do algoritmo de eliminação de duplicação.
  
Ao usar ferramentas de descoberta eletrônica para exportar os resultados de uma pesquisa de descoberta eletrônica, você tem a opção de eliminar a duplicação dos resultados exportados. Cenário Quando você habilita a eliminação de duplicação (por padrão, a eliminação de duplicação não está habilitada), apenas uma cópia de uma mensagem de email é exportada, mesmo que várias instâncias da mesma mensagem possam ter sido encontradas nas caixas de correio que foram pesquisadas. A eliminação de duplicação ajuda você a economizar tempo reduzindo o número de itens que você precisa analisar e analisar após os resultados da pesquisa serem exportados. Mas é importante entender como a eliminação de duplicação funciona e estar ciente de que há limitações no algoritmo que podem fazer com que um item exclusivo seja marcado como duplicado durante o processo de exportação.
  
## <a name="how-duplicate-messages-are-identified"></a>Como as mensagens duplicadas são identificadas

as ferramentas de descoberta eletrônica usam uma combinação das seguintes propriedades de email para determinar se uma mensagem é uma duplicata:
  
- **InternetMessageId** -esta propriedade especifica o identificador de mensagem da Internet de uma mensagem de email, que é um identificador global exclusivo que se refere a uma versão específica de uma mensagem específica. Essa ID é gerada pelo programa cliente de email do remetente ou pelo sistema de email host que envia a mensagem. Se uma pessoa enviar uma mensagem para mais de um destinatário, a ID de mensagem da Internet será a mesma para cada instância da mensagem. Revisões subsequentes à mensagem original receberão um identificador de mensagem diferente. 

- **ConversationTopic** -esta propriedade especifica o assunto do thread de conversa de uma mensagem. O valor da propriedade **ConversationTopic** é a cadeia de caracteres que descreve o tópico geral da conversa. Uma conservação consiste em uma mensagem inicial e todas as mensagens enviadas em resposta à mensagem inicial. As mensagens dentro da mesma conversa têm o mesmo valor para a propriedade **ConversationTopic** . O valor dessa propriedade normalmente é a linha de assunto da mensagem inicial que gerou a conversa. 

- **BodyTagInfo** -esta é uma propriedade interna do repositório do Exchange. O valor dessa propriedade é calculado com a verificação de vários atributos no corpo da mensagem. Essa propriedade é usada para identificar as diferenças no corpo das mensagens. 

Durante o processo de exportação de descoberta eletrônica, essas três propriedades são comparadas a cada mensagem que corresponde aos critérios de pesquisa. Se essas propriedades forem idênticas para duas (ou mais) mensagens, essas mensagens serão determinadas como duplicatas e o resultado será que apenas uma cópia da mensagem será exportada se a eliminação de duplicação estiver habilitada. A mensagem exportada é conhecida como "item de origem". As informações sobre mensagens duplicadas são incluídas nos relatórios **Results. csv** e **manifest. xml** que estão incluídos nos resultados de pesquisa exportados. No arquivo **Results. csv** , uma mensagem duplicada é identificada por ter um valor na coluna **duplicar para item** . O valor desta coluna corresponde ao valor na coluna de **identidade do item** para a mensagem que foi exportada. 
  
Os gráficos a seguir mostram como as mensagens duplicadas são exibidas nos relatórios **Results. csv** e **manifest. xml** exportados com os resultados da pesquisa. Esses relatórios não incluem as propriedades de email descritas anteriormente, que são usadas no algoritmo de eliminação de duplicação. Em vez disso, os relatórios incluem a propriedade de **identidade de item** atribuída a itens pelo repositório do Exchange. 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>Relatório Results. csv (exibido no Excel)
  
![Exibindo informações sobre itens duplicados no relatório Results. csv](../media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Relatório manifest. XML (exibido no Excel)
  
![Exibindo informações sobre itens duplicados no relatório manifest. xml](../media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
Além disso, outras propriedades de mensagens duplicadas são incluídas nos relatórios de exportação. Isso inclui a caixa de correio na qual a mensagem duplicada está localizada, se a mensagem foi enviada a um grupo de distribuição e se a mensagem era CC ou Cco para outro usuário.
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>Limitações do algoritmo de eliminação de duplicação

Há algumas limitações conhecidas do algoritmo de eliminação de duplicação que podem fazer com que itens exclusivos sejam marcados como duplicatas. É importante entender essas limitações para que você possa decidir se usará ou não o recurso de eliminação de duplicação opcional.
  
Há uma situação em que o recurso de eliminação de duplicação pode identificar incorretamente uma mensagem como uma duplicata e não exportá-la (mas ainda a cite como uma duplicata nos relatórios de exportação). Essas são mensagens que um usuário edita, mas não envia. Por exemplo, digamos que um usuário selecione uma mensagem no Outlook, copie o conteúdo da mensagem e, em seguida, Cole-o em uma nova mensagem. Em seguida, o usuário altera uma das cópias removendo ou adicionando um anexo ou alterando a linha de assunto ou o próprio corpo. Se essas duas mensagens corresponderem à consulta de uma pesquisa de descoberta eletrônica, somente uma das mensagens será exportada se a eliminação de duplicação estiver habilitada quando os resultados da pesquisa forem exportados. Portanto, embora a mensagem original ou a mensagem copiada tenha sido alterada, nenhuma das mensagens revisadas foi enviada e, portanto, os valores das propriedades **InternetMessageId**, **ConversationTopic** e **BodyTagInfo** não foram atualizados. Mas, conforme explicado anteriormente, ambas as mensagens serão listadas nos relatórios de exportação 
  
As mensagens exclusivas também podem ser marcadas como duplicatas quando o recurso de proteção de página de cópia de gravação estiver habilitado, como no caso de uma caixa de correio em retenção de litígio ou bloqueio in-loco. O recurso de cópia na gravação copia a mensagem original (e salva-a na pasta versões da pasta itens recuperáveis do usuário) antes que a revisão para o item original seja salva. Nesse caso, a cópia revisada e a mensagem original (na pasta itens recuperáveis) podem ser consideradas como mensagens duplicadas e, portanto, apenas uma delas seria exportada.
  
> [!IMPORTANT]
> Se as limitações do algoritmo de eliminação de duplicação puderem afetar a qualidade dos resultados da pesquisa, você não deverá habilitar a eliminação de duplicação ao exportar itens. Se as situações descritas nesta seção forem improvável de ser um fator nos resultados da pesquisa e você quiser reduzir o número de itens que mais provavelmente serão duplicados, deverá considerar a possibilidade de habilitar a eliminação de duplicação. 
  
## <a name="more-information"></a>Mais informações

- As informações deste artigo se aplicam ao exportar os resultados da pesquisa usando uma das seguintes ferramentas de descoberta eletrônica:

  - Pesquisa de conteúdo no centro de conformidade no Office 365

  - Descoberta Eletrônica In-loco no Exchange Online

  - A Central de Descoberta Eletrônica no SharePoint Online

- Para obter mais informações sobre como exportar resultados de pesquisa, consulte:

  - [Exportar pesquisa de conteúdo](export-search-results.md)

  - [Exportar um relatório da Pesquisa de Conteúdo](export-a-content-search-report.md)

  - [Exportar resultados de pesquisa de descoberta eletrônica in-loco para um arquivo PST](https://go.microsoft.com/fwlink/p/?linkid=832671)

  - [Exportar conteúdo e criar relatórios no Centro de Descoberta eletrônica](https://support.office.com/article/7b2ea190-5f9b-4876-86e5-4440354c381a)
