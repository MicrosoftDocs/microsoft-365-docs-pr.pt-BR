---
title: Usar o portal de remoção da lista para ser removido da lista de remetentes bloqueados
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
description: Você está recebendo uma mensagem de erro ao tentar enviar um email para um destinatário cujo endereço de email está no Microsoft 365? Se achar que você não deve receber a mensagem de erro, você pode usar o portal de remoção da lista para se remover da lista de remetentes bloqueados.
ms.openlocfilehash: 39f2c9335f162f26e8bf07a213236e0e0eefef2a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636399"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Usar o portal de remoção da lista para ser removido da lista de remetentes bloqueados

Você está recebendo uma mensagem de erro ao tentar enviar um email para um destinatário cujo endereço de email está no Microsoft 365? Se achar que você não deve receber a mensagem de erro, você pode usar o portal de remoção da lista para se remover da lista de remetentes bloqueados.

## <a name="what-is-the-blocked-senders-list"></a>O que é a lista de remetentes bloqueados?

A Microsoft usa a lista de remetentes bloqueados para proteger seus clientes contra spam, falsificação e ataques de phishing. O endereço IP do seu servidor de email, ou seja, o endereço que seu servidor de email usa para identificar-se na Internet, foi marcado como uma ameaça potencial para a Microsoft 365 por um dos vários motivos. Quando o Microsoft 365 adiciona o endereço IP à lista, ele impede todas as outras comunicações entre o endereço IP e qualquer um de nossos clientes por meio de nossos data centers.

Você saberá que foi adicionado à lista quando receber uma resposta a uma mensagem de email que inclui um erro parecido com o seguinte:

> 550 5.7.606-649 acesso negado, envio de IP proibido [_endereço IP_]; Para solicitar a remoção dessa lista, acesse https://sender.office.com/ e siga as instruções. Confira mais informações [em notificações de falha na entrega de email no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

em que  _IP address_ é o endereço IP do computador no qual o servidor de email é executado.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Para usar o portal de remoção da lista para ser removido da lista de remetentes bloqueados

1. Em um navegador da Web, acesse [https://sender.office.com](https://sender.office.com).

2. Siga as instruções descritas na página. Certifique-se de usar o endereço de email ao qual a mensagem de erro foi enviada e o endereço IP que é especificado na mensagem de erro. Você só pode inserir um endereço de email e um endereço IP por visita.

3. Clique em **Enviar**.

    O portal envia um email para o endereço de email que você fornecer. O email será parecido com o seguinte: ![captura de tela do email recebido ao enviar uma solicitação pelo portal de deslista](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Clique no link confirmação no email enviado a você pelo portal de remoção da lista.

    Isso leva você de volta ao portal de remoção da lista.

5. No portal de remoção da lista, clique em **remover IP da lista**.

    Depois que o endereço IP for removido da lista de remetentes bloqueados, as mensagens de email desse endereço IP serão entregues aos destinatários que usam o Microsoft 365. Portanto, certifique-se de que os emails enviados a partir desse endereço IP não sejam ofensivos ou mal-intencionados; caso contrário, o endereço IP pode ser bloqueado novamente.

    > [!NOTE]
    > Pode levar até 24 horas ou os resultados podem variar muito antes de as restrições serem removidas.

Consulte [criar listas de remetentes seguros no office 365](create-safe-sender-lists-in-office-365.md) e [proteção de spam de saída no Office 365](outbound-spam-controls.md) para impedir que o IP seja removido.
