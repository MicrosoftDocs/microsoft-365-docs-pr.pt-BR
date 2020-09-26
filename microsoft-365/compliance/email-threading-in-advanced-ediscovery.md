---
title: Encadeamento de emails na descoberta eletrônica avançada
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
description: Ao realizar uma análise de descoberta eletrônica avançada, o encadeamento de emails analisa uma conversa por email e separa cada mensagem em diferentes categorias.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285557"
---
# <a name="email-threading-in-advanced-ediscovery"></a>Encadeamento de emails na descoberta eletrônica avançada

Considere uma conversa por email que está acontecendo por algum tempo. Na maioria dos casos, o último email no thread incluirá o conteúdo de todos os emails anteriores; a revisão do último email fornecerá um contexto completo da conversa que aconteceu no thread. O encadeamento de emails identifica esses emails para que os Revisores possam revisar uma fração de documentos coletados sem perder nenhum contexto.

## <a name="what-does-email-threading-do"></a>O que o thread de email faz?

O thread de email analisa cada email e o deconstrói para mensagens individuais; cada email é uma cadeia de mensagens individuais. Em seguida, ele analisa todos os emails na análise definida para determinar se um email tem conteúdo exclusivo ou se a cadeia está totalmente contida em um email diferente. Nos emails finais estão divididos em quatro categorias:

- **Inclusive**: a última mensagem no email tem conteúdo exclusivo e o email tem todos os anexos que foram incluídos em outros emails dos quais o conteúdo está totalmente contido neste email.

- **Inclusive menos**: a última mensagem no email tem conteúdo exclusivo, mas o email não contém alguns dos anexos que foram incluídos em outros emails dos quais o conteúdo está totalmente contido neste email.

- **Cópia inclusiva**: uma cópia exata de um email incluindo menos de um

- **Nenhum**: o conteúdo desse email está totalmente contido em pelo menos um email marcado como incluindo, inclusive, o menos.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>Qual é a diferença entre conversas no Outlook?

Em um relance, isso parece semelhante aos agrupamentos de conversa no Outlook. No entanto, há algumas diferenças importantes. Considere uma conversa de email que foi bifurcada em duas conversas; por exemplo, alguém respondeu a um email que não é o mais recente na conversa para que os dois últimos emails da conversa tenham conteúdo exclusivo.

O Outlook ainda agruparia os emails em uma única conversa; somente leitura o último email significaria ter o contexto do segundo email, que também contém conteúdo exclusivo. Como o encadeamento de emails analisa cada email em componentes individuais e os compara, o encadeamento de emails marcaria ambos os dois últimos emails, o que garante que você não perderá nenhum contexto, desde que você leia todos os emails marcados como inclusive.
