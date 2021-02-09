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
description: Os administradores podem aprender sobre os controles de spam de saída no Exchange Online Protection (EOP) e o que fazer se você precisar enviar mensagens em massa.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6d5a82b4a2c7f94b3c5d0958abc8c4552cc04032
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150683"
---
# <a name="outbound-spam-protection-in-eop"></a>Proteção contra spam de saída no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, levam a sério o gerenciamento de spam de saída. Um cliente que intencionalmente ou não envia spam de sua organização pode degradar a reputação de todo o serviço e pode afetar a entrega de emails para outros clientes.

Este tópico descreve os controles e notificações projetados para ajudar a evitar spam de saída e o que você pode fazer se precisar enviar mensagens em massa.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>O que os administradores podem fazer para controlar o spam de saída

- Use notificações **internas:** quando um usuário excede [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) os limites de envio do serviço ou das políticas de [spam](configure-the-outbound-spam-policy.md) de saída e é impedido de enviar emails, a política de alerta padrão chamada Usuário impedido de enviar emails envia notificações por **email** aos membros do grupo **TenantAdmins** **(Administradores** globais). Para configurar quem mais recebe essas notificações, consulte Verificar as [configurações de alerta para usuários restritos.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) Além disso, as  políticas de alerta padrão chamadas limite de envio de email excedidas e padrões suspeitos de envio de **email** detectados enviam notificações por email aos membros do grupo **TenantAdmins** **(administradores** globais). Para obter mais informações sobre políticas de alerta, consulte [Políticas de alerta no centro de segurança e conformidade.](../../compliance/alert-policies.md).

- Revise as reclamações de spam de provedores de **email** de terceiros: muitos serviços de email, como Outlook.com, Yahoo e AOL, fornecem um loop de comentários em que, se algum usuário em seu serviço marcar um email do Microsoft 365 como spam, a mensagem será empacotada e enviada de volta para nós para análise. Para saber mais sobre o suporte ao remetente Outlook.com, vá para <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>Como o EOP controla o spam de saída

- **Segregação do tráfego de email de** saída: todas as mensagens de saída enviadas pelo serviço são examinadas em busca de spam. Se a mensagem for determinada como spam, ela será entregue de um pool de endereços IP secundário e menos confiável chamado pool de entrega de _alto risco._ Para saber mais, confira [Pool de entrega com maior risco em mensagens de saída](high-risk-delivery-pool-for-outbound-messages.md).

- **Monitorando nossa reputação de endereço IP de** origem: o Microsoft 365 consulta várias listas de bloqueio de IP de terceiros. Um alerta é gerado se qualquer um dos endereços IP que usamos para emails de saída aparecer nessas listas. Isso nos permite reagir rapidamente quando o spam causou a degradação de nossa reputação. Quando um alerta é gerado, temos uma documentação interna que descreve como remover nossos endereços IP (deslistados) das listas de bloqueio.

- Desabilite contas que enviam **muito spam:** embora segregamos o spam de saída no pool de entrega de alto risco, não podemos permitir que uma conta (frequentemente, uma conta comprometida) envie <sup>\*</sup> spam indefinidamente. Monitoramos contas que estão enviando spam e, quando elas excedem um limite não descoberta, a conta é impedida de enviar emails. Há limites diferentes para usuários individuais e o locatário inteiro.

- Desabilitar contas que enviam muitos **emails** muito rapidamente: além dos limites que buscam mensagens marcadas como spam, também há limites que bloqueiam contas quando atingem um limite geral de mensagens de saída, independentemente do veredito de filtragem de spam nas mensagens de <sup>\*</sup> saída. Uma conta comprometida pode enviar spam de dia zero (anteriormente não reconhecedo) que é perdido pelo filtro de spam. Como pode ser difícil identificar uma campanha legítima de envio em massa versus uma campanha de spam, esses limites ajudam a minimizar possíveis danos.

<sup>\*</sup> Não anunciamos os limites exatos para que os remetentes de spam não possam jogar no sistema e, portanto, podemos aumentar ou diminuir os limites conforme necessário. Os limites são altos o suficiente para impedir que um usuário comercial médio os exceda e baixos o suficiente para ajudar a conter os danos causados por um remetente de spam.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Recomendações para clientes que querem enviar mensagens em massa por meio do EOP

É difícil encontrar um equilíbrio entre os clientes que querem enviar um grande volume de email em relação à proteção do serviço contra contas comprometidas e envios de email em massa com práticas de aquisição de destinatários ruins. O custo de uma fonte de email do Microsoft 365 chegar a uma lista de IIs bloqueados de terceiros é maior do que bloquear um usuário que está enviando muitos emails.

Conforme descrito na Descrição do Serviço do [Exchange Online,](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)usar o EOP para enviar emails em massa não é um uso suportado do serviço e só é permitido com base no "melhor esforço". Para clientes que querem enviar emails em massa, recomendamos as seguintes soluções:

- **Enviar emails em massa por meio** de servidores de email locais: isso significa que os clientes precisarão manter sua própria infraestrutura de email para correspondências em massa.

- **Use um provedor de email** em massa de terceiros: há vários provedores de soluções de email em massa de terceiros que você pode usar para enviar mensagens em massa. Essas empresas têm interesse em trabalhar com os clientes para garantir boas práticas de envio de emails.

Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publica sua lista de participação em <https://www.maawg.org/about/roster> . Vários provedores de email em massa estão na lista e são conhecidos por serem cidadãos responsáveis pela Internet.
