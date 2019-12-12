---
title: Remetente seguro e listas de remetentes bloqueados no Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Como um administrador do Exchange Online ou do Exchange Online Protection (EOP), você pode ajudar a garantir que uma mensagem de email que viaja pelo serviço não seja marcada como spam. Uma maneira de fazer isso é criar listas de remetentes seguros e remetentes bloqueados para as pessoas da sua organização.
ms.openlocfilehash: 5530fa8c8ee5a83c4e8515a8f31f91e45b2ec97b
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971669"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Remetente seguro e listas de remetentes bloqueados no Exchange Online

Como um administrador do Exchange Online ou do Exchange Online Protection (EOP), você pode ajudar a garantir que uma mensagem de email que viaja pelo serviço não seja marcada como spam. Uma maneira de fazer isso é criar listas de remetentes seguros e remetentes bloqueados para as pessoas da sua organização.

*Consulte a versão atualizada das dicas e procedimentos sobre como trabalhar com essas listas como um administrador em* [como impedir que bons emails sejam marcados como spam no Office 365](https://docs.microsoft.com/microsoft-365/compliance/prevent-email-from-being-marked-as-spam).

Se você não for um administrador e só quiser gerenciar seu próprio lixo eletrônico no Outlook usando uma lista de remetentes seguros, Confira as etapas da[visão geral do filtro de lixo eletrônico](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Quais são os limites de remetentes seguros e bloqueados no Exchange Online?

Os limites de remetentes seguros e bloqueados no Exchange Online diferem dos limites do Active Directory e do Outlook. Que são:

- Limite de remetente seguro: 1.024

- Limite de remetentes bloqueados: 500

Observação:

Você pode experimentar o erro descrito no [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app). Para resolver esse problema, desmarque a caixa de seleção "confiar em emails de meus contatos". Como alternativa, diminua a quantidade de endereços de email que estão na sua pasta de contatos padrão para trazê-lo dentro do limite máximo permitido de 1024 no Exchange Online que está definido para o atributo "parâmetros MaxSafeSenders". Para obter mais informações sobre este atributo e o cmdlet Set-Mailbox, confirao seguinte tópico:

[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a>Confira também

[Filtragem de remetente no Exchange Server](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
