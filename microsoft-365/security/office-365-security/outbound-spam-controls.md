---
title: Proteção contra spam de saída no Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: Os administradores podem saber mais sobre como o Office 365 e o proteção do Exchange Online (EOP) protegem os clientes contra spam de saída e o que fazer se você precisar enviar correspondências em massa.
ms.openlocfilehash: 99e764944335be923ee1918851d4072ea98d3a32
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895318"
---
# <a name="outbound-spam-protection-in-office-365"></a>Proteção contra spam de saída no Office 365

Adotamos o gerenciamento de spam de saída seriamente, porque o Office 365 (proteção do Exchange Online ou do Exchange Online autônomo (EOP) sem caixas de correio do Exchange Online) é um serviço online em que muitos clientes usam um pool de recursos compartilhado. Um cliente do Office 365 que envia intencionalmente o spam de sua organização pode degradar a reputação de todo o serviço e pode afetar a entrega de emails de outros clientes.

Este tópico descreve os controles e as notificações que são projetados para ajudar a evitar spam de saída e o que você pode fazer se precisar enviar correspondências em massa.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>O que os administradores podem fazer para controlar o spam de saída

- **Usar notificações internas**: quando um usuário exceder os limites de envio das políticas de [serviço](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) ou [spam de saída](configure-the-outbound-spam-policy.md) e estiver restrito a enviar emails, a política de alerta padrão chamada **usuário impedida de enviar email** enviará notificações por email aos membros do grupo **TenantAdmins** (**administradores globais**). Para configurar quem mais receberá essas notificações, confira [verificar as configurações de alerta para usuários restritos](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Além disso, as políticas de alerta padrão denominadas **limite de envio de emails excedidos** e **suspeitas de envio de emails detectados** enviar notificações por email aos membros do grupo **TenantAdmins** (**administradores globais**). Para obter mais informações sobre políticas de alerta, consulte [políticas de alerta no centro de conformidade e segurança](../../compliance/alert-policies.md).

- **Revise as reclamações de spam de provedores de email de terceiros**: muitos serviços de email, como o Outlook.com, o Yahoo e o AOL fornecem um loop de feedback onde qualquer usuário em seu serviço marca um email do Office 365 como spam, a mensagem é empacotada e enviada de volta para nós para análise. Para saber mais sobre o suporte do remetente para o Outlook.com <https://sendersupport.olc.protection.outlook.com/pm/services.aspx>, acesse.

## <a name="how-eop-controls-outbound-spam"></a>Como o EOP controla o spam de saída

- **Diferenciação de tráfego de email de saída**: todas as mensagens de saída enviadas pelo serviço são verificadas por spam. Se a mensagem for determinada como spam, ela será entregue de um pool de endereços IP secundário e menos confiável chamado _pool de entrega de alto risco_. Para obter mais informações, consulte [pool de entrega de alto risco para mensagens de saída no Office 365](high-risk-delivery-pool-for-outbound-messages.md).

- **Monitorando nossa reputação de endereço IP de origem**: o Office 365 consulta várias listas de bloqueio de IP de terceiros. Um alerta é gerado se qualquer um dos endereços IP usados para o email de saída aparecer nessas listas. Isso nos permite reagir rapidamente quando o spam causa a degradação da nossa reputação. Quando um alerta é gerado, temos documentação interna que descreve como obter os endereços IP removidos (deslistados) das listas de bloqueios.

- **Desabilitar contas que enviam muito spam**<sup>\*</sup>: embora segrego o spam de saída no pool de entrega de alto risco, não podemos permitir que uma conta (geralmente, uma conta comprometida) envie spam indefinidamente. Monitoramos contas que estão enviando spam e quando elas excedem um limite não divulgado, a conta é bloqueada para envio de email. Há diferentes limites para usuários individuais e para o locatário inteiro.

- **Desabilitando contas que enviam muito email muito rapidamente**<sup>\*</sup>: além dos limites que procuram mensagens marcadas como spam, também há limites que bloqueiam contas quando atingem um limite de mensagens de saída geral, independentemente da veredicto de filtragem de spam nas mensagens de saída. Uma conta comprometida pode enviar spams (anteriormente não reconhecidos) que são perdidos pelo filtro de spam. Como pode ser difícil identificar uma campanha de mala direta em massa legítima vs. uma campanha de spam, esses limites ajudam a minimizar possíveis danos.

<sup>\*</sup>Não anunciamos os limites exatos para que os spammers não possam fazer o jogo do sistema e, portanto, podemos aumentar ou diminuir os limites conforme necessário. Os limites são altos o suficiente para evitar que um usuário da empresa seja excedido de uma média duração e o suficiente para ajudar a conter os danos causados por um remetente de spam.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Recomendações para clientes que desejam enviar correspondências em massa por meio do EOP

É difícil fazer um equilíbrio entre os clientes que desejam enviar um grande volume de emails versus proteger o serviço contra contas comprometidas e remetentes em massa de emails com boas práticas de aquisição de destinatário. O custo de um destino de fonte de email do Office 365 em uma lista de IP bloqueados de terceiros é maior do que o bloqueio de um usuário que está enviando muito email.

Conforme descrito na [Descrição do serviço do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), o uso do EOP para enviar emails em massa não é um uso com suporte do serviço e só é permitido em uma base de "melhor esforço". Para clientes que desejam enviar email em massa, recomendamos as seguintes soluções:

- **Enviar email em massa por meio de servidores de email locais**: isso significa que os clientes precisarão manter sua própria infraestrutura de email para correspondências em massa.

- **Use um provedor de email em massa de**terceiros: há vários provedores de soluções de email em massa de terceiros que você pode usar para enviar correspondências em massa. Essas empresas têm interesse em trabalhar com os clientes para garantir boas práticas de envio de email.

O grupo de trabalho de MAAWG (mensagens antiabuso, móvel e malware) publica sua lista de associação <https://www.maawg.org/about/roster>em. Vários provedores de email em massa estão na lista e são conhecidos como cidadãos da Internet responsáveis.
