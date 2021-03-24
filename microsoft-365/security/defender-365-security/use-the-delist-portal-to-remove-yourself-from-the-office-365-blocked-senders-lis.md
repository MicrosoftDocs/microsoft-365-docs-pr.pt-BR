---
title: Remova-se da lista de envios bloqueados
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá a usar o portal de lista para remover a si mesmo da lista de envios bloqueados do Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c4488f5e5607d71da35b2921e863fb02195467e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052797"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Usar o portal de remoção da lista para ser removido da lista de remetentes bloqueados

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Você está recebendo uma mensagem de erro ao tentar enviar um email para um destinatário cujo endereço de email está no Microsoft 365? Se você acha que não deve receber a mensagem de erro, pode usar o portal de lista de listas para remover a si mesmo da lista de envios bloqueados.

## <a name="what-is-the-blocked-senders-list"></a>O que é a lista de envios bloqueados?

A Microsoft usa a lista de remetentes bloqueados para proteger seus clientes contra spam, falsificação e ataques de phishing. O endereço IP do servidor de email, ou seja, o endereço que seu servidor de email usa para se identificar na Internet, foi marcado como uma possível ameaça ao Microsoft 365 por uma das várias razões. Quando o Microsoft 365 adiciona o endereço IP à lista, ele impede toda a comunicação entre o endereço IP e qualquer um de nossos clientes por meio de nossos datacenters.

Você saberá que foi adicionado à lista quando receber uma resposta a uma mensagem de email que inclui um erro parecido com o seguinte:

> 550 5.7.606-649 Acesso negado, proibiu o envio de IP [_endereço IP_]; Para solicitar a remoção dessa lista, visite <https://sender.office.com/> e siga as instruções. Para obter mais informações, [consulte Email non-delivery reports in Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

em que  _IP address_ é o endereço IP do computador no qual o servidor de email é executado.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Para usar o portal de lista para remover a si mesmo da lista de envios bloqueados

1. Em um navegador da Web, acesse <https://sender.office.com>.

2. Siga as instruções descritas na página. Certifique-se de usar o endereço de email ao qual a mensagem de erro foi enviada e o endereço IP que é especificado na mensagem de erro. Você só pode inserir um endereço de email e um endereço IP por visita.

3. Clique em **Enviar**.

    O portal envia um email para o endereço de email que você fornecer. O email será parecido com o seguinte: Captura de tela do email recebido ao enviar uma solicitação por meio ![ do portal de lista de espera](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Clique no link confirmação no email enviado a você pelo portal de remoção da lista.

    Isso leva você de volta ao portal de remoção da lista.

5. No portal de remoção da lista, clique em **remover IP da lista**.

    Depois que o endereço IP for removido da lista de remetentes bloqueados, as mensagens de email desse endereço IP serão entregues aos destinatários que usam o Microsoft 365. Portanto, certifique-se de que os emails enviados a partir desse endereço IP não sejam ofensivos ou mal-intencionados; caso contrário, o endereço IP pode ser bloqueado novamente.

    > [!NOTE]
    > Pode levar até 24 horas ou os resultados podem variar bastante antes que as restrições sejam removidas.

Consulte [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md) and [Outbound spam protection in EOP](outbound-spam-controls.md) to prevent an IP from being blocked.