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
ms.openlocfilehash: 5480916f55fc180a6f08d3c420cb92c730e4065b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167534"
---
# <a name="outbound-delivery-pools"></a>Pools de entrega de saída

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Os servidores de email nos datacenters do Microsoft 365 podem ficar temporariamente sem enviar spam. Por exemplo, um ataque de malware ou spam mal-intencionado em uma organização de email local que envia emails de saída por meio do Microsoft 365 ou contas comprometidas do Microsoft 365. Os invasores também tentam evitar a detecção retransmitindo mensagens por meio do encaminhamento do Microsoft 365.

Esses cenários podem fazer com que o endereço IP dos servidores de datacenter afetados do Microsoft 365 apareça em listas de bloqueio de terceiros. As organizações de email de destino que usam essas listas de bloqueio rejeitarão emails dessas fontes de mensagens.

## <a name="high-risk-delivery-pool"></a>Pool de entrega de alto risco
Para evitar isso, todas as mensagens de saída dos servidores de datacenter do Microsoft 365 que são determinadas como spam ou que excedem os limites de envio do serviço ou das políticas de [spam](configure-the-outbound-spam-policy.md) de saída são enviadas através do _pool_ de entrega de alto risco. [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

O pool de entrega de alto risco é um pool de endereços IP separado para emails de saída que é usado apenas para enviar mensagens de "baixa qualidade" (por exemplo, spam e [backscatter](backscatter-messages-and-eop.md)). Usar o pool de entrega de alto risco ajuda a impedir que o pool de endereços IP normal para emails de saída envie spam. O pool de endereços IP normal para emails de saída mantém a reputação enviando mensagens de "alta qualidade", o que reduz a probabilidade de que esses endereços IP apareçam nas listas de bloqueio de IP.

A possibilidade muito real de que os endereços IP no pool de entrega de alto risco sejam colocados em listas de bloqueio de IP permanece, mas isso é feito por design. A entrega aos destinatários pretendido não é garantida, porque muitas organizações de email não aceitam mensagens do pool de entrega de alto risco.

Para obter mais informações, consulte [Controle de spam de saída.](outbound-spam-controls.md)

> [!NOTE]
> As mensagens em que o domínio de email de origem não tem nenhum registro A e nenhum registro MX definido no DNS público são sempre roteadas através do pool de entrega de alto risco, independentemente de seu spam ou disposição do limite de envio.

### <a name="bounce-messages"></a>Mensagens de salto

O pool de entrega de alto risco de saída gerencia a entrega de todos os relatórios de não entrega (também conhecidos como NDRs, mensagens de rejeição, notificações de status de entrega ou DSNs).

As possíveis causas para um aumento nas NDRs incluem:

- Uma campanha de spoofing que afeta um dos clientes que usam o serviço.
- Um ataque de colheita de diretório.
- Um ataque de spam.
- Um servidor de email não..

Todos esses problemas podem resultar em um aumento súbito no número de NDRs sendo processadas pelo serviço. Muitas vezes, essas NDRs parecem ser spam para outros servidores e serviços de email (também conhecidos como _[backscatter).](backscatter-messages-and-eop.md)_

## <a name="relay-pool"></a>Pool de retransmissão

As mensagens que são encaminhadas ou retransmitida do Microsoft 365 são enviadas usando um pool de retransmissão especial, pois o destino final não deve considerar o Microsoft 365 como o remetente real. Também é importante isolar esse tráfego, pois existem cenários legítimos e inválidos para o envio automático ou a retransmissão de emails do Microsoft 365. Semelhante ao pool de entrega de alto risco, um pool de endereços IP separado é usado para emails repassados. Esse pool de endereços não é publicado, pois pode mudar com frequência.

O Microsoft 365 precisa verificar se o remetente original é legítimo para que possamos entregar a mensagem encaminhada com confiança. Para fazer isso, a autenticação de email (SPF, DKIM e DMARC) precisa passar quando a mensagem chegar até nós. Nos casos em que podemos autenticar o remetente, usamos a Reescrita de Remetente para ajudar o receptor a saber que a mensagem encaminhada é de uma fonte confiável. Você pode ler mais sobre como isso funciona e o que pode fazer para ajudar a garantir que o domínio de envio passe na autenticação no [SRS (Esquema de Reescrita](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme)de Remetente).
