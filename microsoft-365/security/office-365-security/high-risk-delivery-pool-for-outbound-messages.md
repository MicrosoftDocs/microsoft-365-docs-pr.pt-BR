---
title: Pool de entrega de alto risco para mensagens de saída
f1.keywords:
- NOCSH
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
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Saiba como o pool de entrega de alto risco é usado para proteger a reputação de servidores de email nos datacenters do Microsoft 365.
ms.openlocfilehash: 190dc3bd7ed2a6cddb23c8bc7c117dee30fd4f13
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209182"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>Pool de entrega de alto risco para mensagens de saída

Os servidores de email nos datacenters do Microsoft 365 podem ser temporariamente culpados no envio de spam. Por exemplo, um ataque de malware ou spam mal-intencionado em uma organização de email local que envia emails de saída pelo Microsoft 365 ou contas do Microsoft 365 comprometidas. Esses cenários podem resultar no endereço IP dos servidores de datacenters do Microsoft 365 afetados que aparecem nas listas de bloqueios de terceiros. As organizações de email de destino que usam essas listas de bloqueio rejeitarão emails dessas fontes de mensagens.

Para evitar isso, todas as mensagens de saída dos servidores de datacenter da Microsoft 365 que são determinados como spam ou que excedem os limites de envio do [serviço](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) ou [as políticas de spam de saída](configure-the-outbound-spam-policy.md) são enviadas através do pool de _entrega de alto risco_.

O pool de entrega de alto risco é um pool de endereços IP secundário para email de saída que só é usado para enviar mensagens de "baixa qualidade" (por exemplo, spam e [dispersão](backscatter-messages-and-eop.md)). O uso do pool de entrega de alto risco ajuda a evitar que o pool de endereços IP normal para email de saída envie spam. O pool de endereços IP normal para email de saída mantém a reputação de enviar mensagens de "alta qualidade", o que reduz a probabilidade de que esse endereço IP apareça em listas de bloqueios de IP.

A possibilidade real de que os endereços IP no pool de entrega de alto risco sejam colocados em listas de bloqueios de IP permaneça, mas isso ocorre por design. A entrega aos destinatários pretendidos não é garantida, pois muitas organizações de email não aceitarão mensagens do pool de entrega de alto risco.

Para obter mais informações, consulte [controlar spam de saída](outbound-spam-controls.md).

> [!NOTE]
> Mensagens em que o domínio de email de origem não tem um registro A e nenhum registro MX definido no DNS público sempre é roteado através do pool de entrega de alto risco, independentemente da disposição de spam ou de limite de envio.

## <a name="bounce-messages"></a>Mensagens de devolução

O pool de entrega de alto risco de saída gerencia a entrega de todas as notificações de falha na entrega (também conhecidas como NDRs, mensagens de devolução, notificações de status de entrega ou DSNs).

As possíveis causas para uma sobrecarga nos NDRs incluem:

- Uma campanha de falsificação que afeta um dos clientes que usam o serviço.
- Um ataque de coleta de diretório.
- Um ataque de spam.
- Um servidor de emails não autorizados.

Todos esses problemas podem resultar em um aumento repentino no número de NDRs que estão sendo processados pelo serviço. Muitas vezes, esses NDRs parecem ser spam para outros servidores de email e serviços (também conhecidos como _[dispersão](backscatter-messages-and-eop.md)_).
