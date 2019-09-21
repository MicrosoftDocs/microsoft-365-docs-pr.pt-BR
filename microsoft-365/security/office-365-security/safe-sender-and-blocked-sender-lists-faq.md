---
title: Listas de remetentes seguros e remetentes bloqueados no Exchange Online
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
ms.openlocfilehash: 5b1082e0a8f492da1ebc559b0958a6ef76f9a70c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073766"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Listas de remetentes seguros e remetentes bloqueados no Exchange Online

Como um administrador do Exchange Online ou do Exchange Online Protection (EOP), você pode ajudar a garantir que uma mensagem de email que viaja pelo serviço não seja marcada como spam. Uma maneira de fazer isso é criar listas de remetentes seguros e remetentes bloqueados para as pessoas da sua organização. 
  
 *Consulte a versão atualizada das dicas e procedimentos sobre como trabalhar com essas listas como um administrador no* [Impedir email falso positivo marcado como spam com uma lista de segura ou outras técnicas](https://go.microsoft.com/fwlink/p/?LinkID=534224). 
  
Se você não for um administrador e só quiser gerenciar seu próprio lixo eletrônico no Outlook usando uma lista de remetentes seguros, Confira as etapas desta visão geral do filtro de [lixo eletrônico](https://go.microsoft.com/fwlink/?LinkId=817222). 
  
## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Quais são os limites de remetentes seguros e bloqueados no Exchange Online?

Os limites de remetentes seguros e bloqueados no Exchange Online diferem dos limites do Active Directory e do Outlook. São eles:
  
- Limite de remetente seguro: 1.024
    
- Limite de remetentes bloqueados: 500
    
Observação:
  
Você pode experimentar o erro descrito no [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app). Para resolver esse problema, desmarque a caixa de seleção "confiar em emails de meus contatos". Como alternativa, diminua a quantidade de endereços de email que estão na sua pasta de contatos padrão para trazê-lo dentro do limite máximo permitido de 1024 no Exchange Online que está definido para o atributo "parâmetros MaxSafeSenders". Para obter mais informações sobre este atributo e o cmdlet Set-Mailbox, confirao seguinte tópico:
  
[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)
  
## <a name="see-also"></a>Confira também

[Filtragem de remetente no Exchange 2016](http://technet.microsoft.com/library/b833f864-ff10-46a0-a653-28fb9ba30896.aspx)

