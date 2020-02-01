---
title: Pool de entrega de alto risco para mensagens de saída
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/24/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Quando o sistema de email de um cliente é comprometido por malware ou um ataque de spam mal-intencionado e está enviando spam de saída por meio do serviço de filtragem hospedado, isso pode resultar em endereços IP dos servidores de data center do Office 365 listados no bloco de terceiros contém.
ms.openlocfilehash: 19987ae74b9c78a796ddb5f13cf8291a5ed269ad
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599228"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>Pool de entrega de alto risco para mensagens de saída

Quando o sistema de email de um cliente é comprometido por malware ou um ataque de spam mal-intencionado e está enviando spam de saída por meio do serviço de filtragem hospedado, isso pode resultar em endereços IP dos servidores de data center do Office 365 listados no bloco de terceiros contém. Servidores de destino que não usam o serviço de filtragem hospedado, mas usam essas listas de bloqueio, rejeitam todos os emails enviados de qualquer um dos endereços IP de filtragem hospedado que foram adicionados a essas listas. Para evitar isso, todas as mensagens de saída que excedem o limite de spam são enviadas por meio de um pool de entrega de alto risco. Esse pool de emails de saída secundário só é usado para enviar mensagens que podem ter baixa qualidade. Isso ajuda a proteger o restante da rede de enviar mensagens que são mais prováveis no bloqueio do endereço IP de envio.
  
O uso de um pool de entrega de alto risco dedicado ajuda a garantir que o pool de saída normal só esteja enviando mensagens conhecidas por uma alta qualidade. O uso desse pool IP secundário ajuda a reduzir a probabilidade de o pool de saída de IP normal ser adicionado a uma lista de bloqueados. A possibilidade de um pool de entrega de alto risco ser colocado em uma lista bloqueada continua a ser um risco. Isso é por desígnio.
  
Mensagens em que o domínio de envio não tem registro de endereço (um registro), que fornece o endereço IP do domínio, e nenhum registro MX, que ajuda a direcionar o email aos servidores que devem receber o email de um domínio específico no DNS, são sempre roteados através do pool de entrega de alto risco independentemente da disposição de spam.
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a>Noções básicas sobre mensagens de notificação de status de entrega (DSN)

O pool de entrega de alto risco de saída gerencia a entrega de todas as mensagens "devolvidas" ou "com falha" (DSN).
  
As possíveis causas para um surto nas mensagens DSN incluem o seguinte:
  
- Uma campanha de falsificação que afete um dos clientes que utilizam o serviço
    
- Um ataque de coleta de diretório
    
- Um ataque de spam
    
- Um servidor SMTP invasor
    
Todos esses problemas podem resultar em um aumento repentino no número de mensagens DSN processadas pelo serviço. Muitas vezes, essas mensagens DSN parecem ser spam para outros serviços e servidores de email.
  
## <a name="for-more-information"></a>Para obter mais informações

[Configuração da política de spam de saída](configure-the-outbound-spam-policy.md)
  
[Perguntas frequentes sobre a proteção antispam](anti-spam-protection-faq.md)
  

