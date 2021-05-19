---
title: Proteção contra spam de saída
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre os controles de spam de saída no Proteção do Exchange Online (EOP) e o que fazer se você precisar enviar emails em massa.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0fb6bfe5d83c551c0a93cc7b453b27a2d7b476bc
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538730"
---
# <a name="outbound-spam-protection-in-eop"></a>Proteção contra spam de saída no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas Proteção do Exchange Online (EOP) sem Exchange Online caixas de correio, levam a sério o gerenciamento de spam de saída. Mesmo que um cliente envie spam intencionalmente ou não intencionalmente de sua organização, essa ação pode degradar a reputação de todo o serviço e pode afetar a entrega de email para outros clientes.

Este artigo descreve os controles e notificações projetados para ajudar a evitar spam de saída e o que você pode fazer se precisar enviar emails em massa.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>O que os administradores podem fazer para controlar o spam de saída

- Use notificações **internas**: quando um usuário excede [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) os limites de envio das políticas de serviço ou de  [spam](configure-the-outbound-spam-policy.md) de saída e é restrita ao envio de emails, a política de alerta padrão chamada Usuário restrito de enviar emails envia notificações de email para membros do grupo **TenantAdmins** (**Administradores** globais ). Para configurar quem mais recebe essas notificações, consulte [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Além disso, as  políticas de alerta padrão denominadas Limite de envio de email excedida e padrões suspeitos de envio de **emails** detectados enviam notificações de email para membros do grupo **TenantAdmins** (**Administradores** globais ). Para obter mais informações sobre políticas de alerta, consulte [Políticas de alerta em Microsoft 365](../../compliance/alert-policies.md).

- Analisar reclamações de **spam** de provedores de email de terceiros : Muitos serviços de email, como Outlook.com, Yahoo e AOL, fornecem um loop de comentários em que, se algum usuário em seus serviços marcar um email do Microsoft 365 como spam, a mensagem será empacotada e enviada de volta para nós para revisão. Para saber mais sobre o suporte ao remetente para Outlook.com, acesse <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>Como o EOP controla o spam de saída

- **Segregação do tráfego de email de** saída : Todas as mensagens de saída enviadas pelo serviço são verificados em busca de spam. Se a mensagem for determinada como spam, ela será entregue de um pool de endereços IP secundário e menos confiável chamado pool de entrega de alto _risco._ Para saber mais, confira [Pool de entrega com maior risco em mensagens de saída](high-risk-delivery-pool-for-outbound-messages.md).

- **Monitorando nossa reputação de endereço IP de origem**: Microsoft 365 consultas a várias listas de bloqueios de IP de terceiros. Um alerta será gerado se qualquer um dos endereços IP que usamos para email de saída aparecer nessas listas. Esse monitoramento nos permite reagir rapidamente quando o spam fez com que nossa reputação degradasse. Quando um alerta é gerado, temos uma documentação interna que descreve como remover nossos endereços IP (deslistados) das listas de bloqueios.

- **Desabilitar** contas que enviam muito spam : Embora nós segregamos o spam de saída para o pool de entrega de alto risco, não podemos permitir que uma conta (muitas vezes, uma conta comprometida) envie <sup>\*</sup> spam indefinidamente. Monitoramos contas que estão enviando spam e, quando excedem um limite não revelado, a conta é impedida de enviar emails. Há limites diferentes para usuários individuais e para todo o locatário.

- **Desabilitando** contas que enviam emails muito rapidamente : além dos limites que procurarem mensagens marcadas como spam, também há limites que bloqueiam contas quando atingem um limite geral de mensagem de saída, independentemente do veredito de filtragem de spam nas mensagens de <sup>\*</sup> saída. Uma conta comprometida poderia enviar spam de dia zero (anteriormente não-reconhecedo) que é perdido pelo filtro de spam. Como pode ser difícil identificar uma campanha de email em massa legítima versus uma campanha de spam, esses limites ajudam a minimizar possíveis danos.

<sup>\*</sup> Não anunciamos os limites exatos para que os remetentes de spam não possam jogar o sistema e, portanto, podemos aumentar ou diminuir os limites conforme necessário. Os limites são altos o suficiente para impedir que um usuário comercial médio os exceda e baixo o suficiente para ajudar a conter os danos causados por um spammer.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Recomendações para clientes que querem enviar emails em massa por meio do EOP

É difícil encontrar um equilíbrio entre os clientes que querem enviar um grande volume de email em vez de proteger o serviço de contas comprometidas e envios de email em massa com práticas de aquisição de destinatários ruins. O custo de uma aterrissagem Microsoft 365 fonte de email em uma lista de bloqueios de IP de terceiros é maior do que bloquear um usuário que está enviando muitos emails.

Conforme descrito na descrição do serviço Exchange Online [,](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)usar o EOP para enviar emails em massa não é um uso suportado do serviço e só é permitido com base em "melhor esforço". Para clientes que querem enviar emails em massa, recomendamos as seguintes soluções:

- **Enviar emails em massa por meio** de servidores de email locais: os clientes mantêm sua própria infraestrutura de email para envios em massa.

- **Use um provedor de email** em massa de terceiros: há vários provedores de solução de email em massa de terceiros que você pode usar para enviar emails em massa. Essas empresas têm interesse em trabalhar com clientes para garantir boas práticas de envio de email.

O Grupo de Trabalho de Mensagens, Dispositivos Móveis, Antibusos de Malware (MAAWG) publica sua lista de membros em <https://www.maawg.org/about/roster> . Vários provedores de email em massa estão na lista e são conhecidos por serem cidadãos responsáveis da Internet.
