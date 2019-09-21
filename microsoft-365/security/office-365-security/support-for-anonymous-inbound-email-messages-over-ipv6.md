---
title: Suporte para mensagens de email de entrada anônimas por IPv6
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: Saiba como configurar o suporte para mensagens anônimas de fontes IPv6 para o Exchange Online Protection e o Exchange Online.
ms.openlocfilehash: b6b1a0f42d879929de5059b6e197bd5fe14887dc
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073834"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a>Suporte para mensagens de email de entrada anônimas por IPv6

Exchange Online Protection (EOP) e Exchange Online suportam o recebimento de mensagens de email de entrada anônimas sobre comunicações IPv6 de remetentes que não enviam mensagens sobre Transport Layer Security (TLS). Você pode optar por receber mensagens por IPv6 solicitando essa funcionalidade do suporte da Microsoft abrindo o centro de administração do Microsoft 365 em [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home), clicando em **suporte**e, em seguida, clicando em **nova solicitação de serviço**. Se você não optar por IPv6, continuará recebendo mensagens sobre IPv4.
  
Remetentes que transmitem mensagens para serviço sobre IPv6 devem cumprir com os dois requisitos a seguir:
  
1. O endereço de IPv6 remetente deve ter um registro PTR válido ([registro DNS inverso](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) do endereço IPv6 remetente). 
    
2. O remetente deve passar por verificação SPF (definida na [RFC 7208](https://tools.ietf.org/html/rfc7208)) ou [verificação DKIM](http://dkim.org/) (definida na [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).
    
É obrigatório cumprir com esses requisitos, independentemente da configuração anterior à escolha do IPv6. Se ambos os requisitos forem satisfeitos, a mensagem passará pelo filtro de mensagens de email normal fornecido pelo serviço. Se uma ou outra não for atendida, a mensagem será rejeitada com uma das seguintes respostas 450:
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
Se você não tiver a opção de receber mensagens sobre IPv6 e o remetente tentar forçar uma mensagem sobre IPv6 manualmente conectando-se ao servidor de email, a mensagem será rejeitada com uma resposta 550 parecida com a seguinte:
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a>Para saber mais

[Suporte para validação de mensagens assinadas por DKIM](support-for-validation-of-dkim-signed-messages.md)
  

