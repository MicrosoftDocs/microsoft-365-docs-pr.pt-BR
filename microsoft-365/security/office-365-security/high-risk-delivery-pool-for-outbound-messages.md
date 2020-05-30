---
title: Pools de entrega de saída
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
description: Saiba como os pools de entrega são usados para proteger a reputação de servidores de email nos datacenters do Microsoft 365.
ms.openlocfilehash: 213149eda3dd121b65b64e3bddbb4bd73d66f57c
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419155"
---
# <a name="outbound-delivery-pools"></a>Pools de entrega de saída

Os servidores de email nos datacenters do Microsoft 365 podem ser temporariamente culpados no envio de spam. Por exemplo, um ataque de malware ou spam mal-intencionado em uma organização de email local que envia emails de saída pelo Microsoft 365 ou contas do Microsoft 365 comprometidas. Os invasores também tentam evitar a detecção retransmitindo mensagens por meio do Microsoft 365 Forwarding.

Esses cenários podem resultar no endereço IP dos servidores de datacenters do Microsoft 365 afetados que aparecem nas listas de bloqueios de terceiros. As organizações de email de destino que usam essas listas de bloqueio rejeitarão emails dessas fontes de mensagens.

## <a name="high-risk-delivery-pool"></a>Pool de entrega de alto risco
Para evitar isso, todas as mensagens de saída dos servidores de datacenter da Microsoft 365 que são determinados como spam ou que excedem os limites de envio do [serviço](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) ou [as políticas de spam de saída](configure-the-outbound-spam-policy.md) são enviadas através do pool de _entrega de alto risco_.

O pool de entrega de alto risco é um pool de endereços IP separado para email de saída que só é usado para enviar mensagens de "baixa qualidade" (por exemplo, spam e [dispersão](backscatter-messages-and-eop.md)). O uso do pool de entrega de alto risco ajuda a evitar que o pool de endereços IP normal para email de saída envie spam. O pool de endereços IP normal para email de saída mantém a reputação de enviar mensagens de "alta qualidade", o que reduz a probabilidade de que esse endereço IP apareça em listas de bloqueios de IP.

A possibilidade real de que os endereços IP no pool de entrega de alto risco sejam colocados em listas de bloqueios de IP permaneça, mas isso ocorre por design. A entrega aos destinatários pretendidos não é garantida, pois muitas organizações de email não aceitarão mensagens do pool de entrega de alto risco.

Para obter mais informações, consulte [controlar spam de saída](outbound-spam-controls.md).

> [!NOTE]
> Mensagens em que o domínio de email de origem não tem um registro A e nenhum registro MX definido no DNS público sempre é roteado através do pool de entrega de alto risco, independentemente da disposição de spam ou de limite de envio.

### <a name="bounce-messages"></a>Mensagens de devolução

O pool de entrega de alto risco de saída gerencia a entrega de todas as notificações de falha na entrega (também conhecidas como NDRs, mensagens de devolução, notificações de status de entrega ou DSNs).

As possíveis causas para uma sobrecarga nos NDRs incluem:

- Uma campanha de falsificação que afeta um dos clientes que usam o serviço.
- Um ataque de coleta de diretório.
- Um ataque de spam.
- Um servidor de emails não autorizados.

Todos esses problemas podem resultar em um aumento repentino no número de NDRs que estão sendo processados pelo serviço. Muitas vezes, esses NDRs parecem ser spam para outros servidores de email e serviços (também conhecidos como _[dispersão](backscatter-messages-and-eop.md)_).

## <a name="relay-pool"></a>Pool de retransmissão

As mensagens que são encaminhadas ou retransmitidas para o Microsoft 365 são enviadas usando um pool de retransmissão especial, pois o destino final não deve considerar o Microsoft 365 como o remetente real. Também é importante que possamos isolar esse tráfego, porque há cenários legítimos e illegitmate para o encaminhamento ou a retransmissão de emails do Microsoft 365. Semelhante ao pool de entrega de alto risco, um pool de endereços IP separado é usado para retransmitir emails. Este pool de endereços não é publicado, pois pode ser alterado com frequência. 

O Microsoft 365 precisa verificar se o remetente original é legítimo, para que possamos fornecer com segurança a mensagem encaminhada. Para fazer isso, a autenticação de email (SPF, DKIM e DMARC) precisa passar quando a mensagem chega a nós. Nos casos em que podemos autenticar o remetente, usamos a reconfiguração do remetente para ajudar o destinatário a saber que a mensagem encaminhada é de uma fonte confiável. Você pode ler mais sobre como isso funciona e o que você pode fazer para ajudar a garantir que o domínio de envio passe a autenticação no [reconfiguração do remetente (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).
