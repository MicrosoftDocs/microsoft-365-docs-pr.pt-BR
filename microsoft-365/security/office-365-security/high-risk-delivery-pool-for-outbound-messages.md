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
description: Saiba como os pools de entrega são usados para proteger a reputação dos servidores de email nos Microsoft 365 datacenters.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 85f200cf226a050762db4ea37255f71241d1f98c
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137710"
---
# <a name="outbound-delivery-pools"></a>Pools de entrega de saída

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Os servidores de email Microsoft 365 datacenters podem ser temporariamente considerados como os que enviam spam. Por exemplo, um ataque de malware ou spam mal-intencionado em uma organização de email local que envia emails de saída por meio de Microsoft 365 ou contas Microsoft 365 comprometidas. Os invasores também tentam evitar a detecção retransmitindo mensagens Microsoft 365 encaminhamento.

Esses cenários podem resultar no endereço IP dos servidores Microsoft 365 datacenter afetados que aparecem em listas de bloqueio de terceiros. As organizações de email de destino que usam essas listas de bloqueio rejeitarão emails dessas fontes de mensagens.

## <a name="high-risk-delivery-pool"></a>Pool de entrega de alto risco
Para evitar isso, todas as mensagens de saída de servidores de datacenter Microsoft 365 que são [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) determinadas como spam ou que excedem os limites de envio do serviço ou das políticas de [spam](configure-the-outbound-spam-policy.md) de saída são enviadas por meio do _pool_ de entrega de alto risco.

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


### <a name="relay-pool"></a>Pool de retransmissão

As mensagens encaminhadas ou retransmitida por Microsoft 365 em determinados cenários serão enviadas usando um pool de retransmissão especial, pois o destino não deve considerar Microsoft 365 como o remetente real. É importante isolar esse tráfego de email, pois existem cenários legítimos e inválidos para encaminhamento automático ou retransmissão de emails fora de Microsoft 365. Semelhante ao pool de entrega de alto risco, um pool de endereços IP separado é usado para emails reenvados. Esse pool de endereços não é publicado porque pode mudar com frequência e não faz parte do registro SPF publicado para Microsoft 365.

Microsoft 365 precisa verificar se o remetente original é legítimo para que possamos entregar com confiança a mensagem encaminhada.

A mensagem encaminhada/retransmitida deve atender a um dos seguintes critérios para evitar o uso do pool de retransmissão:

- O remetente de saída está em [um domínio aceito.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
- SPF passa quando a mensagem é Microsoft 365.
- O DKIM no domínio do remetente passa quando a mensagem é Microsoft 365.
 
Você pode dizer que uma mensagem foi enviada por meio do pool de retransmissão olhando para o IP do servidor de saída (o pool de retransmissão estará no intervalo 40.95.0.0/16) ou olhando para o nome do servidor de saída (terá "rly" no nome).

Nos casos em que podemos autenticar o remetente, usamos o Esquema de Reescrita de Remetente (SRS) para ajudar o sistema de email do destinatário a saber que a mensagem encaminhada é de uma fonte confiável. Você pode ler mais sobre como isso funciona e o que pode fazer para ajudar a garantir que o domínio de envio passe autenticação no [SrS (Esquema](/office365/troubleshoot/antispam/sender-rewriting-scheme)de Reescrita do Remetente) em Office 365 .

Para que o DKIM funcione, certifique-se de habilitar o DKIM para envio de domínio. Por exemplo, fabrikam.com faz parte do contoso.com e é definido nos domínios aceitos da organização. Se o remetente da mensagem sender@fabrikam.com, o DKIM precisará ser habilitado para fabrikam.com. você pode ler sobre como habilitar em [Usar DKIM para validar emails](use-dkim-to-validate-outbound-email.md)de saída enviados do seu domínio personalizado.

Para adicionar domínios personalizados, siga as etapas em [Adicionar um domínio a Microsoft 365](../../admin/setup/add-domain.md).
