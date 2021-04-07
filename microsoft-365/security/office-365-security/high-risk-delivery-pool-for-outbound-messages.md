---
title: Pools de entrega de saída
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Saiba como os pools de entrega são usados para proteger a reputação dos servidores de email nos datacenters do Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac3469150ef5cf5c1040fcddf7f0bc95e7a18805
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599906"
---
# <a name="outbound-delivery-pools"></a>Pools de entrega de saída

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Os servidores de email nos datacenters do Microsoft 365 podem ser temporariamente considerados como os que enviam spam. Por exemplo, um ataque de malware ou spam mal-intencionado em uma organização de email local que envia emails de saída por meio do Microsoft 365 ou contas comprometidas do Microsoft 365. Os invasores também tentam evitar a detecção retransmitindo mensagens por meio do encaminhamento do Microsoft 365.

Esses cenários podem resultar no endereço IP dos servidores de datacenter do Microsoft 365 afetados que aparecem em listas de bloqueios de terceiros. As organizações de email de destino que usam essas listas de bloqueio rejeitarão emails dessas fontes de mensagens.

## <a name="high-risk-delivery-pool"></a>Pool de entrega de alto risco
Para evitar isso, todas as mensagens de saída dos servidores de datacenter do Microsoft 365 que são determinadas como spam ou que excedem os limites de envio do serviço ou das políticas de [spam](configure-the-outbound-spam-policy.md) de saída são enviadas por meio do _pool_ de entrega de alto risco. [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

O pool de entrega de alto risco é um pool de endereços IP separado para email de saída que é usado apenas para enviar mensagens de "baixa qualidade" (por exemplo, spam e [backscatter](backscatter-messages-and-eop.md)). O uso do pool de entrega de alto risco ajuda a impedir que o pool de endereços IP normal para email de saída envie spam. O pool de endereços IP normal para email de saída mantém a reputação de envio de mensagens de "alta qualidade", o que reduz a probabilidade de que esses endereços IP apareçam em listas de bloqueios de IP.

A possibilidade muito real de que os endereços IP no pool de entrega de alto risco sejam colocados em listas de bloqueios de IP permanece, mas isso é por design. A entrega aos destinatários pretendido não é garantida, pois muitas organizações de email não aceitarão mensagens do pool de entrega de alto risco.

Para obter mais informações, consulte [Control outbound spam](outbound-spam-controls.md).

> [!NOTE]
> As mensagens em que o domínio de email de origem não tem registro A e nenhum registro MX definido no DNS público são sempre roteadas pelo pool de entrega de alto risco, independentemente de seu spam ou disposição de limite de envio.

### <a name="bounce-messages"></a>Mensagens de rejeição

O pool de entrega de alto risco de saída gerencia a entrega de todos os relatórios de não entrega (também conhecidos como NDRs, mensagens de rejeição, notificações de status de entrega ou DSNs).

As possíveis causas para uma sobrecarga em NDRs incluem:

- Uma campanha de spoofing que afeta um dos clientes que usam o serviço.
- Um ataque de coleta de diretório.
- Um ataque de spam.
- Um servidor de email desonesto.

Todos esses problemas podem resultar em um aumento repentino no número de NDRs sendo processados pelo serviço. Muitas vezes, essas NDRs parecem ser spam para outros servidores de email e serviços (também conhecidos como _[backscatter](backscatter-messages-and-eop.md)_).
