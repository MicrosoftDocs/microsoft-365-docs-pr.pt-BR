---
title: Proteção de spam de saída
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
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre os controles de spam de saída na proteção do Exchange Online (EOP) e o que fazer se você precisar enviar emails em massa.
ms.openlocfilehash: 1097b768b955f2fa99c552ceda7564bef33a1aa7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202382"
---
# <a name="outbound-spam-protection-in-eop"></a>Proteção contra spam de saída no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, vamos Gerenciar spam de saída seriamente. Um cliente que envia de forma intencional ou não spam de sua organização pode degradar a reputação de todo o serviço e pode afetar a entrega de email para outros clientes.

Este tópico descreve os controles e as notificações que são projetados para ajudar a evitar spam de saída e o que você pode fazer se precisar enviar correspondências em massa.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>O que os administradores podem fazer para controlar o spam de saída

- **Usar notificações internas**: quando um usuário exceder os limites de envio das políticas de [serviço](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) ou [spam de saída](configure-the-outbound-spam-policy.md) e estiver restrito a enviar emails, a política de alerta padrão chamada **usuário impedida de enviar email** enviará notificações por email aos membros do grupo **TenantAdmins** (**administradores globais**). Para configurar quem mais receberá essas notificações, confira [verificar as configurações de alerta para usuários restritos](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Além disso, as políticas de alerta padrão denominadas **limite de envio de emails excedidos** e **suspeitas de envio de emails detectados** enviar notificações por email aos membros do grupo **TenantAdmins** (**administradores globais**). Para obter mais informações sobre políticas de alerta, consulte [Políticas de alerta no centro de segurança e conformidade.](../../compliance/alert-policies.md).

- **Revise as reclamações de spam de provedores de email de terceiros**: muitos serviços de email, como o Outlook.com, o Yahoo e o AOL fornecem um loop de feedback em que, se qualquer usuário em seu serviço marca um email da Microsoft 365 como spam, a mensagem é empacotada e enviada de volta para nós para análise. Para saber mais sobre o suporte do remetente para o Outlook.com, acesse <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>Como o EOP controla o spam de saída

- **Diferenciação de tráfego de email de saída**: todas as mensagens de saída enviadas pelo serviço são verificadas por spam. Se a mensagem for determinada como spam, ela será entregue de um pool de endereços IP secundário e menos confiável chamado _pool de entrega de alto risco_. Para saber mais, confira [Pool de entrega com maior risco em mensagens de saída](high-risk-delivery-pool-for-outbound-messages.md).

- **Monitorando nossa reputação de endereço IP de origem**: o Microsoft 365 consulta várias listas de bloqueios de IP de terceiros. Um alerta é gerado se qualquer um dos endereços IP usados para o email de saída aparecer nessas listas. Isso nos permite reagir rapidamente quando o spam causa a degradação da nossa reputação. Quando um alerta é gerado, temos documentação interna que descreve como obter os endereços IP removidos (deslistados) das listas de bloqueios.

- **Desabilitar contas que enviam muito spam** <sup>\*</sup> : embora segrego o spam de saída no pool de entrega de alto risco, não podemos permitir que uma conta (geralmente, uma conta comprometida) envie spam indefinidamente. Monitoramos contas que estão enviando spam e quando elas excedem um limite não divulgado, a conta é bloqueada para envio de email. Há diferentes limites para usuários individuais e para o locatário inteiro.

- **Desabilitando contas que enviam muito email muito rapidamente** <sup>\*</sup> : além dos limites que procuram mensagens marcadas como spam, também há limites que bloqueiam contas quando atingem um limite de mensagens de saída geral, independentemente da veredicto de filtragem de spam nas mensagens de saída. Uma conta comprometida pode enviar spams (anteriormente não reconhecidos) que são perdidos pelo filtro de spam. Como pode ser difícil identificar uma campanha de mala direta em massa legítima vs. uma campanha de spam, esses limites ajudam a minimizar possíveis danos.

<sup>\*</sup> Não anunciamos os limites exatos para que os spammers não possam fazer o jogo do sistema e, portanto, podemos aumentar ou diminuir os limites conforme necessário. Os limites são altos o suficiente para evitar que um usuário da empresa seja excedido de uma média duração e o suficiente para ajudar a conter os danos causados por um remetente de spam.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Recomendações para clientes que desejam enviar correspondências em massa por meio do EOP

É difícil fazer um equilíbrio entre os clientes que desejam enviar um grande volume de emails versus proteger o serviço contra contas comprometidas e remetentes em massa de emails com boas práticas de aquisição de destinatário. O custo de um patamar de fonte de email do Microsoft 365 em uma lista de IP bloqueados de terceiros é maior do que o bloqueio de um usuário que está enviando muito email.

Conforme descrito na [Descrição do serviço do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), o uso do EOP para enviar emails em massa não é um uso com suporte do serviço e só é permitido em uma base de "melhor esforço". Para clientes que desejam enviar email em massa, recomendamos as seguintes soluções:

- **Enviar email em massa por meio de servidores de email locais**: isso significa que os clientes precisarão manter sua própria infraestrutura de email para correspondências em massa.

- **Use um provedor de email em massa de**terceiros: há vários provedores de soluções de email em massa de terceiros que você pode usar para enviar correspondências em massa. Essas empresas têm interesse em trabalhar com os clientes para garantir boas práticas de envio de email.

O grupo de trabalho de MAAWG (mensagens antiabuso, móvel e malware) publica sua lista de associação em <https://www.maawg.org/about/roster> . Vários provedores de email em massa estão na lista e são conhecidos como cidadãos da Internet responsáveis.
