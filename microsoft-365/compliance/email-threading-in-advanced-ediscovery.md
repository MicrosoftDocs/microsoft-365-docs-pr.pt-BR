---
title: Threading de emails
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: dd155668c8ed91bced7fc7d84764f08ef9799002
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595086"
---
# <a name="email-threading"></a>Threading de emails

Considere uma conversa por email que está acontecendo por algum tempo. Na maioria dos casos, o último email no thread incluirá o conteúdo de todos os emails anteriores; a revisão do último email fornecerá um contexto completo da conversa que aconteceu no thread. O encadeamento de emails identifica esses emails para que os Revisores possam revisar uma fração de documentos coletados sem perder nenhum contexto.

## <a name="what-does-email-threading-do"></a>O que o thread de email faz?

O encadeamento de emails analisa cada email e o desconstructs para mensagens individuais; cada email é uma cadeia de mensagens individuais. Em seguida, ele analisa todos os emails na análise definida para determinar se um email tem conteúdo exclusivo ou se a cadeia está totalmente contida em um email diferente. Nos emails finais estão divididos em quatro categorias:

- **Inclusive**: a última mensagem no email tem conteúdo exclusivo e o email tem todos os anexos que foram incluídos em outros emails dos quais o conteúdo está totalmente contido neste email.


- **Inclusive menos**: a última mensagem no email tem conteúdo exclusivo, mas o email não contém alguns dos anexos que foram incluídos em outros emails dos quais o conteúdo está totalmente contido neste email.

- **Cópia inclusiva**: uma cópia exata de um email incluindo menos de um

- **Nenhum**: o conteúdo desse email está totalmente contido em pelo menos um email marcado como incluindo, inclusive, o menos.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>Qual é a diferença entre conversas no Outlook?
Em resumo, isso parece muito semelhante aos agrupamentos de conversa no Outlook. No entanto, há algumas diferenças importantes. Considere uma conversa de email que foi bifurcada em duas conversas; por exemplo, alguém respondeu a um email que não é o mais recente na conversa para que os dois últimos emails da conversa tenham conteúdo exclusivo.

O Outlook ainda agruparia os emails em uma única conversa; somente leitura o último email significaria ter o contexto do segundo email, que também contém conteúdo exclusivo. Como o encadeamento de emails analisa todos os emails em componentes individuais e os compara, o encadeamento de emails marcaria os dois últimos emails como inclusivos, garantindo que você não perderá nenhum contexto, desde que Leia todos os emails marcados como inclusive.