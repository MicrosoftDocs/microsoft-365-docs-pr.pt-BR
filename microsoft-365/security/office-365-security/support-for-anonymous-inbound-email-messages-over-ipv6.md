---
title: Adicionar suporte para emails de entrada anônimos por IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: O administrador pode saber como configurar o suporte para emails de entrada anônimos de fontes IPv6 no Exchange Online e no Exchange Online Protection.
ms.openlocfilehash: 67e839249d41381be22bbccf6b09d1616c387c66
ms.sourcegitcommit: 748bc3484b7ccbd65b558f495b6fa42196c3c571
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "43083636"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a>Adicionar suporte para email de entrada anônimo por IPv6 no Office 365

As organizações do Office 365 com caixas de correio do Exchange Online e do proteção autônoma do Exchange Online (EOP) sem caixas de correio do Exchange Online dão suporte a emails de entrada anônimos por IPv6. O servidor de email IPv6 de origem deve cumprir os seguintes requisitos:

- O endereço IPv6 de origem deve ter um registro de pesquisa de DNS reverso válido que permite que o destino encontre o nome de domínio do endereço IPv6.

- O remetente deve passar por verificação SPF (definida na [RFC 7208](https://tools.ietf.org/html/rfc7208)) ou [verificação DKIM](https://dkim.org/) (definida na [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).

Antes que sua organização possa receber emails de entrada anônimos por IPv6, um administrador precisa entrar em contato com o suporte da Microsoft e solicitá-lo:

1. Abra o centro de administração do Microsoft <https://admin.microsoft.com/adminportal/home> 365 em e clique em **ajuda** (?).

2. No submenu **precisa de ajuda?** que aparece, digite algo descritivo na caixa de pesquisa (por exemplo, "solicitar email IPv6 de entrada anônimo") e pressione Enter.

3. Na parte inferior da página, clique em **entrar em contato com o suporte**.

4. Na página de **suporte de contato** que aparece, preencha e verifique as informações (role para baixo conforme necessário) e clique em **entrar em contato comigo**.

Depois que o suporte à mensagem IPv6 de entrada anônima estiver habilitado em sua organização, a mensagem passará pela filtragem de mensagens normal fornecida pelo serviço.

## <a name="troubleshooting"></a>Solução de problemas

- Se o servidor de email de origem não tiver um registro de pesquisa de DNS reverso IPv6, as mensagens serão rejeitadas com o seguinte erro:

  > 450 o serviço 4.7.25 não está disponível, enviando endereço IPv6 [2a01:111: F200: de 2004:: 240] deve ter um registro DNS reverso.

- Se o remetente não passar pela validação SPF ou DKIM, as mensagens serão rejeitadas com o seguinte erro:

  > 450 4.7.26 serviço não disponível, a mensagem enviada por IPv6 [2a01:111: F200:2004:: 240] deve passar pela validação SPF ou DKIM.

- Se você tentar receber mensagens IPv6 anônimas antes de optar por você, a mensagem será rejeitada com o seguinte erro:

  > 550 o serviço 5.2.1 não está disponível, [contoso.com] não aceita emails sobre IPv6.

## <a name="for-more-information"></a>Para obter mais informações

[Suporte para validação de mensagens assinadas por DKIM](support-for-validation-of-dkim-signed-messages.md)
