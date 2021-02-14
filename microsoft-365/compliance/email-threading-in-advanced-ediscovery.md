---
title: Threading de email na Descoberta Eletrônico Avançada
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
description: Ao conduzir uma análise de Descoberta Eletrônico Avançada, o threading de email analisará uma conversa de email e separará cada mensagem em categorias diferentes.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285557"
---
# <a name="email-threading-in-advanced-ediscovery"></a>Threading de email na Descoberta Eletrônico Avançada

Considere uma conversa de email que está acontecendo há algum tempo. Na maioria dos casos, o último email no thread incluirá o conteúdo de todos os emails anteriores; analisar o último email dará um contexto completo da conversa que aconteceu no thread. O threading de email identifica esses emails para que os revisadores possam revisar uma fração de documentos coletados sem perder nenhum contexto.

## <a name="what-does-email-threading-do"></a>O que o threading de email faz?

O threading de email avalia cada email e o desconstrói para mensagens individuais; cada email é uma cadeia de mensagens individuais. Em seguida, ele analisa todos os emails no conjunto de revisão para determinar se um email tem conteúdo exclusivo ou se a cadeia está totalmente contida em um email diferente. No final, os emails são divididos em quatro categorias:

- **Inclusive:** a última mensagem no email tem conteúdo exclusivo, e o email tem todos os anexos incluídos em outros emails dos quais o conteúdo está totalmente contido neste email.

- **Menos inclusive:** a última mensagem no email tem conteúdo exclusivo, mas o email não contém alguns dos anexos incluídos em outros emails dos quais o conteúdo está totalmente contido neste email.

- **Cópia inclusiva**: uma cópia exata de um email inclusivo/inclusivo

- **Nenhum**: o conteúdo desse email está contido totalmente em pelo menos um email marcado como menos inclusivo/inclusivo.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>Qual é a diferença entre as conversas no Outlook?

Em um relance, isso parece semelhante a agrupações de conversas no Outlook. No entanto, há algumas distinções importantes. Considere uma conversa de email bifurcada em duas conversas; por exemplo, alguém respondeu a um email que não é o mais recente na conversa para que os dois últimos emails da conversa tenham conteúdo exclusivo.

O Outlook ainda agruparia os emails em uma única conversa; ler apenas o último email significa perder o contexto do segundo ao último email, que também contém conteúdo exclusivo. Como o threading de email analisará cada email em componentes individuais e os comparará, o threading de email marcará os dois últimos emails como inclusivos, garantindo que você não perca nenhum contexto desde que leia todos os emails marcados como inclusivos.
