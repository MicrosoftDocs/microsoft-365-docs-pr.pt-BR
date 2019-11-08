---
title: Mnsagens backscatter e EOP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: As mensagens de dispersão são as mensagens de retorno automatizadas que são enviadas por servidores de email, geralmente como resultado de um spam de entrada. O DNSBL de Remetente de Backscatterer é uma lista de endereços IP que enviam mensagens backscatter. Não é uma lista de remetentes de spam e não tentamos remover nossos servidores da DNSBL de Remetentes de Backscatter.
ms.openlocfilehash: a90383709763974f36aede6f10c9e78224592744
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38034252"
---
# <a name="backscatter-messages-and-eop"></a>Mensagens backscatter e EOP

As mensagens de dispersão são as mensagens de retorno automatizadas que são enviadas por servidores de email, geralmente como resultado de um spam de entrada. Porque o Exchange Online Protection (EOP) é um serviço de filtro de spam, mensagens de email enviadas a destinatários inexistentes e para outros destinos suspeitos são rejeitadas por nosso serviço. Quando isso acontece, EOP gera uma mensagem do relatório de não-entregas (NDR) e a devolve ao "remetente". Porque remetentes de spam frequentemente usam um endereço "De" falsificados ou inválidos nas suas mensagens, o endereço do remetente ao qual o NDR é enviado pode resultar em uma mensagem backscatter. Quando isso acontece, servidores de saída que são associados à rede EOP podem ser listados na Lista de Bloqueio DNS de Remetente de Backscatter (DNSBL). O DNSBL de Remetente de Backscatterer é uma lista de endereços IP que enviam mensagens backscatter. Não é uma lista de remetentes de spam e não tentamos remover nossos servidores da DNSBL de Remetentes de Backscatter.

> [!TIP]
> De acordo com as instruções no site da web Backscatterer, o uso do modo rejeitar para todo email de entrada não é uma configuração recomendada ou uso desse serviço. Ao invés disso, ele deve ser usado no modo de segurança. Para obter mais informações sobre a implementação da configuração correta de backscatter, visite o site da web [Backscatterer.org](https://www.backscatterer.org/?target=usage).

## <a name="related-topics"></a>Tópicos relacionados

[Opções avançadas de filtragem de spam](advanced-spam-filtering-asf-options.md)
